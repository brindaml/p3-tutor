# Riley showed the belief that the model runs tools itself (M4)

On their first attempt at quiz 0001, Riley had the model open the booking system itself and run three tools inside a single model call.
They identified the loop as what makes an agent, but the split between model and program needs work before tool definitions, and it affects how they estimate cost per request.

**Evidence:** quiz 0001, submission s1, items q2 and q4 (both M4). Item q5 says the tool result is sent back to the model, but gives no reason.

**Implications:** Have Riley trace a request with separate model and program lanes, counting model calls. This answers the "not yet checked" point in record 0002 for this attempt. The later attempt, s2, has not been graded, so check it before assuming M4 is still held.
