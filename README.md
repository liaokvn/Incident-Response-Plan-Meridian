# Incident-Response-Plan-Meridian
Incident response plan and ransomware tabletop exercise for a mid-size electronics manufacturer, aligned to ISO 27035 and SOC 2 CC7.x

# Incident Response Plan & Tabletop Exercise — Meridian Electronics

A self-directed GRC project building a full Incident Response Plan (IRP) for a mid-size manufacturer and stress-testing it through a tabletop simulation of a ransomware incident — the core compliance requirement behind ISO 27035 and SOC 2 CC7.x.

## Project Summary

This project builds an Incident Response Plan for **Meridian Electronics**, a fictional mid-size electronics manufacturer (~200 employees) with a hybrid IT/OT environment — corporate systems (ERP, email, file servers) alongside a separate operational technology environment (production line control systems). Rather than treating the IR plan as a static document, the project tests it against a realistic tabletop scenario: a phishing email leads to credential compromise, which an attacker uses to deploy ransomware against corporate systems overnight on a weekend. The project follows the full ISO 27035 incident management lifecycle:

1. **IR Team design** — building a realistic 19-role response structure across Core, Extended, and Support/External tiers, including associate/junior staff who execute hands-on response actions
2. **Procedure design** — writing Detection, Containment, Eradication, and Recovery procedures specific to a hybrid IT/OT environment, with explicit phase-gating (no remediation during detection, no recovery before eradication is confirmed)
3. **Tabletop simulation** — running the scenario against a realistic, mixed-quality response (not a perfect one), including a 24/7/365 hybrid MSSP monitoring model tested specifically by setting the incident overnight on a weekend
4. **Incident documentation** — producing a filled Incident Report mapped to ISO 27035, SOC 2 CC7.x, and ISO 27001 Annex A control references, plus a fully timestamped Incident Timeline
5. **Lessons Learned analysis** — identifying three real findings from the simulation and converting each into a specific, traceable policy update to the IR Plan itself

## Deliverables

| File | Description |
|---|---|
| `Meridian_Incident_Response_Plan.docx` / `.pdf` | The reusable IR Plan: Purpose, full 19-role team structure, Detection/Containment/Eradication/Recovery procedures, Lessons Learned process, Severity-Based Escalation Matrix, and recurring testing requirement |
| `Meridian_Incident_Simulation_Report.docx` / `.pdf` | The one-time simulation record: filled Incident Report with compliance framework mapping, full timestamped timeline, and Lessons Learned findings |

## What I Did

- Designed a 19-role incident response team spanning Core decision-makers, Extended business-function leads, Support/External partners, and the associate/junior staff who actually execute response steps — rather than a flat, oversimplified team structure
- Distinguished IT-side containment from OT/production-side containment, reflecting that "isolate the system" means something materially different (and riskier) on a manufacturing floor than on a corporate network
- Wrote phase-gated procedures across Detection, Containment, Eradication, and Recovery, each with an explicit goal and an explicit rule about what *not* to do yet (e.g., never powering off a compromised machine before forensic evidence is preserved)
- Built a 24/7/365 hybrid MSSP monitoring model and specifically tested it by setting the simulated incident overnight on a weekend, rather than during convenient business hours
- Produced a full incident timeline with real timestamps, calculating Time to Detect, Time to Contain, and Time to Recover — the same metrics real SOC 2 audits and board security reports reference
- Mapped the incident response directly to ISO 27035 lifecycle stages, SOC 2 CC7.2/7.3/7.4, and ISO 27001 Annex A controls, so the documentation is usable as actual audit evidence
- Identified three genuine findings from the simulation and converted each into a four-part structured finding (Root Cause, Why It Matters, Policy Update, and which IR Plan section it updates) rather than vague "lessons learned" prose
- Updated the IR Plan itself based on the findings — adding a Severity-Based Escalation Matrix and a formal recurring tabletop testing requirement — so the simulation produced a better plan, not just a report about one

## What I Learned

- **A plan is only as good as its untested assumptions.** The original IR plan implicitly assumed business-hours detection. That assumption was invisible until the simulation specifically placed the incident overnight — a reminder that tabletop exercises exist to find the gaps a plan doesn't know it has, not to rehearse the parts that already work.
- **Speed in one phase doesn't guarantee speed everywhere.** Adding 24/7 MSSP monitoring dropped detection time by over 95%, but the Cyber Insurance Carrier notification still quietly waited for business hours, because no one had explicitly extended the "always-on" assumption to that specific step. Fast technical response and fast business-process response are two different things that both need to be designed for.
- **Roles need a clear chain of command, not just a list of names.** Having a Technical Lead report findings to an Incident Commander — rather than making independent containment calls — prevents two common real failure modes: unauthorized business-impacting decisions, and indecision when someone is waiting for permission that was never going to come.
- **OT and IT containment are not interchangeable.** Writing "isolate the affected system" once and applying it everywhere ignores that a factory floor has physical safety and equipment-damage considerations a corporate network doesn't. This requires a genuinely different role (Controls Engineer) and a genuinely different procedure, not just a copy-pasted IT step.
- **A finding is only useful if it's traceable to a specific fix.** Writing "communication could be better" teaches nothing. Writing "add Cyber Insurance Carrier notification to the Incident Commander's on-call checklist, updating IR Plan Section 2" is something a real organization could implement and verify next quarter.

## Real-World Application

Incident response planning and testing is a named, explicit requirement in major compliance frameworks, not an optional best practice:

- **SOC 2 CC7.x compliance** — auditors specifically look for evidence of incident detection, response, and recovery procedures, and increasingly expect evidence that those procedures have actually been tested, not just written
- **Cyber insurance underwriting** — insurers increasingly require evidence of a tested IR plan, a pre-contracted forensics partner, and defined notification procedures before issuing or renewing coverage, exactly the elements built into this plan
- **Manufacturing-specific risk** — manufacturing is one of the most frequently targeted industries for ransomware specifically because production downtime creates outsized pressure to pay; an IT/OT-aware IR plan reflects the real operational stakes this industry faces
- **Regulatory breach notification timing** — the Severity-Based Escalation Matrix added after this exercise directly addresses a common real-world compliance failure: notification clocks that start at discovery, not at whenever Legal happens to wake up and find out

## Conclusion

This project demonstrates the fourth core pillar of GRC analyst work, completing a portfolio that now spans compliance frameworks (NIST 800-53), internal risk management (the BudgetWise risk register), third-party risk (the Slack vendor assessment), and incident response (this project). Of the four, this one is the most explicitly cyclical: a tabletop exercise isn't a one-time deliverable, it's a mechanism for continuously finding the gap between what a plan assumes and what is actually true about an organization's readiness. The most valuable output of this project wasn't the original IR plan — it was the updated one, written only after the simulation revealed exactly where the first version would have failed. That distinction, between writing a plan and proving a plan, reflects the difference between compliance-on-paper and operational readiness that real GRC work is ultimately responsible for closing.

---
*This is a self-directed portfolio project using a fictional organization and simulated incident. It does not reflect any real company's incident history or response capabilities.*
