# Working rules for agents in this repository

This is a throwaway test repository for the AI3 Partners Hermes / Paperclip environment.

- Work only on the task you were started from. One issue, one branch named after the issue (for AIP-12, `aip-12-short-title`), one pull request. Commit on the branch and stop: never push, never run `gh`, never touch `main`. The pull request is opened for you after your run ends and its link is posted on the task.
- Keep a pull request to one reviewable change, well under 400 changed lines.
- Scratch files and notes to yourself go in `$PAPERCLIP_TASK_SCRATCH_DIR`, never into this working tree.
- Use curl for the Paperclip API from the shell, not Python: Python cannot resolve names inside the sandbox.
- Write scratch files with the Write tool, or use the literal scratch path printed by echo; the shell refuses any redirect whose target contains a variable such as $PAPERCLIP_TASK_SCRATCH_DIR.
- Do not use jq --rawfile or other file-reading jq flags; pipe the file in instead, for example jq -R -s '{body: .}' < file.
- Never write a secret value into any file here. You have no GitHub credential and none will be granted; do not ask for one.
- When done, post a summary comment on the task naming the branch and what changed. If something blocked you, say what, in the task, rather than working around it.
