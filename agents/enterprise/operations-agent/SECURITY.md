# Security Configuration

NemoClaw sandbox policy for this agent.

## Network Policy

Deny-by-default egress. Only explicitly listed endpoints are reachable.

```yaml
network:
  default: deny
  enforcement: strict
  tls: required
  rules:
    - name: inference
      endpoints:
        - "api.anthropic.com:443"
        - "statsig.anthropic.com:443"
        - "sentry.io:443"
      binaries:
        - "/usr/local/bin/claude"
      methods: ["*"]

    - name: openclaw
      endpoints:
        - "openclaw.ai:443"
        - "docs.openclaw.ai:443"
      binaries:
        - "/usr/local/bin/openclaw"
      methods: ["GET", "POST"]

    - name: clawhub
      endpoints:
        - "clawhub.com:443"
      binaries:
        - "/usr/local/bin/openclaw"
      methods: ["GET", "POST"]
```

## Filesystem Policy

```yaml
filesystem:
  rules:
    - path: /sandbox
      access: read-write
    - path: /tmp
      access: read-write
    - path: /sandbox/.openclaw-data
      access: read-write
    - path: /dev/null
      access: read-write
    - path: /sandbox/.openclaw
      access: read-only
    - path: /usr
      access: read-only
    - path: /lib
      access: read-only
    - path: /etc
      access: read-only
    - path: /proc
      access: read-only
    - path: /dev/urandom
      access: read-only
```

## Process Isolation

```yaml
process:
  run_as_user: sandbox
  run_as_group: sandbox
  seccomp: enabled
  landlock: enabled
```

## Inference Routing

```yaml
inference:
  route: local
  gateway: openshell
  credentials: host-only
  credential_store: ~/.nemoclaw/credentials.json
  credential_mode: "0600"
```

## Supply Chain

```yaml
supply_chain:
  blueprint_digest_verification: enabled
  docker_image_pinning: enabled
```
