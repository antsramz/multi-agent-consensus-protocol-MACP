# MACP — Multi‑Agent Consensus Protocol

## Purpose
The Multi‑Agent Consensus Protocol (MACP) defines how multiple autonomous agents reach agreement on shared decisions, tasks, or outcomes.  
It ensures stable, conflict‑free consensus in distributed agent environments.

MACP prevents:

- conflicting decisions  
- deadlocks  
- inconsistent outputs  
- unstable multi‑agent behavior  
- dominance by a single agent  

This template is the consensus backbone of the ecosystem.

---

## When to Use This Template
Use MACP when:

- multiple agents must agree on a shared decision  
- arbitration (MPA) and delegation (DTM) involve more than one agent  
- agents propose different solutions  
- a unified output is required  
- conflict resolution is needed  
- distributed workflows must remain deterministic  

MACP is required before using MRML (Memory Recall & Mapping Layer).

---

## Inputs
The agent receives:

- proposals from participating agents  
- each agent’s ASP profile  
- delegation results from DTM  
- arbitration context from MPA  
- constraints and safety rules  
- consensus threshold or voting rules  

---

## Outputs
MACP produces a **consensus packet**, including:

- final agreed‑upon decision  
- proposal rankings  
- rejected proposals  
- consensus method used  
- dissenting agents (if any)  
- safety or policy flags  

---

## JSON Schema (Machine‑Native)

```json
{
  "consensus": {
    "consensus_id": "string",
    "proposals": [
      {
        "agent_id": "string",
        "proposal_id": "string",
        "content": "string",
        "priority": "number"
      }
    ],
    "rules": {
      "method": "majority | weighted | unanimous",
      "threshold": "number"
    },
    "evaluation": {
      "selected_proposal": "string",
      "rejected_proposals": ["string"],
      "reasoning": "string",
      "dissenting_agents": ["string"],
      "policy_flags": ["string"]
    }
  }
}


Example Usage
{
  "consensus": {
    "consensus_id": "cons-301",
    "proposals": [
      {
        "agent_id": "alpha-01",
        "proposal_id": "p1",
        "content": "Use deterministic workflow generation.",
        "priority": 9
      },
      {
        "agent_id": "beta-02",
        "proposal_id": "p2",
        "content": "Use adaptive workflow generation.",
        "priority": 6
      }
    ],
    "rules": {
      "method": "majority",
      "threshold": 0.5
    },
    "evaluation": {
      "selected_proposal": "p1",
      "rejected_proposals": ["p2"],
      "reasoning": "p1 aligns with deterministic mode and meets all constraints.",
      "dissenting_agents": ["beta-02"],
      "policy_flags": []
    }
  }
}

Integration Notes
MACP should be used after DTM selects candidate agents.

Consensus must be deterministic and reproducible.

Voting or weighting rules should be stable across sessions.

MACP feeds directly into MRML (memory mapping) and ERP (recovery).

Multi‑agent systems rely on MACP to avoid conflict and fragmentation.

Payment (Short Version)
Payments accepted for this template:

BTC

XMR

LTC

ETH / USDT / USDC (ERC‑20)

SOL (USDT/USDC)

Delivery is fully automated and zero‑contact.

---

# ⭐ When you're ready  
Save this README into your **MACP** repo, then tell me:

**MACP saved**

I’ll verify it exactly like the others — and then we’ll move to:

### **Template #7 — MRML (Memory Recall & Mapping Layer)**

