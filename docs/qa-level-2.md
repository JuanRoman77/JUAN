# QA Level-2

## Table of contents

- [QA Level-2](#qa-level-2)
  - [Table of contents](#table-of-contents)
  - [Testing specific PRs](#testing-specific-prs)
    - [Testing open branches](#testing-open-branches)
    - [PR is already merged](#pr-is-already-merged)
  - [What to do when you find a bug](#what-to-do-when-you-find-a-bug)
    - [Update your environment](#update-your-environment)
    - [Check other environments](#check-other-environments)
  - [Approving PRs](#approving-prs)
  - [After testing](#after-testing)
    - [Test cases](#test-cases)
  - [Misc](#misc)
    - [Tips](#tips)
    - [Useful links](#useful-links)

## Testing specific PRs

- You will be added as [Reviewer](https://i.imgur.com/0UjzJEH.png) in different PRs. Also add yourself, be proactive
- All PRs need to be tested within 24 hours of creation
- Always check [Discord and Github notifications]([https://i.imgur.com/mTVGKOr.png](https://github.com/colonistio/katan/blob/development/docs/welcome/how-to-use-discord-and-github.md#notifications))

### Testing open branches
- Read [this](../welcome/test-deployments.md) 
- Under each PR, there is a "Click to deploy PR" link
- Clicking it will open `deploy.katan.io`, and the PR will be automatically deployed to one of the 10 test servers
- Deployment typically takes around 10 seconds
- Stop the server after you're done so others can use it
- `development` branch will automatically get deployed into onlinecatan.com every time a new branch gets merged
- `staging` branch will automatically get deployed into hexs.io every time it gets an update

Tips:
- Hover over the Patch Notes number in the footer to see what branch has been deployed to the test server. [Example](https://i.imgur.com/TWsFpg8.png)  
- Always review issues attached to PRs for edge cases, design, etc., to avoid missing details during testing
- Do not test Draft PRs unless otherwise instructed  
- Do no test PRs with merge conflicts until they are resolved
- In case conflict is only on `PatchNoteData.ts` you may resolve them by following [these steps](https://www.loom.com/share/e0bcb7b2544c44dda58f761918564b4b?sid=1ae4c90b-73cf-4577-9549-f90129ffc985). Make sure you double click on the line you need to delete so it's fully removed (no trailing spaces nor empty lines)  
- You can test any PR on staging environment posting the command `/deploy-staging` in PR comments. Avoid using this command unless absolutely necessary
- **Never deploy to staging right after a new version of staging has been created**

### PR is already merged

PRs that have been merged into a main PR, also known as sub-PRs ([example](https://i.imgur.com/v4AyEtP.png)), should be tested directly through the main PR. If that main PR has been merged into `development`, test the feature in `development` branch (onlinecatan.com). If `development` has been merged into `staging`, test in `staging` branch (hexs.io)  
Keep in mind that some test cases might be added into a sub-pr and not into the main one, so make sure to check for sub-prs. [Example](https://github.com/colonistio/katan/pull/13914)
## What to do when you find a bug

### Update your environment

Some bugs are only present in your device. To make sure your environment is stable:

- Pull the latest version of the branch
- Delete the branch from local and checkout again from origin

### Check other environments

Some bugs are live in other environments as well

- Check bug on [Colonist.io](https://colonist.io/)
- If the bug is live in `development` or `staging`, track down the merged PR which introduced it

## Approving PRs

If everything is working as expected in every affected platform, you should approve the PR

- If it's open, [mark as Approved](https://i.imgur.com/RE1pgfb.png) if you don't find any bugs, or if the bug you reported was successfully fixed
- If the PR has already been merged, post the word "Approved" in a comment

## After testing

- Hide the comment used to deploy a branch to test server, and mark it as outdated: https://imgur.com/a/avTJi7y  
- Comment on the PR which cases you tested: [example](https://github.com/colonistio/katan/pull/13655#issuecomment-1787747672)
  - If you didn't test the PR, check the test cases posted by other QAs, and add untested cases into the PR body (if any)
 
### Test cases

- Test everything the developer mentioned in the PR -> QA not meeting expectations
- Come up with additional test cases, covering all edge cases -> QA meeting expectations
- Introduce new testing processes and tools to increase the efficiency of the system -> QA exceeding expectations

## Misc

### Tips 
- You can test production, staging, and development branches by deploying them via `deploy.katan.io`. This will allow you to use in game commands
- You can modify code in specific PRs for testing without creating separate PRs. Simply copy the branch, make the changes, and deploy via `deploy.katan.io`

### Useful links

- [In-game commands](./../welcome/in-game-commands.md)
- [FAQ & Test credit card info](https://github.com/colonistio/katan/blob/development/docs/misc/faq.md)
- [API testing](./../testing/api-testing.md)
- [Deleting/manipulating Google account](https://www.loom.com/share/96056ce7c0fa40d8b252d3d37cd60e7e)
- [UI testing](./../testing/ui-testing.md)
- [UI browser tests](./../testing/ui-browser-tests.md)
