# Name Ideas:
- [ ] SportSlot
- [ ] SportsLot
- [ ] SportsPlay
- [ ] ChipMunk (chipmunk holding chips)
- [ ] SportsBet.pizza
- [ ] SportsPlay.pizza
- [ ] Team Player
- [ ] SportsPlay.club ($20/year)
- [ ] Apples.pizza
- [x] **SliceIt.pizza**


# Logo Ideas:
- [ ] Dice with sport icons
- [ ] Viking Pirate
- [ ] Coins with sport icon
- [ ] Currency sign with ball in center
- [ ] Betting chip with sports
- [ ] Pizza Slices

# Odds Multiplier
| Wins In Week   | Multiplier |
| -------------- | ---------- |
| 16             | 50.0       |
| 15             | 25.0       |
| 14             | 20.0       |
| 13             | 15.0       |
| 12             | 10.0       |
| 11             | 5.0        |
| 10             | 4.0        |
| 9              | 3.5        |
| 8              | 3.0        |
| 7              | 2.5        |
| 6              | 2.0        |
| 5              | 1.8        |
| 4              | 1.6        |
| 3              | 1.4        |
| 2              | 1.2        |
| 1              | 1.0        |
# Wikia for Team Player
# Directions: Go to Wiki Tab to view Pages
# Organized by Sprints

# Rough Draft Of Models
## User
- [ ] ID (object ID)
- [ ] Name (STR)
- [ ] Email (email)
- [ ] Username (STR)
- [ ] Password (STR)
- [ ] PizzaSlicesTotal (INT)
- [ ] PizzaSlicesWeekly (INT) (resets to 200 every week)
- [ ] Wins (INT)
- [ ] Loses (INT)
- [ ] Favorite Teams (Array(Object)) (Team Reference)
- [ ] Friends (Array(Object)) (User Reference)
- [ ] Leagues (Array(Object)) (League Reference)
- [ ] Bets (Array(Object)) (Bet Reference)
- [ ] GlobalRank (INT)
- [ ] Permissions (INT)
- [ ] Commends (INT)
- [ ] Reports (INT)
- [ ] Badge (STR)
- [ ] Achievements (Array(STR))
- [ ] Comments (Array(Object)) (Comment Reference)

## Game Thread
- [ ] ID (object ID)
- [ ] Week (INT)
- [ ] HomeTeam (Object) (Team Reference)
- [ ] AwayTeam (Object) (Team Reference)
- [ ] Bets (Array(Object)) (Bet Reference)
- [ ] Winner (Object)
- [ ] IsFinished (Boolean) 
- [ ] Comments (Array(Object)) (Comment Reference)

## Bet
- [ ] ID (object ID)
- [ ] Owner (Object) (User Reference)
- [ ] OnGame (Object) (Game Thread Reference)
- [ ] TeamBetOn (Object) (Team Reference)
- [ ] SlicesBet (INT)

## Team
- [ ] ID (object ID)
- [ ] Name (STR)
- [ ] Wins (INT)
- [ ] Losses (INT)
- [ ] Draws (INT)

## League
- [ ] ID (object ID)
- [ ] Name (STR)
- [ ] Members (Array(Object)) (User Reference)
- [ ] IsActive (Boolean)
- [ ] Ranking (Array(Object)) (User Reference) (Ordered Descending)

## Comment
- [ ] ID (object ID)
- [ ] Owner (Object) (User Reference)
- [ ] Comments (Array) (Comment Reference)

## Formula
- `correctBets : Number of bets guessed correctly by user`
- `slicesBetted : Amout of slices betted on a game`
- `slicesWon : Total amount of slices won all together from all games won`
- `multiplier: Amount from the multiplier table`
- `totalSlices : Total slices won after multiplier has been applied`
> slicesWon = 2(slicesBetted) SIGMA correctBets
----------------------------------------------------
> totalSlices = slicesWon x multiplier
----------------------------------------------------

## API Endpoints
--------------------------------------------------------------------------------
**GET**
- `GET /users -> Reads all users`
- `GET /users/:id -> Read user based off id`
- `GET /users/:id/bets -> Reads all bets made by user based off ID`
- `GET /gamethreads -> Reads all game threads`
- `GET /gamethreads/:id -> Read game thread based off id`
- `GET /gamethreads/:id/bets -> Read all bets made on a game thread based off ID`
- `GET /bets -> Reads all bets (caution)`
- `GET /bets/:id -> Read bet based off id`
- `GET /teams -> Reads all teams`
- `GET /teams/:id -> Read team based off id`
- `GET /leagues -> Reads all leagues`
- `GET /leagues/:id -> Read leagues based off id`
-------------------------------------------------------------------------------
**POST**
- `POST /users -> Creates a user. Requires a req.body`
- `POST /gamethreads -> Creates a gamethread. Requires a req.body`
- `POST /bets -> Creates a bet. Requires a req.body`
- `POST /teams -> Creates a team. Requires a req.body`
- `POST /leagues -> Create a league`
- `POST /signup -> signup`
- `POST /login -> login`
-------------------------------------------------------------------------------- 
**PATCH**
- `PATCH /users/:id -> Updates a user based off id`
- `PATCH /gamethreads/:id -> Updates a gamethread based off id`
- `PATCH /bets/:id -> Updates a bet based off id`
- `PATCH /teams/:id -> Updates a team based off id`
- `PATCH /leagues/:id -> Updates a league based off id`
--------------------------------------------------------------------------------
**DELETE**
- `DELETE /users/:id -> Deletes a user based off id`
- `DELETE /gamethreads/:id -> Deletes a gamethread based off id`
- `DELETE /bets/:id -> Deletes a bet based off id`
- `DELETE /teams/:id -> Deletes a team based off id`
- `DELETE /leagues/:id -> Deletes a league based off id`
--------------------------------------------------------------------------------

**RETRIEVAL OF DATA**
- First NFL game of a week is on a thursday night.
- Last NFL game of a week is on a monday night.
- Majority of NFL games happen on a sunday.
- Some NFL games happen around saturday, 
- On a thanksgiving thursday, more NFL games occur.
