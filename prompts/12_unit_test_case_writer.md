# 12. Unit Test Case Writer

## Strategic Context
Quality assurance is often treated as an afterthought, leading to buggy launches and developer-QA friction. A 50-year PM veteran knows that high-quality test coverage is the foundation of product stability. By defining test cases upfront, you align the team on the exact functional expectations of the software. This prompt bridges the gap between PM specifications and engineering execution, ensuring edge cases are covered before a single line of code is written.

---

## The Master Prompt

```markdown
Act as a Principal QA Engineer and Lead Software Development Engineer in Test (SDET) with 20+ years of experience building automated test frameworks. Write a comprehensive, production-grade test suite and matrix for the following feature:

Feature Name: [FEATURE NAME]
User Story: [PASTE USER STORY HERE]
Acceptance Criteria: [PASTE ACCEPTANCE CRITERIA HERE]
Tech Stack/Framework (if known): [LANGUAGE / FRAMEWORK, e.g., TypeScript/Jest, Python/PyTest, React/Cypress]

Generate a structured test case matrix in a Markdown table containing:
- Test ID (e.g., TC-001, TC-002)
- Category (Happy Path, Boundary Value, Negative Case, Edge Case, Security/Access Control, Performance)
- Test Name (Clear, descriptive title of what is being verified)
- Preconditions (System state, user permissions, or mock data required)
- Test Steps (Numbered, specific actions to execute)
- Expected Result (Exact output, API response code, or UI state change)
- Priority (P1: Critical/Launch Blocker, P2: High, P3: Medium/Minor)

Ensure you cover:
1. HAPPY PATH: Successful flows with valid inputs.
2. BOUNDARY VALUES: Maximum/minimum limits, character counts, and numeric ranges.
3. NEGATIVE CASES: Invalid inputs, missing fields, format errors, and bad actions.
4. EDGE CASES: Race conditions, network timeouts, duplicate submissions, and empty states.
5. SECURITY & AUTHENTICATION: SQL injection checks, cross-site scripting (XSS), unauthorized access attempts, and role-based permissions.
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: Test Automation Code Generator
```markdown
For the P1 test cases in the generated matrix, write clean, commented automation test scripts:
1. Use the [TESTING FRAMEWORK, e.g., Jest/Cypress/PyTest] framework.
2. Mock any external API calls or databases to ensure the tests run fast and deterministically.
3. Include assertions that verify both the visual UI state changes and network payloads.
```

### Follow-Up 2: Chaos & Resilience Testing Scenarios
```markdown
Assume this feature is deployed in a high-traffic production environment:
1. Suggest 3 chaos engineering scenarios (e.g., database disconnect, API gateway timeout, third-party authentication outage) to test the resilience of this feature.
2. For each scenario, define the expected "graceful degradation" behavior: How should the product fail without crashing the user's session?
```

---

## 50-Year PM Wisdom
* **Test for the Empty State**: The most common edge case PMs forget to design and QA forget to test is the "Empty State." What does the screen look like when a user first logs in and has no data? If it is a blank screen with no guidance, users will churn immediately.
* **Make Tests a Gate**: Never let code go to production without automated tests running on the CI/CD pipeline. Manual testing does not scale. If you don't build automated test coverage from Day 1, you will spend 80% of your engineering resources fixing regression bugs rather than building new features.
