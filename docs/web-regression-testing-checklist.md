### Web Regression Testing Checklist

Test the following in Web (Chrome, Safari, Firefox). Use BrowserStack to test older browser versions.

## Accounts
- Login/logout of a User account
  - Using different providers (Google, Apple, Discord)
  - From different pages (Home, Leaderboard, Store)
  - Same account, multiple tabs
- Creating new User accounts
  - Using different providers
- Creating Guest accounts
  - New guest account created on fresh page load
  - New guest account created when logging out of User account
- Linking/unlinking providers (Google/Discord/Apple)
  - One linked provider minimum
  - Changing to another account on the same provider
- Changing region
  - Displaying changes on the leaderboard
  - Re-selecting the region
- Deleting account
  - Linking provider from deleted account
  - Login back to deleted account

## Game creation
- Starting and finishing games of all types (Play vs Bots, Ranked, Unranked, Room)
  - Using the different available buttons (landing page, home, leaderboards)
- Creating rooms
  - Other players can see/join the room
  - Adding/kicking bots and players
  - Sharing link
- Bots play the game successfully
  - Game doesn't break when timers run out 
  - Verify the bots correct behavior checking these [test cases](./../testing//bots-smoke-testing.md)

## Store
- Purchasing coins, items, Memberships
  - Monthly vs annual
- Upgrading/downgrading/canceling Memberships
- Store access points
  - Homepage links, Popups, "remove ads" and other CTAs 
- All types `/giftmembership`
  - Activating
  - Cancel before/after activating
  - Deleting account before/after activating

## Ads
- Ranked game video ads load & play when queueing
- Lobby ads
- In-game banner ads
- Adblock on/off
  - Cannot launch ranked games with adblock on
  - Internal banner ads appear

## Ranked/unranked
- Matchmaking queue
- Placement games
  - Rank change animation and Rating gain/loss is shown upon completing placements
  - End game screen shows rank change animation
- Leaderboards (all game modes + all tabs)

## Profile
- Data being saved and updated correctly in #history
- Username/avatar/default color change
- Friends
  - Adding, removing, leaderboards

## Room
- Check that rooms with different settings can be created
- Try starting games with maps/modes you don't own
- Confirm a subscription allows selecting premium modes and maps
- Check Share room link feature
- Check room settings fields (appearance, switching, changing game settings)
- Check adding bots (medium and easy)
- Check kicking bots
- Web players can view room created on mobile and can join
- Check adding and kicking players
  - Try going back to lobby after kick
- Check name change in the room
- Verify sent messages are visible to other players

## Game
- Running out of time does not break bot behavior
- Settings menu is functional
- Can pause game
- Can view rule book
- 1v1 ranked/casual matches start
- C&K/Seafarers matches start
- Game info displays correctly
- Disconnect/reconnect works, game is lost if only player
- Confirm end game screen buttons function correctly
- Check if games are displayed in the web history
- Check the game chat, game log, keyboard opening

## Sharing image
- Check different combinations of game modes to make sure they look correct and work correctly
- Picture should clearly show the end of the game
- "The winner is" should be correctly shown for images
- Rapid clicking of "share" should have no issues
- All types of wins should be correctly displayed on the map

## Replay
- Replay opens through end game screen, shared link, and profile history
- Changing perspectives works for Members and shows error popup for free users of all types
- Game chat remains static in Replay, and works for players after the game ends
- Replay buttons and scroll bar work properly
- Longest Road, Largest Army, and Monopoly icons show on scroll bar
- Replay window resizes properly, on manual resize or full screen button
- All game mechanics display properly. E.g. uncovering fog tiles, ship placement/removal, etc..

## Gift Memberships
- Gift by username or link
- Gifting and receiving gift shouldn’t work for non logged in users
- Gift Monthly/Annual Memberships of any tier
- User icon appears correctly when typing a valid recipient username
-`https://{environment}.io/store#gift` is accesible
- Gift link URLs can only be redeemed once
- Verify error popups on visiting wrong gift URL and already redeemed URL
- Gift buttons appear in in-game player dropdown, friends list, & player profile dropdown, allowing to gift to that player
- Appropriate notifications are received by both gifter and gifted users
  

