# Open: who runs the tools (M4) and why a loop needs a limit (M6)

On a spaced attempt, Riley said the model runs each tool itself (M4), although they also correctly chose that the model outputs a tool request, and they chose to let a stuck agent keep running (M6).
Neither is shown to be corrected yet, so revisit both before building on tool calling or designing the assistant's loop.

**Evidence:** quiz 0001, submission s2: q4 reason (M4), q3 (M6), q2 (correct choice of a tool request).

**Implications:** Have Riley label each step of a trace "model" or "program" and say when the loop stops.
Also incomplete: Riley named only the tool's name as how the model chooses a tool (q6), which matters for the mission goal of writing a tool description.
