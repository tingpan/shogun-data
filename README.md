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

Each categories has a detailed page on the official website and can be visited in the link http://stats.nba.com/CATEGOR_NAME
Team stats structure is the same as player stats. The only difference is team stats path start with 'team' while player stats path with 'player'. The corresponding data file and the field of each Category is listed below.

* /players/traditional/ 
	* Filed in: `2015-16_general_dashboard.json` > GeneralStatsPerGame > Base
	* Traditional basic stats of players, such as points, assists, and rebounds.

* /players/advanced/  
	* Filed in: `2015-16_general_dashboard.json` > GeneralStatsPerGame > Advanced
	* Advanced stats of players, which gives a more comprehensive view of players' ability. For example, Traditional Stats may not indicate if a player is a good scorer, but True Shooting Percentage of Advanced Stats could.

* /players/misc/ 
	* Filed in: `2015-16_general_dashboard.json` > GeneralStatsPerGame > Misc	
	* Some miscellaneous stats.

* /players/scoring/ 
	* Filed in: `2015-16_general_dashboard.json` > GeneralStatsPerGame > Scoring
	* Stats that measure players' scoring efficiency.

* /players/usage/ 
	* Filed in: `2015-16_general_dashboard.json` > GeneralStatsPerGame > Usage
	* Stats that show how much time one player is controlling the ball.

* /players/defense/ 
	*  Filed in: `2015-16_general_dashboard.json` > TrackingStatsPerGame > Defense
	* Stats that measure players' defense efficiency.
	
* /players/rebounding/  
	* Filed in: `2015-16_general_dashboard.json` > TrackingStatsPerGame
	*  Rebounding performance of player.
	
* Detailed defense stats of the players in different areas
	* Filed in: `2015-16_defense_dashboard.json`
	* /players/defense-dash-overall/: Overall
	* /players/defense-dash-3pt/: 3 Pointers
	* /players/defense-dash-2pt/: 2 Pointers
	* /players/defense-dash-lt6/: Less Than 6Ft
	* /players/defense-dash-lt10/: Less Than 10Ft
	* /players/defense-dash-gt15/: Greater Than 15Ft

* Play Type Statistics go beyond the play-by-play section of the box score and break down what happened on each play to produce the end result. This shows the frequency and efficiency of player when performing each play type. 
	* Filed in: `2015-16_play_types_dashboard.json`
	* /players/isolation/: Isolation
	* /players/transition/: Transition
	* /players/ball-handler/: PRBallHandler
	* /players/roll-man/: PRRollman
	* /players/post-up/: Postup
	* /players/spot-up/: Spotup
	* /players/hand-off/: Handoff
	* /players/cut/: Cut
	* /players/off-screen/: OffScreen
	* /players/putbacks/: OffRebound
	* /players/playtype-misc/: Misc
	
* Some detailed advanced stats that shows different aspects of abilities of players. 
	* Filed in: `2015-16_general_dashboard.json` > TrackingStatsPerGame
	* /players/catch-shoot/: CatchShoot
	* /players/defensive-impact/: Defense
	* /players/drives/: Drives
	* /players/passing/: Passing
	* /players/pullup/: PullUpShot
    * /players/shooting-efficiency/: Efficiency
	* /players/speed-distance/: SpeedDistance
	* /players/elbow-touch/: ElbowTouch
	* /players/post-touch/: PostTouch
	* /players/paint-touch/: PaintTouch
	

	
* Player shooting frequency and efficiency stats. 
	* Filed in: `2015-16_shot_dashboard.json`
	* /players/shots-general/: GeneralRange
	* /players/shots-shotclock/: ShotClockRange
	* /players/shots-dribbles/: DribbleRange
	* /players/shots-touch-time/: ClosestDefenderRange
	* /players/shots-closest-defender/: ClosestDefender10ftPlusRange
	* /players/shots-closest-defender-10/: TouchTimeRange
