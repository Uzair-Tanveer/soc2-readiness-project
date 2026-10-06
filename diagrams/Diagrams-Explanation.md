# Diagrams — Plain-English Explanation

This file is a quick-reference guide to the two diagrams in this folder. 
Read this before talking about the diagrams out loud — it explains what 
each one shows, in simple terms, without the technical jargon.

---

## Diagram 1: Architecture Diagram (`01-architecture-diagram.md`)

### What it shows (one sentence)
This diagram shows **where everything lives** — the actual pieces of 
technology (servers, databases, logins) that make up the NorthLedger 
platform, and how they connect to each other.

### How to explain it simply
"This is basically a map of the system. A customer opens their browser, 
their request goes through a load balancer — think of it like a traffic 
cop directing requests to the right place — then into the actual web app, 
which talks to a database and file storage. Everything is encrypted, and 
anyone trying to log in has to go through MFA. There's also a backup copy 
of everything running in a second AWS region, in case the main one goes 
down."

### Why it matters for this project
- It proves the controls aren't just theoretical — things like encryption 
  (CC6.6-01) and MFA (CC6.1-01) actually map to real pieces of this diagram.
- The "DR Region" box ties directly to the disaster recovery gap 
  (CC9.1-02) — the backup exists, but we never tested if it actually works 
  fast enough (that's the gap).

### If asked "why does this diagram matter in a SOC 2 context?"
Auditors want to see that security controls aren't just written policy — 
they want to see where in the actual system those controls are enforced. 
This diagram is the "proof" that MFA, encryption, and logging aren't just 
claims — they're built into the real architecture.

---

## Diagram 2: Data Flow Diagram (`02-data-flow-diagram.md`)

### What it shows (one sentence)
This diagram shows **where customer financial data goes** — step by step, 
from the moment a customer uploads it, to where it's stored, checked for 
accuracy, and eventually deleted.

### How to explain it simply
"When a customer uploads their financial data, the system first checks if 
the data looks valid — if it's garbage data, it gets rejected right away. 
If it's good, it gets tagged by sensitivity level, stored in an encrypted 
database, and run through accuracy checks before it's ever shown in a 
report. There's also an automatic process that deletes old data once it's 
past its retention period, so we're not holding onto customer data forever."

### Why it matters for this project
- This diagram is specifically about **Confidentiality** and 
  **Processing Integrity** — two of the Trust Services Criteria this 
  project covers.
- It visually connects to two real gaps: inconsistent data classification 
  tagging (C1.1-01) and incomplete validation for unusual/edge-case data 
  (PI1.2-01).

### If asked "why does this diagram matter in a SOC 2 context?"
This diagram proves the company understands exactly where sensitive data 
lives and how it moves — which is the foundation of being able to protect 
it. Auditors specifically look for this kind of data flow mapping because 
you can't secure what you haven't mapped.

---

## Quick Comparison (if asked "what's the difference between these two diagrams?")

| | Architecture Diagram | Data Flow Diagram |
|---|---|---|
| **Focuses on** | The system itself (servers, databases, logins) | The data itself (where it goes, how it's handled) |
| **Answers the question** | "What does the system look like?" | "What happens to customer data as it moves through the system?" |
| **Most relevant TSC categories** | Security (CC6), Availability (A1) | Confidentiality (C1), Processing Integrity (PI1) |
| **Simple analogy** | Think of this like a building blueprint — walls, rooms, doors | Think of this like a delivery tracking map — where the package goes, step by step |

---

## One-Liner Summary (memorize this if nothing else)

- **Architecture Diagram** = "Here's what the system is built out of."
- **Data Flow Diagram** = "Here's what happens to customer data once it enters that system."

Together, they answer the two questions every SOC 2 auditor cares about most: 
**"What are you protecting it with?"** and **"What exactly are you protecting?"**