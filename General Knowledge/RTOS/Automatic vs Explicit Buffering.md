
Automatic:

The OS/system manages the buffer size automatically (unbounded queue).

|✅ Pros|❌ Cons|
|---|---|
|Sender never blocks — just keeps sending|Can run out of memory if buffer grows indefinitely|
|Easier to use — no manual management needed|Harder to control flow and prioritize messages|

Explicit:

#### Explicit Buffering

The buffer has a **fixed, defined size** set by the programmer.

|✅ Pros|❌ Cons|
|---|---|
|Memory usage is controlled and predictable|Sender blocks when buffer is full|
|Easier to reason about system resource limits|Requires careful sizing — too small causes bottlenecks|