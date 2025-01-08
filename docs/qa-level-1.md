# QA Level-1

## Table of contents

- [QA Level-1](#qa-level-1)
  - [Table of contents](#table-of-contents)
  - [Development cycle](#development-cycle)
  - [Testing development and staging](#testing-development-and-staging)
  - [Testing production](#testing-production)
  - [QA Team Games](#qa-team-games)
    - [Development Game](#development-game)
    - [Staging Game](#staging-game)
  - [What to do when you find a bug](#what-to-do-when-you-find-a-bug)
    - [Check if it is already reported](#check-if-it-is-already-reported)
  - [Reporting bugs](#reporting-bugs)
    - [Handling User-Reported Bugs](#handling-user-reported-bugs)
    - [Reviewing reports](#reviewing-reports)
  - [Misc](#misc)
    - [What to do when you find a UI issue](#what-to-do-when-you-find-a-ui-issue)
    - [What to do when you find a UX issue](#what-to-do-when-you-find-a-ux-issue)
    - [Identify problems](#identify-problems)
    - [Useful links](#useful-links)

## Development cycle

A new version of the game goes live to production (Colonist.io) every week on Tuesday (check [Patch Notes](https://colonist.io/patch-notes) and [Product Cycle](./../company/schedule.md))

1. Every cycle we test open Pull Requests (PRs) that will be merged into the `development` branch
2. 24 hours before release, the new `staging` version is created and deployed to a test server: https://hexs.io
3. All PRs need to be tested, approved, and merged into `development` before `staging` is created; otherwise, they won't make it into the next version
4. The new `staging` branch is tested in hexs.io, along with all previously merged PRs. New PRs merged directly into `staging` are also tested
5. On Tuesday, when the cycle ends, the new version is deployed to production (Colonist.io), at which point we assess the overall stability of [Colonist](https://colonist.io/) by conducting smoke testing


## Testing development and staging

- `development` branch: Conduct regular smoke testing on the `development` branch (always live on onlinecatan.com), focusing on recently merged PRs to ensure everything works as expected

- `staging` branch: When a new version of the game is created ([example PR](https://github.com/colonistio/katan/pull/10186)) and deployed to hexs.io, conduct regression testing focusing on the PRs that were merged that version
  - Compiled list of PRs merged into `staging` (previously tested in `development`) that should be re-tested, can be found in the version thread, inside the [development category](https://discord.com/channels/605233308577562643/731686966613114891) in Discord. It can also be found in Github searching for PRs with the following titles: `v172 development -> staging` and `v172 staging -> development (2)`, in the [Closed Pull requests list](https://github.com/colonistio/katan/pulls?q=is%3Apr+is%3Aclosed)
- Conduct web, mobile and Discord regression following the [Regression Testing Checklists](./../testing//regression-testing-checklist.md) and [Smoke Testing Checklists](./../testing//smoke-testing-checklist.md)

## Testing production

After the production release, check the things that players are unlikely to report:
- All ads are working
- Paid features work only with a subscription
- It is impossible to get a subscription for free
- Hidden features that are not yet published (toggled off) are unavailable

## QA Team Games
QA Games are designed to more effectively find bugs in the development and staging versions:
### Development Game
- Development Game takes place every Monday
- We are focus on PRs that have already been merged into the development branch
- After the game, conduct [smoke testing](./../testing//smoke-testing-checklist.md) of the parts affected by PRs outside the game
### Staging Game
- Staging Game takes place every Tuesday
- The game focuses on all PRs that have made it to staging, including those tested in development, to ensure they work correctly together
- After the game, conduct [regression testing](./../testing//regression-testing-checklist.md) of the parts affected by PRs outside the game

## What to do when you find a bug

- Check if the bug exists in [Colonist.io](https://colonist.io/)
- Check [testing FAQ](./../testing//faq.md) to verify if it's in fact a bug or expected behavior

### Check if it is already reported

If the bug exists on `development`, `staging`, or production, do the following before reporting it:

- Check if it has been reported in [QA #bug-reports Discord channel](https://discord.com/channels/605233308577562643/1037508743375638608)
- Check if there is an issue to fix the bug: https://github.com/colonistio/katan/issues 

If you are not sure if something is a bug or a feature, ask another tester. If still unsure, ask your manager

## Reporting bugs

1. If the bug exists on `development`, `staging`, or `production`:
  - Create a GitHub issue (every single bug must have an issue, no exceptions).
  - Add the corresponding labels.
  - Add the issue to an appropriate Project.
  - If the issue doesn't fit any existing Projects:
    - Consider if it might require a new project that will be relevant for a long time (e.g., Web, Mobile, Discord, SEO).
    - If you decide that a new project is needed, create a thread in QA, explain why the new project is necessary, and link the issue.
    - Tag Demi for approval
   - Specify in the issue where the bug was found (development/staging/production).
   - Add this bug to the [Bug Tracking](https://docs.google.com/spreadsheets/d/1qGUr-B1fbxo4N3wK_bdP6zNfS37AOy6rcwl2zS3pOrk/edit?usp=sharing) list.
   - DM or tag the developer of the previous PR and DM the lead of the project to align expectations on a fix.
2. If the bug is in an open PR
- [Request changes](https://i.imgur.com/QtknB3N.png), and post the bug description and screenshot in the PR

### Handling User-Reported Bugs

- **Support Tickets**: When users report bugs, Support tags QA in [#Sup-Tickets Channel](https://discord.com/channels/1245213425399762985/1254058615086649438)
  - If the bug is confirmed, create an issue

- **Bugs Thread**: Users also post bugs in the [#Bugs Channel](https://discord.com/channels/605233308577562643/631340849975787520)
  - Review these reports
  - If the bug is confirmed, create an issue

### Reviewing reports

As part of the Quality Assurance team, you are expected to help other QAs adhere to high bug reporting standards.
- All Github issues created, should be reviewed by the rest of the QAs to collaborate on improving their quality
- The goal is to review the validity & accuracy of each submission, without re-testing the PR
- Open a thread to give feedback or discuss a report, or simply react with 👍🏼 if everything looks fine  

## Misc


### What to do when you find a UI issue
1. Open the console in the browser or Discord and download the logs
2. Add the logs to the created issue 

### What to do when you find a UX issue

Some features will have UX problems
1. If it is an obvious problem, contact the project lead or report it as a bug
2. If it is not an obvious problem, create a thread in the [QA #bug-reports Discord channel](https://discord.com/channels/605233308577562643/1037508743375638608) to suggest an improvement

### Identify problems

While testing, you are expected to identify areas for improvement. These many deviate from just having the product work. It could be a problem from multiple areas such as algorithms, user experience, animations, text, features, or anything else. Share these problems in the [QA #bug-reports Discord channel](https://discord.com/channels/605233308577562643/1037508743375638608)

### Useful links

- [Multi session Chrome extension](https://chrome.google.com/webstore/detail/sessionbox-multi-login-to/megbklhjamjbcafknkgmokldgolkdfig?hl=en)
- Screenshots: https://flameshot.org/
- Screen video recording: [Loom](./../welcome/how-to-use-loom.md)
- [Ad testing](./../testing/ad-testing.md)
