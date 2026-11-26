# Systems Support Labs

Hamdi’s hands-on portfolio of IT support and systems administration exercises. Each completed lab follows a support ticket from the first report through diagnosis, verification and handover. All scenarios use a personal lab environment.

## Lab index

| Lab | Skills | Status | Evidence |
| --- | --- | --- | --- |
| [001 · Investigate a Windows DNS fault](labs/001-windows-dns/README.md) | Windows, PowerShell, DNS, ticket notes | Completed | [DNS fault and successful TCP check](labs/001-windows-dns/evidence/03-dns-fault.png) |

## Next exercises

- **Windows account access** — use a test account to investigate a failed sign-in and verify restored access.
- **Linux permissions** — diagnose why a test user cannot read a shared file and verify the fix as that user.
- **PowerShell reporting** — build a read-only disk-space report and check its results against a manual query.

## Add a lab

1. From the repository root, run the PowerShell commands below. Choose the next number and a descriptive folder name.
2. Edit the new README and add a row to the index marked **Planned**. Switch to **In progress** when you start the exercise.
3. Save redacted screenshots or short output excerpts alongside the write-up. Use relative links and captions that explain what each item proves.
4. When the verification steps pass, mark the lab **Completed** and link its strongest evidence in the index. For LinkedIn, share the GitHub link directly to the completed lab.

```powershell
$lab = "labs/002-windows-account-access"
New-Item -ItemType Directory -Path $lab
Copy-Item templates/lab.md "$lab/README.md"
```
