# Evaluation cases

These are **evaluation definitions, not benchmark results**. They encode failures that previously changed the Skills and make those corrections reviewable.

Run each case in a clean session with the named Skill. Record:

- host and host version;
- model;
- repository commit or Skill hash;
- date;
- exact prompt and fixture hash;
- output path;
- assertion-by-assertion result;
- human reviewer and unresolved ambiguity.

A passing run must satisfy every assertion without accessing files outside the allowed fixture root. Installation or `available` status is not a pass.

The initial cases cover unconfirmed notes, incompatible metric definitions, missing predecessor history, interview attribution drift, and unauthorized idealized operations assumptions. Add negative cases when new failure modes are discovered.