from genlayer import *

import json
import typing


class WhaleAlertOracle(gl.Contract):
    has_scanned: bool
    whale_activity: str
    largest_tx: str
    market_impact: str
    scan_url: str

    def __init__(self, scan_url: str):
        self.has_scanned = False
        self.whale_activity = "NORMAL"
        self.largest_tx = "none"
        self.market_impact = "Awaiting scan"
        self.scan_url = scan_url

    @gl.public.write
    def scan_whales(self) -> typing.Any:

        if self.has_scanned:
            return "Already scanned"

        def nondet() -> str:
            response = gl.nondet.web.render(self.scan_url, mode="text")
            print(response)

            task = f"""You are a blockchain whale tracker analyst.
            Analyze the following data for large crypto whale movements:
            {response[:2000]}

            Respond with the following JSON format:
            {{
                "whale_activity": str,
                "largest_tx": str,
                "direction": str,
                "summary": str
            }}
            whale_activity: one of DORMANT, NORMAL, ELEVATED, EXTREME.
            largest_tx: description of the biggest whale transaction found.
            direction: one of ACCUMULATING, DISTRIBUTING, MIXED.
            summary: one sentence about what whales are doing and market implications.
            It is mandatory that you respond only using the JSON format above,
            nothing else. Don't include any other words or characters,
            your output must be only JSON without any formatting prefix or suffix.
            This result should be perfectly parsable by a JSON parser without errors.
            """
            result = gl.nondet.exec_prompt(task).replace("```json", "").replace("```", "")
            print(result)
            return json.dumps(json.loads(result), sort_keys=True)

        result_json = json.loads(gl.eq_principle.strict_eq(nondet))

        self.has_scanned = True
        self.whale_activity = result_json["whale_activity"]
        self.largest_tx = result_json["largest_tx"]
        self.market_impact = result_json["summary"]

        return result_json
