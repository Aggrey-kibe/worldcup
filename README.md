# World Cup Database

A freeCodeCamp Relational Database certification project. It builds a PostgreSQL database from the results of the final three rounds of the World Cup tournaments since 2014, loads the data with a Bash script, and answers questions about it with SQL queries.

## Files

- `worldcup.sql`: a dump of the `worldcup` database.
- `insert_data.sh`: reads `games.csv` and inserts the teams and games into the database.
- `queries.sh`: prints answers to a set of questions about the data.

## Database structure

- `teams`: `team_id` (primary key), `name` (unique, not null)
- `games`: `game_id` (primary key), `year`, `round`, `winner_id` (foreign key to `teams`), `opponent_id` (foreign key to `teams`), `winner_goals`, `opponent_goals`. All columns are `NOT NULL`.

## Usage

Load the data (this empties the tables first, then inserts 24 teams and 32 games):

```bash
./insert_data.sh
```

Run the queries:

```bash
./queries.sh
```

The queries cover total and average goals, the most goals in one game, the 2018 winner, the teams in the 2014 Eighth-Final round, every winning team, the champions by year, and the teams whose names start with `Co`.

## Restoring the database

```bash
psql -U postgres < worldcup.sql
```

## Requirements

- PostgreSQL, with a `freecodecamp` user
- Bash
- `games.csv` in the same folder as `insert_data.sh`
