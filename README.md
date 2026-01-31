# sageos-public
Secure Agent Governed Execution OS
SAGE OS Secure Agent Governed Execution OS (Governed execution runtime for AI agents — auditable, killable, least-privilege.)

Website · Request Investor Demo - contact@sageos.ai · LinkedIn - https://www.linkedin.com/in/saranraj-kumar-pmp/

⭐ Enterprise-grade “execution governance” for AI agents operating on endpoints + edge + offline environments.

Why SAGE OS exists

AI agents are becoming powerful, but execution is still dangerously under-governed:

Agents can read/write files, trigger tools, and move data

Enterprises need audit trails, approval gates, and kill switches

Many “agent platforms” focus on orchestration/control planes — but execution still leaks risk at the runtime layer (where actions happen).

SAGE OS addresses the execution layer: ✅ Every task is governed with limits + permissions + approvals + audit logs. ✅ Execution is stoppable mid-run (kill switch). ✅ Designed to run offline / edge / endpoint where cloud control-plane governance can’t enforce real-time.

(Layman: “We make agents behave like robots in a factory—strict rules, logs, and emergency stop.”)

What we’ve built (Pilot V1) ✅ Task Type #1: search_text_in_folder (governed file search)

A controlled sandbox task that scans .txt files under an allowed root folder and returns:

matched files

hit counts

line numbers + snippets

deterministic limits (runtime, max files, max matches)

kill switch support

full audit correlation (RUN/TASK/ORG/AGENT)

Evidence (not claims)

Live UI demo (Streamlit)

Audit logs prove every lifecycle event:

RUN_START → TASK_SUBMITTED → TASK_RUNNING → TOOL_READ → TASK_MATCH_FOUND → TASK_FINISHED

Limit enforcement:

TASK_LIMIT_MAX_MATCHES

Kill switch supported:

scheduler pre-dispatch kill + sandbox in-loop kill checks

Architecture (V1)

SAGE OS is intentionally “boring” and strict:

Control Plane (Scheduler)

validates task type

enforces org isolation

dispatches tasks to sandbox

checks kill switch before dispatch

Sandbox Execution

executes task loops

enforces:

root path restrictions

deny symlinks

file extension allow-list

file size caps

runtime caps

match caps

kill checks inside loops

Tools Layer (Real-world gateway)

the only allowed way to touch filesystem/network

can require approvals (human-in-the-loop)

Audit Trail

all events correlated to RUN/TASK/ORG/AGENT

supports per-run audit logs (roadmap: tamper-evident hash chaining)

(Layman: “Control plane decides what’s allowed; sandbox executes it safely; tools touch the world; audit logs record everything.”)

Current Guardrails (V1 Policy)

Allowed file types: .txt

Max files scanned: 1000

Max file size: 500KB

Max runtime: default 10s (configurable per task)

Max matches: default 100 (configurable)

Deny symlink root, symlink dirs/files

Prevent path escape via realpath checks

Kill switch: pre-dispatch + in-loop checks

Audit logs include correlation IDs

Roadmap (Investor-ready) Next 7 days

Per-run audit logs (logs/runs/<run_id>.log)

Tamper-evident hashing at end of run (RUN_LOG_HASH)

UI: run log viewer + download run audit bundle

Next 30 days

Task Type #2: governed write/edit task (with approvals)

Policy templates (role-based)

Signed task manifests + deterministic replay

Next 60–90 days

Endpoint agent runtime packaging (Windows/Linux)

Offline governance mode

Fleet telemetry (optional cloud sync)

SOC/Compliance export formats (JSONL)

Ideal Customers (ICP)

Regulated industries: finance, healthcare, legal, government

Enterprises running AI agents on:

laptops/desktops (endpoints)

field devices (edge)

offline environments

Teams needing:

auditability

approvals

kill switch governance

least-privilege execution

(ICP = Ideal Customer Profile)

Contact / Investor Demo

📩 Email: contact@sageos.ai 🌐 Website: https://sageos.ai

Disclaimer

SAGE OS is compliance-ready design (not certified). Built for strict governance foundations first.
