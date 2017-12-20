Welcome to the xbox-live-full-unity-plugin wiki!

This plugin is based on [xbox-live-unity-plugin](https://github.com/Microsoft/xbox-live-unity-plugin) to support [ID@Xbox](https://www.xbox.com/en-US/developers/id) program. Most API surfaces are remained the same. 

In this plugin, we used [xbox-live-api](https://github.com/Microsoft/xbox-live-api) instead of the original Xbox Live libraries (e.g. Microsoft.Xbox.Services.UWP.CSharp.dll), so that we can use achievements and some other features that is not supported in Xbox Live Creators Program. However, as we used WinRT APIs, there will be no placeholder data when playing in the editor.

This plugin is still under developing. For now, it only demonstrates SignIn and Profile, Stats, Leaderboards and Achievements. Developers can refer to this plugin and develop your own implementation.
