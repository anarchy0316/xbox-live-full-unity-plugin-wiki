使用Xbox Live Unity plugin，您可以在Unity项目中轻松地登录 Xbox Live。 您可以使用内置的 prefab，也可以将包含的脚本附加到您自己的自定义 object 中。 本篇假设您已经在 Unity 项目中设置了Xbox Live plugin。 有关如何操作的信息，请参阅[[Configure Xbox Live in Unity]]]。

## 配置和测试 prefabs
你可以按照如下步骤在你的 Scene 中登陆 Xbox Live:

1. 将 **UserProfile** prefab 拖拽进 scene.
2. 将 **XboxLiveServices** 拖拽进 scene.


您将需要生成项目并从 Visual Studio 中运行，以便使用真实的 Xbox Live 帐户进行登录。

### UserProfile Prefab
**UserProfile** prefab 是最重要的 Xbox Live prefab, 它位于 **Xbox Live\Prefabs** 目录下. 这个 prefab 允许用户登录到 Xbox Live，并且在用户登录之后，显示他们的gamertag，gamerpic 和 gamerscore。 通常您会在初始菜单上显示这个perfab，或者在游戏启动时自动触发它。 为了使用任何其他 Xbox Live prefab，您必须 引入 UserProfile prefab 或手动调用 Sign-in API. 具体请请参阅 **UserProfile.cs** 脚本和下面的内容来了解关于如何操作的详细信息。

在 Unity Inspector 中，你可以设置如下 attributes:
* Input Controller Button: 指定将用于登录Xbox Live用户的按钮。
* Allow Guest Accounts: 支持第二个玩家使用 其 Xbox Live 个人资料登录或仅作为 Guest 进行游戏。 这只适用于多个用户登录的场景。更多信息请访问[Add multi-user support to your Unity Game](https://docs.microsoft.com/windows/uwp/xbox-live/get-started-with-creators/add-multi-user-support) for more information.


### XboxLiveServices Prefab
要使用任何 Xbox Live prefab，您需要在初始场景中拥有 **XboxLiveServices** prefab的实例。 您可以切换是否通过 `XboxLiveServicesSettings` 脚本（包含在 prefab 中）在控制台中显示Xbox Live调试消息。


## 使用 scripts
在 **UserProfile** prefab 中用来登陆 Xbox Live的脚本是 `Xbox Live\Scripts\UserProfile.cs`.最主要也最值得注意的method是`SignInAsync`，它 调用了 `XboxLiveUser.SignInSilentlyAsync` 和 `XboxLiveUser.SignInAsync` 两个 method. 更多的底层细节，请访问  [Authentication for UWP projects](https://docs.microsoft.com/windows/uwp/xbox-live/using-xbox-live/auth/authentication-for-uwp-projects).

`XboxLiveUserInfo` 脚本  (`Xbox Live\Scripts\XboxLiveUserInfo.cs`) 管理了 Xbox Live 在 Unity 中最重要的两个功能。 `XboxLiveUserInfo.User`提供了各种服务被调用时可能需要的 当前认证的 user 的 reference.`XboxLiveUserInfo.XboxLiveContext` 是可以用来访问 Xbox Live services 的 Xbox Live context。

如果用户已经成功登陆了，你可以从以上脚本中中获取更多的信息。您可以看 `UserProfile.LoadProfileInfo` 来参考脚本是如何得到用户的 id， gamerpic 以及更多信息。


## 接下来请参考

* [[Configure Xbox Live in Unity]]
