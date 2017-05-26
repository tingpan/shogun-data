# shogun-data

Datasets for the shogun project

## Overview

The dataset used in this project is from NBA [official stats website](http://stats.nba.com/players/).  `description.json` lists the description of every field in the dataset. The dataset includes player stats and team stats, and both of them have different of categories, which are explained in the Categories Section.

## Sample data

Sample data is placed in `./data` directory and the structure of dir is:

```
- data
- dashboard
- 2015-16(season name)
- 2015-16_defense_dashboard.json()
- 2015-16_general_dashboard.json
- 2015-16_play_types_dashboard.json
- 2015-16_shot_dashboard.json
- gamelog.json
```

Each file has a different data type:

* `2015-16_defense_dashboard.json` has all defense associated stats (/players/defense-*/)
* `2015-16_general_dashboard.json` has traditional, advanced, usage, scoring and misc stats.
* `2015-16_play_types_dashboard.json` has player play type stats.
* `2015-16_shot_dashboard.json` has all shooting stats.

These dashboard files have the below tructure:

```json
{
	"PlayerID":
	{
		"Category": {
			"SubCategory": {
				"Sub..SubCategory":"value"
			}
		}
	}
}
```

The `gamelog.json` shows team stats of every game:

```javascript
{
	"SEASON_ID":"22015",
	"TEAM_ID":1610612765,
	"TEAM_ABBREVIATION":"DET",
	"TEAM_NAME":"Detroit Pistons",
	"GAME_ID":"0021500391",
	"GAME_DATE":"2015-12-18",
	"MATCHUP":"DET @ CHI",
	"WL":"W",
	//... and other traditional stats of team such as assists and rebounds.
}
```

## Categories

Each categories has a detailed page on the official website and can be visited in the link http://stats.nba.com/ATTRIBUTE_NAME
Team stats structure is the same with player stats. The only difference is team stats path start with 'team' while player stats path with 'player'. 

* /players/traditional/
	* Traditional basic stats of players, such as points, assists, and rebounds. 
* /players/advanced/
	* Advanced stats of players, which gives a more comprehensive view of players' ability. For example, Traditional Stats may not indicate if a player is a good scorer, but True Shooting Percentage of Advanced Stats could.
* /players/misc/
	* Some miscellaneous stats.
* /players/scoring/
	* Stats that measure players' scoring efficiency.
* /players/usage/
	* Stats that show how much time one player is controlling the ball.
* /players/opponent/
	* Stats that show opponent's performance.
* /players/defense/
	* Stats that measure players' defense efficiency.
* /players/clutch-traditional/
	* Similar to the Traditional Stats, but only include the stats during last minutes of the game.
* /players/clutch-advanced/
	* Similar to Advanced Stats, but only include stats during last minutes of the game.
* /players/clutch-misc/
	* Similar to Misc Stats, but only include stats during last minutes of the game.
* /players/clutch-scoring/
	* Similar to Scoring Stats, but only include stats during last minutes of the game.
* /players/clutch-usage/
	* Similar to Usage Stats, but only include stats during last minutes of the game.
* /players/clutch-opponent/
	* Similar to Opponent Stats, but only include stats during last minutes of the game.
* /players/defense/ shows detailed defense stats of the players in different areas
	* /players/defense-dash-overall/
	* /players/defense-dash-3pt/
	* /players/defense-dash-2pt/
	* /players/defense-dash-lt6/
	* /players/defense-dash-lt10/
	* /players/defense-dash-gt15/
	* /players/opponent-shooting/
* Play Type Statistics go beyond the play-by-play section of the box score and break down what happened on each play to produce the end result. This shows the frequency and efficiency of player when performing each play type.
	* /players/isolation/
	* /players/transition/
	* /players/isolation/
	* /players/ball-handler/
	* /players/roll-man/
	* /players/post-up/
	* /players/spot-up/
	* /players/hand-off/
	* /players/cut/
	* /players/off-screen/
	* /players/putbacks/
	* /players/playtype-misc/
	* /players/catch-shoot/
	* /players/defensive-impact/
	* /players/drives/
	* /players/passing/
	* /players/touches/
	* /players/pullup/
* Rebounding performance of player:
	* /players/rebounding/
	* /players/offensive-rebounding/
	* /players/defensive-rebounding/
* Player shooting frequency and efficiency stats.
	* /players/shooting-efficiency/
	* /players/speed-distance/
	* /players/elbow-touch/
	* /players/post-touch/
	* /players/paint-touch/
	* /players/shots-general/
	* /players/shots-shotclock/
	* /players/shots-dribbles/
	* /players/shots-touch-time/
	* /players/shots-closest-defender/
	* /players/shots-closest-defender-10/
	* /players/shooting/
