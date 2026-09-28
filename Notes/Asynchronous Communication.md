---
type: principle
tags: [software]
created: 2026-09-28
---

# Asynchronous Communication

The sender doesn't need the receiver to act immediately - the message waits
until the receiver is ready, so the sender isn't blocked or failed by
whatever the receiver's current availability or speed is.

Same shape shows up everywhere, not just in software: a restaurant ticket
(the waiter drops it and moves on rather than waiting at the kitchen
window), a voicemail or text versus needing someone to pick up the phone
right now.

## Shows up in

- [[SQS]]
