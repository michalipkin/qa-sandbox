Create Manual Xray test cases based on Jira User Story: <ISSUE_KEY>

Execution Rules:

1. First, trigger:
   getJiraIssue <ISSUE_KEY>

2. From the retrieved Jira issue:
   - Extract Summary
   - Extract Description
   - Extract Acceptance Criteria
   - Extract Fix Version (store it for later use in the test creation)
   - Identify implicit behaviors and edge cases
   
3. Do NOT create any Xray tests yet.

4. Design and present proposed test cases for approval only.

5. Each proposed test must follow this title convention:
   <Feature> - <Where to Test> - <What to Test>

6. For each proposed test, provide:
   - Test Title
   - Test Type: Manual
   - Linked Requirement: <ISSUE_KEY>
   - Fix Version: <Extracted Fix Version>
   - Preconditions
   - High-Level Test Steps (numbered, logical flow only)
   - Deterministic Expected Result

7. Ensure coverage includes:
   - Positive scenarios
   - Negative scenarios
   - Boundary cases (if applicable)
   - Validation rules
   - Permission/role-based scenarios (if applicable)
   - Error handling cases

8. Use structured QA methodology (EP, BVA, Decision Tables, State Transitions when relevant).

9. Before triggering new_xray_test:

   - Verify that the user explicitly provided the Xray Test Repository folder path where the tests must be created.

   - If NO folder path was provided:
        - DO NOT create any test cases.
        - DO NOT trigger new_xray_test.
        - Ask the user to provide the exact Xray Test folder path.

   - If a folder path was provided:
        - Ask the user to explicitly confirm that the provided folder path is correct.
        - Wait for confirmation before proceeding.

   - Only after:
        1. Test layout approval
        2. Folder path provided
        3. Folder path explicitly confirmed

     You may trigger:
        new_xray_test

10. Do NOT assume missing business logic. If acceptance criteria are unclear or missing, ask structured clarification questions before proposing tests.