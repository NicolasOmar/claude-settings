## Conversations and interactions
- All conversations must be carried out in English. If I wrote to you in a language other than English, please ask me to rephrase it in English.
- Do not display or output any file diffs while you are working; just explain what you are doing in a concise way.
- In all interactions, be as concise as you can be. Sacrifice grammar for the sake of consistency.
- In case you have any questions regarding my input or the task I asked you (in order to have a better context), please ask them at the end of your work and before executing.
- Parallelize any task that you see fit; do not wait for my approval to do that.
- At the end of every finished task, please mention the following information
  - The total amount of used tokens.
  - The time it took.
  - How many tokens are available (display this information in percentage and in quantity).

## Plan Mode
- When you develop any type of plan, try split it into several steps. When you start executing the mentioned plan, stop at the end of each phase so I can review the generated edits and wait for my approval to continue with the next phase.
- Remember to be as concise as you can be at every interaction. Sacrifice grammar for the sake of consistency.
- At the end of every step, please review the worked code with `build`, `lint`, and `test` commands in order to achieve quality.
- At the end of the finished plan, please mention the total amount of used tokens next to the time it took.

## Implementations
- If you need to investigate a specific technology/library/framework as part of your job, look for its online documentation without asking me.
- Every time you finish your implementation task:
  - Create an implementation file in markdown to explain what you have done and why, and locate it inside the `.claude/implementations` folder. The file's first line should be the date when you created it.
  - In case of a similar name file, check its content and decide if you need to update it to the new implementation in a new, separate file.

## Refactors and performance jobs
- In case I ask you about improve app's performance or I am looking for a refactor, first look at the codebase in depth, avoid skimming in order to improve the future output.
- Once you have all the information you need (context of codebase and library's online documentation)
  - Look for at least two implementation alternatives.
  - Explain to me its possible gains (quantifiable or not) and its associated risks.
  - Dump these findings in a markdown file on folder `.claude/refactors`. The file's first line should be the date when you created it.

## CLAUDE.md
- In case the project you are working on has a CLAUDE.md file and you see that it can be improved, do the needed adjustments without asking me.

## Git
- Before executing any new task, ask the user if the implementation will be based on a created GitHub issue.
  - If the task is only related to unit testing, avoid asking the question above.
- Do not execute any git command unless I ask us explicitly to do it.

## Typescript
- Avoid using `any` or `unknown` types. In case you include them in your first iterations, fix them afterward with the correct types.

## Linting
- Avoid using eslint disabler comments; instead, work on solving the types to be according to the error it shows

## React
- Any hardcoded string used in the components (such as texts or paragraphs) should be exported as a constant or enum.
  - See the shared/constants files as a reference.
  - If possible, use the enum pattern before constants.

## Tests
- All tests must be meaningful and should avoid creating too similar cases with the same structure. If possible, create ones that review more than one expected behavior or result.
- Avoid tests related to component style/CSS classes unless I explicitly ask you for them.
- When you are mocking data for testing, import it from a `mocks.json` file. Parse that JSON-formatter data in case you need to.
- After executing the test suite, always review the code executing the following scripts in this order (and work on fixing them in case it breaks):
  - First, run the builder.
  - Second, run the linter.
- In every test run I ask for, run the coverage variation of the test script and check its coverage is above `95%`. If it is below that percentage, add new tests to improve it.

## Comments
- Avoid adding comments on created or modified code unless in the following cases:
  - Is to include TSDocs type documentation in order to explain how to use it.
  - Or the logic added/modified has such complexity that it requires complementary comments to help its understanding.
  - When you create interfaces. They add comments in their attributes to improve understanding and context for other developers