With the Xbox Live Unity plugin, you can easily sign in to Xbox Live in your Unity project. You can use the included prefab, or you can attach the included scripts to your own custom objects. This topic assumes that you have already set up the Xbox Live plugin in your Unity project. For information about how to do that, see [[Configure Xbox Live in Unity]].

## Configure and test the prefabs
You can setup your scene to sign into Xbox Live by doing the following:

1. Drag the **UserProfile** prefab onto the scene.
2. Drag the **XboxLiveServices** prefab onto the scene.

You will need to build the project and run it from Visual Studio in order to sign in with a real Xbox Live account.

### UserProfile Prefab
The **UserProfile** prefab is the most important Xbox Live prefab, and is located in **Xbox Live\Prefabs**. This prefab allows the user to log in to Xbox Live, and after the user is logged in, it will show their gamertag, gamerpic, and gamerscore. Usually you would show this prefab on the initial menu screen, or automatically trigger it when the game launches. In order to use any of the other Xbox Live prefabs, you must include a UserProfile prefab or manually invoke the sign-in API. See the **UserProfile.cs** script and the section below for details on how to do this.

In the Unity Inspector, you can set the following attributes:

* Input Controller Button: Specify the button that will be used to sign in an Xbox Live user.
* Allow Guest Accounts: Enables the support for secondary players to sign in with their Xbox Live profile or play as a guest. This is only relevant in scenarios where multiple users are signing in. See [Add multi-user support to your Unity Game](https://docs.microsoft.com/windows/uwp/xbox-live/get-started-with-creators/add-multi-user-support) for more information.

### XboxLiveServices Prefab
To use any of the Xbox Live prefabs, you'll need to have an instance of the **XboxLiveServices** prefab in your initial scene. You can toggle whether Xbox Live debug messages are displayed in the console via the `XboxLiveServicesSettings` script, which is included on the prefab.

## Using the scripts

The script that the **UserProfile** prefab uses to sign in to Xbox Live is `Xbox Live\Scripts\UserProfile.cs`. The main method to be aware of here is `SignInAsync`, which calls `XboxLiveUser.SignInSilentlyAsync` and `XboxLiveUser.SignInAsync` method. For more underlying details, see [Authentication for UWP projects](https://docs.microsoft.com/windows/uwp/xbox-live/using-xbox-live/auth/authentication-for-uwp-projects).

`XboxLiveUserInfo` script (`Xbox Live\Scripts\XboxLiveUserInfo.cs`) manages two of the most important Xbox Live functionalities in Unity. `XboxLiveUserInfo.User` provides a reference to the currently authenticated user which might be need when making calls to various services. `XboxLiveUserInfo.XboxLiveContext` is the Xbox Live context which can be used to access lots of Xbox Live services.

Once the user has been signed in, you can get information about them. You can look at `UserProfile.LoadProfileInfo` to see how the script gets the user's ID, gamerpic, and other information.

## See also

* [[Configure Xbox Live in Unity]]
