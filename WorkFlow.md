
---

 Bash Logic Cheat Sheet
For DevOps, Automation, and Smart Scripting

🔗 Command Chaining

| Symbol | Behavior | Example | Use Case |
|--------|----------|---------|----------|
| ; | Run both commands, regardless of success | cmd1 ; cmd2 | Setup + cleanup |
| && | Run second only if first succeeds | rm file && echo "Deleted" | Safe automation |
| || | Run second only if first fails | rm file || echo "Missing" | Error fallback |
| && ... || ... | Combine success and failure logic | rm file && echo "OK" || echo "Fail" | Logging outcomes |

---

 Output Redirection

| Symbol | Meaning | Example | Notes |
|--------|--------|---------|-------|
| > | Overwrite file | echo "Hi" > file.txt | Creates or replaces |
| >> | Append to file | echo "Hi" >> file.txt | Adds to existing |
| 2> | Redirect errors | cmd 2> error.log | Captures stderr |
| &> | Redirect all output | cmd &> all.log | stdout + stderr |

---

🔄 Pipes and Filters

| Symbol | Meaning | Example | Use Case |
|--------|--------|---------|----------|
| | | Pass output to next command | ls | grep txt | Filter results |
| xargs | Convert input to arguments | cat list.txt | xargs rm | Batch actions |
| tee | Output to file and screen | cmd | tee log.txt | Logging + visibility |

---

 Inline Conditionals

`bash
command && echo "Success" || echo "Failure"
`

Or full block:

`bash
if command; then
  echo "Success"
else
  echo "Failure"
fi
`

---

 DevOps Scripting Snippet

`bash

!/bin/bash
LOG="deploy.log"
rm old_config && echo "Old config removed" >> $LOG || echo "No config found" >> $LOG
echo "Starting deployment..." | tee -a $LOG
`

This shows chaining, redirection, and logging—all in one clean snippet.

---

 Badge for Your README

`markdown
!Bash Logic Mastery
`

---

