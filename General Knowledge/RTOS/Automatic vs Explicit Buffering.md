
Automatic:

The OS/system manages the buffer size automatically (unbounded queue).

|✅ Pros|❌ Cons|
|---|---|
|Sender never blocks — just keeps sending|Can run out of memory if buffer grows indefinitely|
|Easier to use — no manual management needed|Harder to control flow and prioritize messages|

