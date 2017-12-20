Stats are key pieces of information you want to track about a player. The stats that you track with Xbox Live should be stats that are relevant to the player, and are displayed in some manner. There are two kinds of stats, featured stats and normal ones. For more information, see [Player Stats](https://docs.microsoft.com/windows/uwp/xbox-live/leaderboards-and-stats-2017/player-stats).

## Featured stats
Featured stats are the ones defined on Dev Center. They will appear on your title's Game Hub. These will make your Game Hub look more interesting, and generate automatic leaderboards to keep players engaged. You can also use them to draw attention to certain gameplay mechanics in your title since these are visible to all players on Xbox Live, even if they don't own your title.

> Note: All stats configured on Dev Center are featured stats. Featured stats and leaderboards are configured together. Every leaderboard is based on a stat. Each featured stat will have an associated global leaderboard.

From now on, all new titles created on [Windwos Dev Center](https://dev.windows.com/) are using Data Platform 2017. For how to configure, please see [Configuring Featured Stats or Leaderboards on Dev Center with Data Platform 2017](https://docs.microsoft.com/windows/uwp/xbox-live/leaderboards-and-stats-2017/player-stats-configure-2017).

## Normal stats
Other stats are thought as normal stats. They do not need to be configured on Dev Center. You can set and update them by calling `StatisticManager.SetStatisticNumberData`, `StatisticManager.SetStatisticIntegerData` or `StatisticManager.SetStatisticStringData` method. For more information, see [Updating Stats 2017](https://docs.microsoft.com/windows/uwp/xbox-live/leaderboards-and-stats-2017/player-stats-updating).

## Using the stat prefabs
With the Xbox Live Unity plugin, you can easily add stats and display in your Unity project. Similar to the sign in steps, you can choose to use the included prefabs or attach the included scripts to your own custom game objects.

For more information, see [Using the player stat prefabs](https://docs.microsoft.com/windows/uwp/xbox-live/get-started-with-creators/add-stats-and-leaderboards-in-unity#using-the-player-stat-prefabs).

> Note: If you didn't set any value for a stat, you will get a "Stat not found in document" erro when you calling `StatisticManager.GetStatistic` method. So it's possible that after you adding a stat prefab with the right ID of your featured stat in Unity, you still get a Stat not found in document" erro. You can try to set a value for the stat first and then try again.

## See also

* [[Configure Xbox Live in Unity]]
* [[Sign into Xbox Live in Unity|Sign In]]
