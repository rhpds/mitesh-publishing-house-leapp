# Leapp-O-Matic: The One-Click Path to RHEL 10

## Problem Statement

Infrastructure teams managing mixed RHEL fleets face a costly and disruptive upgrade cycle when new major versions ship. Manual in-place upgrades using Leapp are error-prone, time-consuming, and difficult to standardize across RHEL 8 and RHEL 9 systems at scale. This demo shows how Ansible Automation Platform 2.6 turns that complexity into a repeatable, auditable single-click operation — enabling infrastructure engineers to upgrade entire fleets to RHEL 10 with confidence.

## Target Audience

- **Role:** Infrastructure engineers, system administrators
- **Experience level:** Intermediate to Advanced
- **What they already know:** RHEL administration basics, familiarity with Ansible concepts, understanding of OS upgrade challenges
- **What they don't know:** How to use Leapp for in-place upgrades, how to automate multi-version fleet upgrades with AAP, how to assess and remediate upgrade inhibitors at scale
- **Prerequisites:** Basic RHEL system administration experience, familiarity with Ansible Automation Platform concepts

## Learning Objectives

1. Explain the Leapp in-place upgrade path from RHEL 8.x and RHEL 9.x to RHEL 10 and when to use it
2. Demonstrate pre-upgrade inhibitor analysis across a mixed-version RHEL fleet using Leapp assessment jobs in AAP
3. Execute an automated in-place upgrade from RHEL 8.10, RHEL 9.5, and RHEL 9.7 to RHEL 10 using a single AAP job template
4. Validate post-upgrade system state and confirm successful RHEL 10 landing across all target systems

## Content Type

Demo (presenter-led)

## Products & Technologies

- Red Hat Enterprise Linux 10
- Red Hat Enterprise Linux 9.7, 9.5
- Red Hat Enterprise Linux 8.10
- Red Hat Ansible Automation Platform 2.6
- Leapp (in-place upgrade framework)

## Module Map

| Module | Title | Duration |
|--------|-------|----------|
| 1 | The Upgrade Challenge: RHEL Lifecycle and Leapp | ~10 min |
| 2 | Pre-Upgrade Analysis — Running Inhibitor Checks Across the Fleet | ~10 min |
| 3 | One-Click Execution — AAP Job Template Kicks Off the Upgrade | ~20 min |
| 4 | Post-Upgrade Validation — Verifying a Clean RHEL 10 Landing | ~10 min |
| — | **Total demo** | **~50 min** |

## Difficulty Level

Intermediate to Advanced

## Environment

**Presenter view:** Pre-deployed environment on CNV with AAP 2.6 controller, a job template for Leapp upgrades, and four managed RHEL instances (2x RHEL 9.7, 1x RHEL 9.5, 1x RHEL 8.10). The presenter demonstrates the full upgrade workflow from the AAP web console — no CLI installs required during the demo.

**Automation needed:** Yes — AAP 2.6 controller fully configured with inventory, credentials, and the Leapp upgrade job template pre-loaded. All RHEL instances pre-provisioned and registered as managed nodes.

## Infrastructure Requirements

- **Base infrastructure:** cloud-vms-base (AgnosticD v2)
- **Sizing:** TBD — estimating 1 AAP controller node (8 CPU, 16GB RAM), 4 RHEL managed nodes (2 CPU, 4GB RAM each, 40GB disk)
- **Cloud provider:** CNV
- **Automation approach:** Ansible (AAP 2.6 job templates via playbook-rhel10-upgrader)
- **Existing workloads to reuse:** Custom workloads from https://gitlab.com/ansible-ssa/playbook-rhel10-upgrader
- **New workloads needed:** AgnosticD v2 cloud-vms-base configuration wrapping the upgrader playbooks; AgnosticV catalog item for CNV
