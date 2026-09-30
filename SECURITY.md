# Security policy

## Reporting a vulnerability

Please report security issues **privately**, not in a public issue:

- through GitHub's private vulnerability reporting ("Report a vulnerability" on the affected repository's Security tab), or
- by email to gxcsoccer@gmail.com.

Include what you found, how to reproduce it, and which repository and version it affects. You will get an answer within a week. Please give us a reasonable time to fix the issue before disclosing it.

## Supported versions

Only the latest release of each repository (and its `main` branch) receives security fixes.

## Scope and safety model

DeskMind operates the user's own Mac, so the following count as security issues:

- **hands** (the desktop harness) doing anything outside what the user asked for and confirmed: touching files outside the attached folder, operating apps the request did not name, sending, deleting, paying or publishing without the approval step, or typing into a window other than the intended one.
- **app** leaking what it sees: screenshots, recordings, window contents or typed text leaving the machine. Models run locally; nothing is sent to a server unless the user configures a remote model.
- **brain / eyes** servers accepting connections from anything other than localhost by default.
- Any way to make the app or its helper run code or read data it was not built to, including through a crafted task, web page or document it looks at (prompt injection that leads to such actions included).

Bugs in the models' judgement (a wrong click, a missed step) are not security issues unless they bypass the safeguards above; please file those as ordinary issues.
