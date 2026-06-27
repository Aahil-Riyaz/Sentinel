# System Overview

## Purpose

Sentinel is an AI-assisted investigation platform designed to help analysts collect, organize, correlate, and analyze evidence from multiple public sources.

The goal is not to replace investigators. Instead, Sentinel helps investigators manage complex investigations by keeping evidence organized, explaining AI-generated insights, and making relationships easier to understand.

---

# Core Idea

Sentinel treats **evidence** as the center of every investigation.

Everything else in the platform is built around that evidence.

Instead of searching for information and immediately generating conclusions, Sentinel follows a structured investigation workflow:

```
Collect Evidence
        ↓
Validate Evidence
        ↓
Correlate Evidence
        ↓
Build Relationships
        ↓
Generate AI Insights
        ↓
Human Review
        ↓
Investigation Report
```

This workflow ensures that conclusions can always be traced back to supporting evidence.

---

# Main Components

Sentinel is divided into several major subsystems.

## Case Management

Responsible for creating and managing investigations.

A case contains:

* Evidence
* Notes
* Timeline
* Relationship graph
* AI findings
* Reports

---

## Evidence Engine

The Evidence Engine stores and organizes collected information.

Examples include:

* Usernames
* Email addresses
* Domains
* IP addresses
* Documents
* Images
* Social media profiles
* URLs

Each piece of evidence should include enough metadata to identify where it came from and when it was collected.

---

## Investigation Engine

The Investigation Engine coordinates the overall investigation process.

Its responsibilities include:

* Running investigation workflows
* Managing evidence relationships
* Tracking investigation progress
* Coordinating plugins
* Preparing information for AI analysis

---

## AI Reasoning Engine

The AI layer assists investigators by:

* Summarizing evidence
* Explaining relationships
* Identifying missing information
* Highlighting possible investigation paths

AI should never invent facts.

Every insight should reference supporting evidence whenever possible.

---

## Relationship Graph

The graph represents how entities are connected.

Examples include:

* Person → Email
* Email → Domain
* Domain → Organization
* Username → Social Profile

This helps investigators discover relationships that are difficult to identify manually.

---

## Timeline Engine

The Timeline Engine organizes investigation events chronologically.

Examples include:

* Evidence collected
* New relationships discovered
* AI analysis completed
* Investigator notes
* Important external events

---

## Plugin System

Sentinel is designed to be extensible.

Plugins will allow new data sources and investigation capabilities to be added without modifying the core platform.

The core application should not depend on individual plugins.

---

# High-Level Architecture

```
                Frontend
                    │
                    ▼
             REST API / Backend
                    │
    ┌───────────────┼────────────────┐
    │               │                │
    ▼               ▼                ▼
Case Engine   Investigation Engine   AI Engine
    │               │                │
    └───────────────┼────────────────┘
                    │
             Evidence Repository
                    │
     ┌──────────────┼──────────────┐
     ▼              ▼              ▼
 Relationship   Timeline      Plugins
     Graph         Engine
```

---

# Design Goals

Sentinel is designed to be:

* Modular
* Testable
* Secure
* Explainable
* Extensible
* Maintainable

These goals take priority over implementing features as quickly as possible.

---

# Version 1 Scope

The first version of Sentinel focuses on building a strong platform rather than supporting every possible investigation source.

Version 1 should provide:

* Case management
* Evidence management
* Timeline generation
* Relationship graph
* Plugin framework
* AI-assisted reasoning
* Investigation reporting

Additional capabilities can be added later through the plugin system.

---

# Summary

Sentinel is designed to help investigators work with evidence more effectively.

The platform combines structured case management, explainable AI, relationship analysis, and extensibility into a single investigation workflow while keeping investigators in control of every conclusion.
