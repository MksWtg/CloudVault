1) confirm FE and BE run inside the same container to allow them to talk, and how to enable internet access for presumably just backend
	1) some examples of needing to query internet
2) What will our exposed API/SDK be? 
	1) Requirements: language agnostic- not writing an sdk because dont want to support python, cpp, haskell, etc.
	2) while we want strong typing, this contradicts requirement #1
	3) we want it to be capable of 100hz+
	4) we know IPC is allowed since they run next to each other
	5) between http endpoint and rpc
3) lets say i make an sdk. this would be the core control logic. we want to ship this with a telemetry server i guess