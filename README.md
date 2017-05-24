# shogun-data

Datasets used in shogun project

## Description

The data used in this project is from NBA [official stats website](http://stats.nba.com/players/). `description.json` contains description of every field in dataset. These data include both player stats and team stats, and both of them have plenty of categories, which is list below. These are sub path of http://stats.nba.com/, so you could view the web version of stats by visiting the url. Team stats structure are same with player stats. The only difference is team stats path start with 'team' while player stats path with 'player'

* /players/traditional/
    * Traditional basic stats of players, such as points, assists and rebounds. They are the most widely used stats but cannot show limited view of players' ability.
* /players/advanced/
    * Advanced stats of players, which gives a more comprehensive view of players' ability. For example, points  stats of Traditional Statsmay not indicate that a player is a good scorer but True Shooting Percentage of Advanced Stats could.
* /players/misc/
    * Some miscellaneous stats.
* /players/scoring/
    * Stats that measure players' scoring efficiency.
* /players/usage/
    * Stats that shows how much time one player is controlling the ball.
* /players/opponent/
    * Stats that shows opponent's performance when the player is on court.
* /players/defense/
    * Stats that measure players' defense efficiency.
* /players/clutch-traditional/
    * Similar to traditional stats but only include stats during last minutes of the game.
* /players/clutch-advanced/
    * Similar to advanced stats but only include stats during last minutes of the game.
* /players/clutch-misc/
    * Similar to misc stats but only include stats during last minutes of the game.
* /players/clutch-scoring/
    * Similar to scoring stats but only include stats during last minutes of the game.
* /players/clutch-usage/
    * Similar to usage stats but only include stats during last minutes of the game.
* /players/clutch-opponent/
    * Similar to opponent stats but only include stats during last minutes of the game.
* /players/defense/ shows detailed defense stats of players in different area
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
