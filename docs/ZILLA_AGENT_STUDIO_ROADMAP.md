# Zilla AI — Android Local Agent Studio

Status: planning / audit. Source: PocketPal fork.

## Vision
Offline GGUF LLM + optional agent tools, safe Python execution, visual Internet/API connections, MCP, and Local/Remote/Hybrid inference.

## Verified stack
React Native 0.87.1, llama.rn 0.13.0-rc.7, ONNX Runtime RN, WatermelonDB. Reuse existing agent/tool abstractions; do not rewrite as a Kotlin app.

## Roadmap
- [ ] R0 Audit AgentRunner, tool registry, model loading, network paths, permissions and existing tests.
- [ ] R1 Agent Studio UI: agent profiles, scoped tools, execution logs, confirmations.
- [ ] R2 Visual Internet Connections: opt-in HTTPS allowlist, credentials in secure storage, per-request approval, test connection.
- [ ] R3 Python sandbox feasibility and implementation: isolate execution, enforce time/memory/storage/network limits.
- [ ] R4 MCP client: transport, tool discovery, explicit scopes, connection editor.
- [ ] R5 Local / Remote / Hybrid inference and OpenAI-compatible endpoint setup.
- [ ] R6 UA/EN/RU localization, security tests, Android builds and release preparation.

## First implementation slice
1. Audit existing agent tools and permission handling.
2. Add an opt-in HTTP GET tool to the existing registry, not a parallel registry.
3. Require HTTPS + user-approved hostname allowlist + explicit approval.
4. Set timeouts and response-size limits, block private-network/loopback addresses by default, sanitize logs and secrets.
5. Test deny/allow/error cases, run lint/typecheck/tests and Android emulator/device before PR.

## Contribution constraints
Follow repository AGENTS.md. Do not claim tests passed until executed. Edit only src/locales/en.json; other translations via Weblate.

## Planning note
GitHub Issues are disabled for this fork (API 410), so this document is the tracked roadmap until Issues are enabled.
