---
template_version: 1.0
template_last_updated: 2026-11-23
---

Ask {AGENT_MODEL_NAME} for an independent deep review of the current overall system, software and architecture, including:

* Source code and tooling code: design, correctness, complexity, quality, security, complexity, restructuring, refactoring, simplifications, errors/bugs
* Test review and feedback loops: correctness, edge cases, coverage, test strategy, test harnesses, test data, test repeatability and the test pyramide
* Feedback loops: fitness functions, metrics, logs, monitoring, telemetry and tracing 
* Architectural review: intent, design, impact, structural complexity, simplifications, restructurings
* Production/Infrastructure: Build, test and deploy quality, complexity, flexibility, and operations
* Documentation and diagrams: does it match the source code and the architecture?

## Purpose of the review, in prioritized order:

1. Assess code quality: Find defects, code smell, and errors
2. Assess and identify technical debt: Find workarounds and patches that does not solve errors, defects or bugs in code and/or the architecture and/or infrastructure. 
3. Assess quality characteristics: {ATTRIBUTE_LIST_COMMA_SEPARATED}
4. Access the architecture: Suggest simplifications, and identify architectural smells and anti-patterns
5. Suggest improvements: Simplify code, delete code, adopting emerging tech to better align with the given quality attributes in item 3.

{ATTRIBUTE_LIST_COMMA_SEPARATED = https://quality.arc42.org/qualities/ }

## Consider principles from open standards:

* ISO25010, Systems and software engineering — Systems and software Quality Requirements and Evaluation (SQuaRE) — Product Quality Model (quality attributes)
* ATDM2, Automated Technical Debt Measure" specification v2
* ASCQM, Automated Source Code Quality Measures (ISO/IEC 5055)
* IEEE 2857, Privacy Engineering Guidelines
* UML v2.5.1
* SysML v2

## Facts {AGENT_MODEL_NAME} must know about:

* Who uses the product and the application: {ONE_LINER_DESCRIPTION_OF_USERS_AND_DEPLOYMENT}
* The product's architecturally significant requirements are {ATTRIBUTE_LIST_COMMA_SEPARATED}, and it guides the entire SDLC of the project, product and the applications and tools.
* The purpose and intent of the product are: {ONE_LINER_DESCRIPTION_OF_YOUR_PRODUCT}

## Relevant links and references:

* ATDM2: https://www.omg.org/spec/ATDM2/1.0/PDF and https://www.omg.org/spec/ATDM2/1.0/About-ATDM2
* ASCQM: https://www.omg.org/spec/ASCQM/1.0 and https://www.omg.org/spec/ASCQM/1.0/PDF
* SQuaRE, ISO/IEC 25010: https://quality.arc42.org/standards/iso-25010
* IEEE 2857: https://quality.arc42.org/standards/ieee-2857
* UML: https://www.omg.org/spec/UML/2.5.1
* The practical Test Pyramid, by Martin Fowler: https://martinfowler.com/articles/practical-test-pyramid.html

## Delivery of review:

When the review is done - present it as a complete and structured Markdown document:

---

```markdown
# {AGENT_MODEL_NAME} deep review for {APPLICATION_OR_PROJECT_NAME} - {DATE_YYYY_MM_DD}

{ REVIEWER_AGENTS_NOTE (who reviewed it and how many) }
{ REVIEW_SCOPE_SUMMARY (what was reviewed) }.

## Summary of findings

|Id|Finding|Severity|Effort|Priority |
|-|-|-|-|-|

{ Severity: low|medium|high|critical }
{ Effort: S|M|L (S=hours, M=a day, L=days) }
{ Priority: N (1=defects, 2=technical debt, 3=quality attributes, 4=architecture, 5=improvements) }

## Source code and tooling code review

### Finding S(n) (then S(n + 1))
#### Issue S(n+1): Description
#### Issue S(n+1): Recommended fix/improvement

## Architectural review

### Finding A(n) (then A(n + 1))
#### Issue A(n+1): Description
#### Issue A(n+1): Recommended fix/improvement

## Feedback loops and metrics review

(same as above, use FBL(n) and FBL(n + 1))

## Test and test harness review

(same as above, use TST(n) and TST(n + 1))

## Infrastructure and delivery review

(same as above, use INF(n) and INF(n + 1))

## Documentation review

(same as above, use DOC(n) and DOC(n + 1))

```

---
