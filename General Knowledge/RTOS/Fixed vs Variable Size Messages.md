
#### Fixed-Sized Messages

Messages are always a **predetermined, constant size**.

|✅ Pros|❌ Cons|
|---|---|
|Simple to implement at OS level|Wasteful if message is smaller than the fixed size|
|Predictable memory and buffer management|Inconvenient for programmers dealing with varying data|

#### Variable-Sized Messages

Messages can be **any size** depending on the data being sent.

|✅ Pros|❌ Cons|
|---|---|
|Flexible — send exactly as much data as needed|More complex to implement at OS level|
|No memory waste from padding|Buffer management is harder and unpredictable|