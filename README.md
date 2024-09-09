# Pull Requests
Review code changes prior to merging them into main branches. This also links up PR details to our JIRA task cards.

This gives us an opportunity to make sure we are meeting our standards:
- Meeting task acceptance criteria
- Optimal implementation
- Unit testing
- Avoiding potential performance impacts
- Clean up debugging/testing code


## Squashing commits
More often than not, we make commits containing work-in-progress (WIP), which makes more sense for authors but not much for paper trail and reviewers.
We also rely more on the PR for the details.
This keeps our commit log clean, consistent and easier to keep track of.

Tracking benefits
`git log --all --grep='Fix:'`
`git log --all --grep='FT-123’'`

Regular merge
```
7hgf8978g9... Added new feature
85493g2458... debug logs
1h354354gh... wip, done for the week
789fdfffdf... added unit tests
9080gf6567... removed logs
2h34839843... applied review comments
```
Squashed merge
```
7hgf8978g9... new: Feature foo (FTM-123)
85493g2458... fix: Loading screen stuck (FT-234)
1h354354gh... chore: Refactored service (FT-345)
```

refs:
https://softwareengineering.stackexchange.com/a/263172


## Format
Pull requests should contain enough details to help reviewers understand the nature of the change and help them perform reviews effectively. Keeping formats consistent would also lead to better collaboration across teams (if and when the need arises).

Following this format gives way for automation in terms of creating release notes, reports, etc.
The format would also immediately inform reviewers what the change is about and contains the reference to the jira task, reducing back and forth clarifications.

Types:
- Feat - used for new features
- Update - when introducing optimizations and/or enhancements
- Fix - for bug fixes
- Chore - non functional requirements like adding unit tests, refactoring, adding readme, etc.

Subject: `<type>: <short subject/description> (<jira-code>)`

Body: 
`<optional summary/description>`
`<list of changes>`

Ex.

### Fix: Resolved loading issue in start screen (FT-123)
Changes:
- Change 1
- Change 2

Ref: `[<jira-code>](<jira-link>)`


refs:
https://www.conventionalcommits.org/en/v1.0.0/



## Benefits
- Automatically generating CHANGELOGs.
- Automatically determining a semantic version bump (based on the types of commits landed).
- Communicating the nature of changes to teammates, the public, and other stakeholders.
- Triggering build and publish processes.
- Making it easier for people to contribute to your projects, by allowing them to explore a more structured commit history.
