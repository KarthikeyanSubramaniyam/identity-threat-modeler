# STRIDE Identity Threat Modeling & Attack Surface Analyzer

<p align="center">
  <img src="https://img.shields.io/badge/Security-Defensive_Auditor-blue?style=flat" alt="Type">
  <img src="https://img.shields.io/badge/Status-Architectural_Showcase-success?style=flat" alt="Status">
  <img src="https://img.shields.io/badge/Python-3.10+-3776AB?style=flat&logo=python&logoColor=white" alt="Python">
</p>

> 🔒 **Technical Showcase & Architecture Specification**  
> *This repository provides public architectural documentation, system specifications, and implementation summaries. Full production source code, internal test suites, and proprietary algorithms are maintained in a secure private repository.*

---

## 📌 Executive Summary

**Category**: Threat Modeling & Application Security  
**Tech Stack**: `Python 3.10+ · STRIDE Threat Modeling · OAuth 2.0 / OIDC · Identity Architecture`  

Automated threat modeling tool mapping identity architectures (OAuth, OIDC, SAML, IAM) against the STRIDE methodology to uncover structural attack vectors.

---

## 🎯 The Problem It Solves

Identity and authentication architectures are the primary target for modern adversaries. Designing identity systems without formal threat modeling results in authentication bypasses and token theft vulnerabilities.

---

## ⚙️ How the Engine Works

1. **Architecture Model Ingestion**: Ingests JSON/YAML identity component definitions (IdP, Relying Parties, Token Issuers, APIs, User Agents, Storage).
2. **Trust Boundary Mapping**: Identifies data flows traversing network and trust boundaries (e.g. browser $	o$ API gateway $	o$ internal auth service).
3. **STRIDE Vulnerability Enumeration**: Systematically evaluates every trust boundary crossing against:
   - **Spoofing**: Weak client authentication, unsigned JWTs, missing PKCE
   - **Tampering**: Token modification, state parameter manipulation
   - **Repudiation**: Missing authentication audit trails
   - **Information Disclosure**: Tokens logged in query params or client storage
   - **Denial of Service**: Token endpoint rate limiting vulnerabilities
   - **Elevation of Privilege**: Role claim manipulation, missing token audience checks
4. **Threat Matrix Output**: Emits prioritized threat matrices with specific architectural mitigations.

---

## 🚀 Key Capabilities

- Automates STRIDE threat modeling for authentication and authorization flows
- Validates OAuth 2.0 / OIDC implementations against RFC 6819 security recommendations
- Identifies token replay, CSRF, and audience mismatch attack vectors
- Produces executive threat modeling scorecards and mitigation blueprints

---

## 🏗️ System Data Flow & Architecture

```
+-----------------------------------+
|  Target Input / Configuration    |
|  (JSON Snapshots / Policies)      |
+-----------------+-----------------+
                  |
                  v
+-----------------------------------+
|  1. Schema Normalization Engine   |
|  Validates types & formats        |
+-----------------+-----------------+
                  |
                  v
+-----------------------------------+
|  2. Core Analytical Pipeline      |
|  Heuristic rule evaluation,       |
|  invariant checks & drift diffs   |
+-----------------+-----------------+
                  |
                  v
+-----------------------------------+
|  3. Risk Classification           |
|  Assigns severity: INFO / HIGH    |
+-----------------+-----------------+
                  |
                  v
+-----------------------------------+
|  4. Structured Findings & Report  |
|  Root cause, evidence &           |
|  actionable remediation steps     |
+-----------------------------------+
```

---

## 📄 Findings Output Structure

The engine generates structured, machine-parsable JSON reports adhering to this standard audit schema:

```json
{
  "results": [
    {
      "resource": "resource-identifier",
      "severity": "HIGH",
      "check": "CHECK_IDENTIFIER",
      "detail": "Descriptive analysis of the identified security posture issue.",
      "remediation": "Actionable step-by-step guidance to restore compliant state.",
      "evidence": {
        "observed_field": "value",
        "required_policy": "enforced_policy"
      }
    }
  ],
  "count": 1,
  "scope": "Comprehensive defensive security audit"
}
```

---

## 🔒 Source Code & Enterprise Inquiries

To protect proprietary intellectual property and client operational security:
* **Public Repository**: Contains comprehensive architecture specifications, schemas, and design overviews.
* **Private Repository**: Contains the complete production implementation, continuous integration pipelines, and full regression test suites.

For architectural questions or enterprise inquiries, connect via [LinkedIn](https://www.linkedin.com/in/karthikeyansubramaniam04/) or visit the [Portfolio Site](https://karthikeyansubramaniyam.github.io).
