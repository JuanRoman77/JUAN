# QA Level-3

## Table of contents

- [QA Level-3](#qa-level-3)
  - [Table of contents](#table-of-contents)
  - [Setting up local environment](#setting-up-local-environment)
  - [Testing specific PRs](#testing-specific-prs)
    - [Checkout and run the branch in local environment](#checkout-and-run-the-branch-in-local-environment)
    - [Mobile](#mobile)
      - [App download](#app-download)
    - [Discord](#discord)
      - [Test mobile branches in local web browser](#test-mobile-branches-in-local-web-browser)
    - [Test in all mobile devices](#test-in-all-mobile-devices)
  - [Misc](#misc)
    - [Enable popups and AB tests](#enable-popups-and-ab-tests)
    - [Git Bisect Guide](#git-bisect-guide)
  - [Ranked](#ranked)
    - [Tips and tricks](#tips-and-tricks)
    - [Leaderboards testing](#leaderboards-testing)
    - [Suggest ways to optimize the QA system](#suggest-ways-to-optimize-the-qa-system)

## Setting up local environment
Follow the guide that corresponds to your operating system to have the game running on your machine:
- [Local development setup](https://github.com/colonistio/katan/blob/development/docs/welcome/developer/setup.md)

## Testing specific PRs

### Checkout and run the branch in local environment

1. In Sourcetree in the left side panel (under Remotes), right click on the branch you want to run in Local and click Checkout https://i.imgur.com/lbabmco.png
2. If a branch gets new commits after you checked it out, click Pull to update the local branch to its latest version
3. In the [Running the game](https://github.com/colonistio/katan/blob/development/docs/welcome/developer/setup.md) section of the setup document you will find the required commands to run the branch
4. Go to `http://localhost:8080` and play the game to test the branch you checked out

### Mobile

####  App download
- Download test versions: https://docs.google.com/spreadsheets/d/15aBfvX5ARH1Oxhg-gGikriDAOhiwgomSfO_x3vYvqr8/edit#gid=0
- Enable Internal App Sharing for Android: https://stackoverflow.com/questions/57478894/how-to-enable-internal-app-sharing-for-android

### Discord
- [Testing on Discord Activity](./../testing/discord-activity.md)

#### Test mobile branches in local web browser

1. Inspect Element > Go to Application > LocalStorage > localhost:8080 > add a new key > key: mVersion, value: anything
2. Go to http://localhost:8080/mobile. This will render the mobile entry point

### Test in all mobile devices
- Use [BrowserStack](./../testing/browserstack.md) to extend coverage to all mobile devices and various browser versions

## Misc

### Enable popups and AB tests

For easier and more fluid testing without popups or AB tests, edit these two lines of code to **false** before you start testing a branch in local:

- Enable ad popups: `static readonly HIDE_POPUPS_ON_DEVELOPMENT = false`
- Enable ABTests: `static readonly INACTIVATE_ABTESTS_ON_DEVELOPMENT = false`
- Trigger Patch Notes popup: https://i.imgur.com/LqReDv5.png

### Git Bisect Guide

- Steps for identifying a problematic commit using Git Bisect: [Guide](./../testing/git-bisect.md)

## Ranked

### Tips and tricks

**VPS TO WIN**
- Edit file code/shared/PremadeGameSettings.ts
- Inside function matchmakingClassic1v1()
- Set `setting.victoryPointsToWin = 1`

**PLACEMENT GAMES**
- Edit file code/shared/RankedModeData.ts
- Edit `readonly numberOfPlacementGamesNeeded = 10` for each game mode

**MATCH TIME**
- Edit file code/server/matchmaking/matchmaking_configurations/MatchmakingEngineConfigurations.ts
- Inside class Class MatchmakingEngineConfigurationsRankedClassic1v1
  - Set `readonly targetWaitTimeInSeconds = 2`
  - Set `readonly timeBeforeForceMatchingPlayersInSeconds = 4`

**GUESTS ACCESS RANKED**
- Edit file code/server/ranked/RankedController.ts
- Inside function isUserQualifiedForRankedGame()
  - Comment out line `if(!user.isLoggedIn()) throw new Error(* EnglishTexts.RANKED_ERRORS_SIGN_IN_REQUIRED)`

### Leaderboards testing

- [Leaderboards testing](./../testing/leaderboard-testing.md)

### Suggest ways to optimize the QA system

- Pending, potentially level 4 qa doc
- Description + examples
