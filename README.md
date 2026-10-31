# portainer-agents

Swarm agents for the ore-dock-110-x swarm (110-4, 110-5, 110-6).

Deployed in `global` mode so one agent runs on every Linux node, which is
what lets Portainer manage stacks on the non-manager nodes.

The compose was derived from the live service spec:
- image `portainer/agent:2.45.2`
- `AGENT_CLUSTER_ADDR=tasks.portainer-agents`
- docker socket and `/var/lib/docker/volumes` bind mounts
- `mode: global`, constraint `node.platform.os==linux`
