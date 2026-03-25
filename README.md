# Straughter Guthrie

Systems engineer. Elixir/OTP, Erlang, Python.

Building agent infrastructure that treats LLM orchestration as a distributed systems problem, not a prompt engineering problem.

## Current work

**VAOS** (Viable Autonomous Operating System) — an Elixir/OTP framework for epistemic agent orchestration. Three libraries, one runtime:

| Library | What it does | Size | Tests |
|---------|-------------|------|-------|
| vas-swarm | Agent orchestrator. Signal classification, 3-tier routing, 48 tools, 18 LLM providers. | 92K lines Elixir + 20K Rust | ~3,320 |
| [vaos-ledger](https://github.com/jmanhype/vaos-ledger) | Epistemic engine. Claims, evidence, attacks tracked with Expected Information Gain scoring. | 6,718 lines | 208 |
| [vaos-knowledge](https://github.com/jmanhype/vaos-knowledge) | Triple store. ETS-backed, SPARQL subset, 4 OWL 2 RL rules. | 1,095 lines | 108 |

The core idea: agents should reason about *what they don't know* (epistemic governance) rather than just executing tool chains. The investigate tool uses adversarial dual-prompt architecture with citation verification — it argues against its own findings before reporting them.

**[vaos.sh](https://vaos.sh)** — SaaS interface to the VAOS runtime.

## Selected repos

| Repo | Language | What |
|------|----------|------|
| [vggt-mps](https://github.com/jmanhype/vggt-mps) | Python | Apple Silicon (MPS) port of Meta's VGGT visual geometry grounded transformer |
| [MCPhoenix](https://github.com/jmanhype/MCPhoenix) | Elixir | Model Context Protocol gateway for Phoenix applications |
| [wf-substrate](https://github.com/jmanhype/wf-substrate) | Erlang | 43 workflow patterns compiled into native OTP control structures |
| [speckit](https://github.com/jmanhype/speckit) | Shell | Spec-driven development toolkit |
| [cloudflare_durable_ex](https://github.com/jmanhype/cloudflare_durable_ex) | Elixir | Cloudflare Durable Objects client for Elixir |
| [ace-playbook](https://github.com/jmanhype/ace-playbook) | Python | Adaptive Code Evolution — self-modifying agent architecture |

## Infrastructure

4-node Tailscale mesh: Mac Mini (gateway, BEAM runtime), MacBook Pro (development), Linux GPU server (3090, training/inference), Windows workstation (Draco, orchestration). OpenClaw for cross-node agent dispatch.

## Organizational theory

The architecture draws from Stafford Beer's Viable System Model (1972) — recursive autonomy with meta-systemic coordination. Each agent subsystem mirrors VSM's System 1-5 structure: operations, coordination, optimization, intelligence, policy.

References: Beer's *Brain of the Firm*, Ashby's Law of Requisite Variety, Wiener's cybernetic feedback loops. See the [viable-systems](https://github.com/viable-systems) org for the upstream VSM implementation.
