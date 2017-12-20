A leaderboard represents an ordered, numbered list of the players who have achieved the "best" value of a stat. For example, a leaderboard might list the people who have achieved the fastest time on a race lap, so that players can compare their best race time against the best race times achieved by other players.

Leaderboards are based on the player stats that are sent to the Xbox Live service by the game. Therefore, leaderboard data is read only, as you cannot modify them directly.

The Xbox Live Unity plugin provides a sample Leaderboard prefab that you can use to understand how to implement leaderboards in your game.

For more information about leaderboards, see [Leaderboards](https://docs.microsoft.com/windows/uwp/xbox-live/leaderboards-and-stats-2017/leaderboards).

## Using the leaderboard prefabs

The Xbox Live Unity plugin contains two prefabs for leaderboards:

* Leaderboard: An object that represents a leaderboard, and contains simple UI to display the values from the leaderboard.
* LeaderboardEntry: An object that represents a single row of a leaderboard.

You can drag a **Leaderboard** prefab onto the scene. In the Unity Inspector, you can set the following attributes:

* Stat: The stat gameobject that this leaderboard is associated with.
* Leaderboard Type: The scope of the results that should be returned for the leaderboard entries.
* Entry Count: The number of rows of data to display per page.

You must build and export your project to Visual Studio and sign in with an authorized user to see real data values. For more information, see [[Configure Xbox Live in Unity]].

## See also

* [[Configure Xbox Live in Unity]]
* [[Sign into Xbox Live in Unity|Sign In]]
* [[Stats]]