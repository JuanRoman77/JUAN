### Functional Testing Checklist

#### Accounts

1. Creating Guest accounts
    - Entering the site for the first time will create a random Guest account, with 0/0 karma
    - Displayed name has a # at the end, followed by 4 numbers
    - The account has a coin balance of 0
    - All menu items, except "More Avatars," open a login window
    - "More Avatars" opens the store and auto-scrolls to the avatars section
    - Any attempt to make purchases in the store opens a login window
    - When selecting a game with bots, the game with bots starts
    - When selecting "Play Online," a screen for game selection opens
    - When attempting to play a ranked game, a warning appears: "Play 5 more games to unlock Ranked games!"
    - After winning 5 games and attempting to play a ranked game, it suggests logging in to play ranked (mb add information that progress will be saved?)
    - After logging in, guest progress is saved, and it's possible to play ranked games (if the guest has played 5)

2. Creating a new account
    - User is successfully logged in
    - Become a Member popup shows up
    - The account is assigned a random username, and 0/0 karma
    - The username can be changed once for free
    - There are no active Memberships or purchases of any kind in that account
    - In the Account tab, in /profile, the account linked to the login is displayed while others are not linked
    - The account has a coin balance of 0
    - The game history within the account is empty
    - The friend list within the account is empty
    - When attempting to play a ranked game, a popup appears: "Play 5 more games to unlock Ranked games!"
    - All paid features (modes, maps, colors) are locked and require to purchase a Membership

3. Logging in/out
    - User is successfully logged in
    - Username and karma are correct
    - Previously made purchases are preserved
    - Coins balance is accurate
    - Active subscription is reflected correctly
    - Game history within the account is accurate
    - Friend list within the account is correct
    - Logging out will create a Guest account

4. Linking/unlinking
    - When adding an account with the same email, the account is added to the profile
    - When adding an account with a different email, an error occurs: "This account is already linked to another Colonist user"

5. Game creation
    - Starting games of all types
    - When clicking "Play," a window for selecting the game type appears
    - Unranked 4P and Unranked 1v1 games start under any conditions
    - Ranked 4P and Ranked 1v1 games only work under the following conditions:
    - The user is logged in
    - The user has played 5 Unranked games
    - Ranked Cities & Knights game only works under the following conditions:
    - The user is logged in
    - The user has played 5 Unranked games
    - The user has an active subscription (plus, premium, or elite)
    - Once these conditions are met, the game search begins, followed by the game opening

6. Creating rooms
    - When clicking "Create Room," a room is created
    - Bot addition buttons work
    - Choosing game modes changes the map selection field
    - With a Membership, all filters work, but "Private Game" and "No Trolls" cannot be selected simultaneously
    - Without a Membership, if one or more participants in the room have premium modes or maps, the game cannot be started
    - All tooltips work and display information correctly
    - A link to the room can be copied and pasted
    - When entering a room from another account, all information is displayed correctly on both accounts
    - The "I'm ready" button changes the readiness status, and this status is correctly displayed to all players in the room
    - If one or more players are not ready, the game cannot be started. A notification "Username is not ready to play" is displayed
    - Only the host has control over the room
    - The host can kick players
    - Kicking a player removes them from the room
    - After being kicked, there is no way to re-join the room

8. Store
    - Purchasing coins, items, and Memberships should lead to checkout
    - After checkout, the purchase should be displayed in the profile
    - When purchasing different types of Memberships, ensure that they enable the functions described
    - Ensure that the purchased amount of coins is correctly displayed in the profile
    - When purchasing items for coins, the correct amount of coins should be deducted
    - Ensure that the purchased item for coins is available for use

9. Upgrading/downgrading/canceling Memberships
    - Upgrading/downgrading/canceling Memberships should lead to the Membership management portal
    - After upgrading, all functions described in the new acquired Membership should appear in the profile
    - After downgrading, the old functions should work until the current subscription expires. After expiration, the functions should work according to the new Membership
    - After canceling, the old functions should work until the current subscription expires. After expiration, there should be no remaining paid functions

10. Game mode mechanics
    - Special Build Phase
    - Gold tiles
    - Fog tiles
    - Foreign Land
    - Barbarian tracker
