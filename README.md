# Team Programming Checkpoint

**Date:** Friday, 9 October 2026  
**Time limit:** 2 hours (120 minutes)  
**Exercises:** 19  
**Programming language:** Any language  
**Submission:** Your own private GitHub repository  
**Reviewer:** [Anasmoner2022](https://github.com/Anasmoner2022)

The facilitator will announce the start time. Your deadline is exactly 120 minutes after that start time.

Read [PROBLEMS.md](PROBLEMS.md), implement the exercises, test your work, and submit using the steps below. All 19 exercises are part of this checkpoint.

## 1. Set up your private repository

1. Create a repository under your GitHub account. Use a clear name, such as `checkpoint-2026-10-09-your-name`.
2. Set its visibility to **Private**.
3. Add **Anasmoner2022** as a collaborator: open the repository's **Settings**, select **Collaborators** in the Access section, choose **Add people**, search for `Anasmoner2022`, select that account, and send the invitation.
4. Check that the invitation was sent. The reviewer receives access after accepting it; you can submit while the invitation is pending.

These access steps follow [GitHub's collaborator invitation guide](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/repository-access-and-collaboration/inviting-collaborators-to-a-personal-repository).

## 2. Organize your answers

Use this simple repository structure:

```text
checkpoint-2026-10-09-your-name/
├── README.md       # Your name, setup, run commands, and solution notes
├── src/            # Your implementations
└── tests/          # Runnable tests or a test runner
```

You may keep your functions in one source file or split them into several files. Make it easy to identify the implementation for every exercise by its number or function name.

Start your repository README by copying [SUBMISSION_TEMPLATE.md](SUBMISSION_TEMPLATE.md) and replacing its placeholders. Include:

- Your full name and GitHub username.
- The language and version you used.
- Exact commands to install any dependencies, run your code, and run your tests.
- A brief explanation of each approach and its time and space complexity.
- Any unfinished exercises or known limitations.

Include the source, tests, and any dependency files needed to run them. Keep the repository runnable from a fresh download or clone.

## 3. Test your solutions

- Run the examples in [PROBLEMS.md](PROBLEMS.md).
- Use [test-cases.json](test-cases.json) as test data, or put equivalent test cases in your test runner. It contains 177 cases with expected results.
- Check every exercise, including boundary values and repeated calls with different inputs.
- Your tests should compare actual and expected results and clearly identify failed cases.
- Follow the result types and rounding rules in the problem sheet.

The JSON file provides test data; you supply the implementations and test runner in your chosen language.

## 4. Submit when finished

Complete these steps before the timer reaches 120 minutes:

1. Commit and push your final source, tests, and README to your private repository.
2. Check on GitHub that the latest files are visible in the repository.
3. Confirm that **Anasmoner2022** has collaborator access or a pending invitation.
4. Send the facilitator your **repository link** and **final commit hash** using your usual team communication channel.
5. List any exercises you did not finish. Submit the work you completed by the deadline.

The submitted commit identifies the version to review. Keep later changes separate from that submitted version.

### Submission message

Copy this message and replace the placeholders:

```text
Name: <your full name>
GitHub username: <your username>
Repository: <private repository URL>
Final commit: <commit hash>
Language and version: <language and version>
Completed exercises: <numbers, or 1–19>
Incomplete exercises / known issues: <list, or None>
Reviewer access: <Invitation sent / Collaborator access confirmed>
```

## Final checklist

- [ ] My repository is private.
- [ ] I invited Anasmoner2022 as a collaborator.
- [ ] My source code is pushed to GitHub.
- [ ] My README explains how to run the source and tests.
- [ ] I ran tests for all completed exercises and recorded any failures.
- [ ] Exercise 5 uses no built-in absolute-value function.
- [ ] Exercise 10 uses a one-line Boolean decision.
- [ ] I listed unfinished work and known issues honestly.
- [ ] I sent the repository link and final commit hash before the deadline.

## Suggested use of the 120 minutes

| Time | Activity |
| --- | --- |
| First 10 minutes | Read the tasks, create the repository, and send the collaborator invitation. |
| Next 90 minutes | Implement the exercises and test as you go. |
| Next 15 minutes | Run all tests and complete your submission README. |
| Last 5 minutes | Push, check the repository, and send your submission message. |

## How your work will be reviewed

The review checks correctness across the stated constraints, the two explicit exercise restrictions, readable code, runnable tests, accurate complexity explanations, and a complete submission.

