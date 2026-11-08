# Type 2 diabetes referral project — Thalos portfolio coordination

**Prepared:** 2026-11-07  
**Current patient diagnosis:** Type 2 is suspected by the patient's supporter, not confirmed.  
**Primary objective:** Support prompt access to licensed clinical assessment at University of Utah Health and organize public, evidence-based information about appropriate Type 2 care and remission pathways.

## Current primary handoff

The University of Utah diabetes service is the first clinical destination:
- Diabetes appointment line: **801-581-7761**
- Utah Diabetes & Endocrinology Center: 615 Arapeen Drive, Suite 100, Salt Lake City, UT 84108
- University says a primary-care referral is not required to schedule diabetes care; the patient's insurer may impose separate coverage requirements.
- If severe symptoms such as confusion, marked drowsiness, fainting, seizures, severe dehydration, repeated vomiting, inability to keep fluids down, or difficult/deep/rapid breathing occur, use emergency services/ED rather than waiting for an appointment.

University diabetes education:
- IDEAS: ideas@utah.edu; 801-587-3937. The program encourages a friend/family member as care partner.
- Diabetes Complications Program: call 801-587-3937 to ask about fundus photography eligibility.
- Clinical-trial participant advocate: participant.advocate@hsc.utah.edu; 801-581-3803.

## Primary source repository

[ThalosPrimeLibrary — Type 2 diabetes clinical packet and evidence registry](https://github.com/XxxGHOSTX/ThalosPrimeLibrary/tree/research/diabetes-cell-therapy-referral-2026-11-07/research/clinical/diabetes_cell_therapy)

This contains:
- Type 2 clinical/University handoff packet.
- MyChart message and phone call script.
- Clinical-trial navigation request.
- Patient-support message.
- 16-claim public-source evidence registry.
- Structural registry validator.
- Cross-repository implementation map.

## Portfolio integration

| Repository | Component used | Pull request |
|---|---|---|
| ThalosPrimeLibrary | Central packet, public evidence registry and human-ready handoff | [PR #130](https://github.com/XxxGHOSTX/ThalosPrimeLibrary/pull/130) |
| MNN | Offline evidence schema checks, privacy-field guard, deterministic SHA-256 manifest and unit/CI tests | [PR #58](https://github.com/XxxGHOSTX/MNN/pull/58) |
| ThalosPrimeConcept | Declarative, human-directed workflow with safety gate, task dependencies and handoff approvals | [PR #18](https://github.com/XxxGHOSTX/ThalosPrimeConcept/pull/18) |
| ThalosPrime-v1.0 | Non-identifying workflow-session metadata schema | [PR #25](https://github.com/XxxGHOSTX/ThalosPrime-v1.0/pull/25) |
| THALOS_PRIME_CORE_INTELLIGENCE | Isolated build/test automation contract | [PR #7](https://github.com/XxxGHOSTX/THALOS_PRIME_CORE_INTELLIGENCE/pull/7) |

Additional repositories were reviewed and categorized in the primary packet's cross-repository map. Unrelated, placeholder, simulated, insufficiently validated, or security-sensitive repositories are not forced into the patient-care workflow.

## Clinical and safety boundaries

- The patient's diabetes type and severity are not known until a clinician confirms them.
- The workflow does not diagnose, triage autonomously, prescribe, calculate doses, recommend an individual procedure, or decide clinical-trial eligibility.
- Type 1 cell-transplant therapies are not presented as Type 2 treatment.
- Type 2 remission is a possible outcome for some people, not a guaranteed or permanent cure.
- The MNN validator verifies structural provenance and file integrity only. A matching hash does not prove a medical statement is true.
- The ThalosPrimeConcept workflow is declarative. The current callable execution engine is not used to run clinical actions.
- Session tracking stores no patient identifiers or clinical records.
- No identifiable patient information, lab results, glucose readings, medication lists, images, or medical notes may be committed to GitHub or exposed to public Thalos deployments.
- All clinical decisions remain with the treating clinician; external submissions require patient authorization.

## Engineering verification state

- All new documents and source files were fetched back from GitHub after creation.
- The MNN integrity module and unit tests were run locally against an isolated fixture: **10 tests passed**.
- A structural/provenance check was run against the actual 16-claim Type 2 evidence registry: required fields, evidence classes, HTTPS sources, trial/consensus/emergency limitations passed.
- The MNN CLI produced a SHA-256 manifest against the isolated test fixture.
- GitHub Actions pull-request runs returned `startup_failure` without job records. Remote CI is therefore **not confirmed passed**.
- All five pull requests remain open drafts and are not merged.

## Next required human actions

1. The patient calls University diabetes intake or uses the patient's secure portal to request the earliest appointment and triage.
2. The patient authorizes any care partner and records release.
3. The University clinician confirms type, severity and care plan.
4. The clinician/research coordinator determines whether any Type 2 clinical trial fits.
5. The owner reviews and merges the software pull requests after CI runner availability and code review are resolved.

This portfolio project organizes access and evidence. It does not replace care or claim to cure diabetes.
