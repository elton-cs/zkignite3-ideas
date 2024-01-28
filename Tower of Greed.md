# Tower of Greed: A Turn-Based Battle Royale


## Summary: 
A 5 player battle royale where players fight each other with their elemental powers to win treasure. Think pokemon mystery dungeon style except it's PvP!

## Game Mechanics:
1. Circular tile-based arena
2. Each player has 3 options:
    - Move 2 (3?) blocks in any direction (l-moves included)
    - Move 1 block and attack in any direction
    - Attack 2 times in any direction
3. A round ends after each player makes their move.
4. Every 2 rounds, random edge blocks break down, and the arena gets smaller. This forces player movement to converge or take damage.
    - Cliff-hanger Buff: Players that choose to stay in the break down zone risk falling and instantly losing if their block breaks down, 
    but in exchange, if they guess correctly, they deal 3x damage for the following 2 rounds. 
5. Two types of attacks:
    - Short range AoE: deals damage to user's surrounding. Low damage
    - Long range straight-shot: deals damage to first opponent standing in the line of fire. 
6. Last one standing wins

## Paima Specific Implementation Ideas:
1. Use NFT Projections to create a player NFT
    - Wins: number of games won
    - Losses: number of games lost
    - EXP: experience points from games played. Based on games played. Ranges from 1-5 xp depending on player rank during each game played. 
2. Use Zeko L2 to create game instances
3. Use Arbitrum/Cardano liquidity to play token prize-pool tournaments


## Token Tournaments Examples
Note: Based on the following token distribution (subject to change): 

- 1st (50%)
- 2nd (30%) 
- 3rd (10%)
- Protocol (10%)

### 1. 5 Player:
    - Entry fee: 2 mina
    - total prize pool: 10 mina
    - distribution: 5/3/1 mina for Top 3
    - protocol: 1 mina per game

### 2. 25 Player:
    - Entry fee: 10 mina
    - total prize pool: 250 mina
    - distribution: 62.5/37.5/12.5 mina for Top 3
    - protocol: 12.5 mina per game

### 3. 125 Player:
    - Entry fee: 25 mina
    - total prize pool: 3125 mina
    - distribution: 1562.5/937.5/312.5 mina for Top 3
    - protocol: 312.5 mina per game

## Different Tournament Modes:
- All or Nothing APE: Only Top 3 in any player game wins tokens. Multi level games award top 3 in the final level
- Moderation MANTIS: Top 3 of every level wins some tokens. 
- Casual CAT: Everyone wins at least 50% of their tokens back.
    - Exampe 5 man game:
        - 2 mina fee
        - 10 mina prize pool
        - 3/2/1/1/1 token distribution
        - protocol: 2 mina per game


## Free-To-Play:
- Basically the same game, but there's no token incentive for winning and there's no fee to enter a game.
- Limitation is going to be stamina:
    - Each player can only play x number of games per day. (FTP Mobile Style)
    - No tournament mode available
- Implement Tarochi style save to play with NFT. Aka, when the user wants to mint an NFT of their progress, they can do so later.


## Protocol Revenue Analysis

### 1. Pay-to-Play
Assumptions:
- Playerbase: 10,000 Monthly Active Players
- Daily active players: 10% of monthly = 1000 players
- games played per day: 1 game per player = 1000/5 = 200 games
- fee per game: 1 mina * 5 player = 5 mina

Revenues 
- per game: 10% of 5 = 0.5 mina
- per day: 0.5 * 200 = 100 mina
- per week: 100 * 7 = 700 mina
- per year: 700 * 52 = 36,400 mina


### 2. Stake-to-Play 
Assumptions:
- Free to play, players don't win tokens for games
- Playerbase: 10,000 Monthly Active Players
- Stake price: 100 mina
- stake return: 5% APR
- total staked: 10,000*100 = 1,000,000 mina

Revenues 
- per year: 5% of 1,000,000 = 50,000 mina 
- per week: year/52 = 961.5 mina
- per day: week/7 = 137.35 mina

### 3. Hybrid
Combine both models:
- 10,000 Monthly active players
- 1000 daily token tournament players

- Stake-to-play is mandatory (50,000 / year)
- 10% of users also play token tournaments (36,000 / year)
- Total revenue: 86,000 mina / year



1. Every tournament game earns some token revenue, which goes to the treasury
2. Treasury funds will be used to continue building the game as well as give more incentives to players
3. Currently thinking of doing 80/20 split of revenue
    - 80: Goes towards monthly tournaments as an additional prize pool.
    - 20: Game Dev funding





## Potential Avenues to Explore:
1. Use liquid staking and/or restaking tokens on eth to:
    - purchase the game and/or player progress NFT
    - Provide in-game incentivizes like more stamina for longer play, special game modes etc. 
2. Stake-to-play:
    - No need to purchase a game copy, instead stake a certain amount of tokens in AAVE/Compound to play the game
    - Provides a revenue stream for the game, while making the game basically free-to-play from the user's perspective.
    - Better alternative to purchasing a worthless pfp avatar based NFT
    - Stake amount can reflect the stamina in game, aka more staked = more gametime.