---
type: permanent
tags: [containers]
created: 2026-10-21
---

# Container Image

A read-only, packaged filesystem plus metadata (what to run), built from a
[[Dockerfile]] by the [[Docker]] engine. It is a template, not a running
thing: starting it creates a [[Container]], an isolated process using that
image. The same image can be started many times.

The [[Dockerfile]] only matters at build time. To reach another machine, the
image is pushed to a [[Container Registry]], and the engine on the other
machine pulls it from there before running it.

## Sequence

```mermaid
sequenceDiagram
    participant D as Dockerfile
    participant R as Registry
    participant E as Docker engine
    participant C as Container

    D->>E: 1 build
    Note over E: 1 image saved locally
    E->>R: 2 push image
    R->>E: 3 pull image
    E->>C: 4 run image
```

Source: general Docker knowledge, no verified vault or doc source. See also
[[Containerisation]].
