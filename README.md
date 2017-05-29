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

## Play Type Stats(Most important stats in this project)

According to NBA.com, Play Type Statistics go beyond the play-by-play section of the box score and break down what happened on each play to produce the end result. Synergy Sports catalogs all of the action that takes place in each play of each game to provide a comprehensive look at how players and teams execute on offense and defense.

For each play type, the two most crucial pieces of information are:

* Frequency (Volume) - Percentage of times the given play type is executed
* Percentile (Efficiency) - PPP(Points per possession) ranked against the rest of the league

There are 10 different play types(another one is miscellaneous):

* Transition: When the possession-ending event comes before the defense sets following a possession change and a transition from one end of the court to the other.
* Isolation: When the possession-ending event is created during a “one-on-one” matchup. The defender needs to be set and have all of his defensive options at the initiation of the play.
* Pick & Roll: Ball Handler: A screen is set on the ball handler’s defender out on the perimeter. The offensive player can use the screen or go away from it and as long as the play yields a possession-ending event, it is tagged as a pick and roll.
* Pick & Roll: Roll Man: When a screen is set for the ball handler, and the screen setter then receives the ball for a possession-ending event. This action can include: pick and rolls, pick and pops and the screener slipping the pick.
* Post-Up: When an offensive player receives the ball with their back to the basket and is less than 15' from the rim when the possession-ending event occurs.
* Spot-Up: When the possession-ending event is a catch-and-shoot or catch-and-drive play.
* Hand-Off: The screen setter starts with the ball and hands the ball to a player cutting close by. This enables the player handing the ball off to effectively screen off a defender creating space for the player receiving the ball.
* Cut: An interior play where the finisher catches a pass while moving toward, parallel to or slightly away from the basket. This will include back screen and flash cuts as well as times when the player is left open near the basket.
* Off Screen: Identifies players coming off of screens (typically downs screens) going away from the basket toward the perimeter. This includes curl, fades, and coming off straight.
* Rebound (Putbacks): When the rebounder attempts to score before passing the ball or establishing themselves in another play type.
* Miscellaneous: When the action doesn't fit any of the other play types. This includes, but is not limited to, last second full court shots, fouls in the backcourt, or errant passes not out of a different play type, etc.

More description TBD

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
