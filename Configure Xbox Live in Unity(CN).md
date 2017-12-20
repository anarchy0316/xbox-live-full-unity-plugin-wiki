这篇文章讲述的是在 Unity 中设置 Xbox Live plugin 的详细流程
## 首先要做的工作

在顺利使用 Unity 插件前你要完成以下步骤:
1. **[[创建一个能使用Xbox Live 的 Title|Pre-coding Preparation]]**.
2. 安装 **[Windows 10 Anniversary Update](https://microsoft.com/windows)** 或者更新版本的 Windows
3. **[Unity](https://store.unity.com/)** 版本 **2017.1p5** (or newer), 或 **2017.2.0f3** (or newer) with **Windows Store .NET Scripting Backend** 或 **Windows Store IL2CPP Scripting Backend**.
4. **[Visual Studio 2017 15.3.3](https://www.visualstudio.com/)** (or newer) with the **Universal Windows Platform development** workload and **Game Development with Unity** workload.
   > 您可以取消选择Unity Editor可选组件，因为您将安装更新版本的Unity。

   > 如果您在Unity中使用 IL2CPP, 您也可以选择 **Desktop development with C++** workload.

## Import Unity 插件
您需要按照以下步骤来将插件载入您的Unity项目中

1. 导航至 Xbox Live Unity Plugin release  [页面](TODO).
2. 下载 **XboxLive.unitypackage**.
3. 在 Unity 中, 点击 **Assets** > **Import Package** > **Custom Package** 并且导航至 **XboxLive.unitypackage**.

## 将Visual Studio设置为 Unity 的默认IDE
您需要 Visual Studio 来生成一个[Universal Windows Platform (UWP)](https://docs.microsoft.com/windows/uwp/get-started/whats-a-uwp)游戏。您可以通过导航至 **Edit** > **Preferences** > **External Tools** 并设置**External Script Editor** 为 Visual Studio 来将你的Unity IDE 设置为 Visual Studio


![set VS External Tool](images/setVSExternalTool_small.gif)

## 授权 Xbox Live
为了让您的Title可以和Xbox Live 交互，你需要对 Xbox Live 进行初始设置。利用 Xbox Live Association Wizard 你可以很轻松地在Unity 中实现这一点。

1. 在 **Xbox Live** 菜单中, 选择 **Configuration**.
2. 在 **Xbox Live** 窗口中, 选择 **Run Xbox Live Association Wizard**.
3. 在 **Associate Your Game with the Windows Store** 对话框中, 点击 **Next**,并且登陆你的Dev Center account
4. 选择您想要和project关联的app, 然后点击 **Select**. 如果你没有看到的话, 请尝试点击 **Refresh**.
5. 在点击后您将会看到 "This application is already Xbox Live enabled." . 如果没有的话，请在你的Xbox Live service中为您的 title 授权 xbox功能,然后再尝试这一步。
   > 即使是 Creators Program,您依然可以通过点击 **Enable** 来为您的 Title 授权 Xbox Live 功能.
6. 点击 **Continue** 来选择一个沙盒.
   > 对 ID@Xbox 开发者来说,请确认选择了发布的 Xbox Live的配置里的同一个沙盒。
7. 点击 **Finish** 来保存您的配置.

要调用Xbox Live服务, 您的电脑必须处于开发人员模式并为您的Title 设置 在Xbox Live 配置相同的沙盒。 您可以通过在Unity中查看 **Xbox Live Configuration** 窗口来验证两者：

1. **Developer Mode Configuration** 应当是 **Enabled**. 如果显示 **Disabled**, 请点击 **Switch to Developer Mode**.
2. **Title Configuration** > **Sandbox** 应该和 **Developer Mode Configuration** > **Developer Mode** 具有与相同的ID. 如果不是，请点击 **Switch to Developer Mode**.

   ![XBL Enabled](images/unity-xbl-enabled.png)

## 生成和测试项目
您可以按照以下步骤再Unity中生成 UWP项目：

1. 通过点击 **File > Build Settings** 或者 **Ctrl+Shift+B** 打开 **Build Settings** 窗口。
2. 确认您在 **Scenes In Build** 中加入了您想要测试的 Scene，如果没有的话，请打开该 Scene 并且选择  **Add Open Scenes**.
3.通过选择在 **Platform** 下的 **Universal Windows Platform** 并点击 **Switch Platform** 来切换到 **Universal Windows Platform**.
4. 为了能 Debug 脚本, 请勾上 **Unity C# Projects**.
5. 点击 **Build** 并且 确认项目所要生成的路径.

   ![build in unity](images/buildInUnity.gif)

一旦完成Build, Unity将会生成一个新的UWP Solution,接下来您需要在 Visual Studio 中做的是：

1. 在您指定生成Project的路径下, 在 Visual Studio 中打开 **&lt;ProjectName&gt;.sln**.
2. 在顶部的工具栏中, 选择 **x64** 并且部署为 **Local Machine**.

如果您在从Unity 中生成 UWP solution 选择了  **script debugging**，那么您的脚本将会位于 **Assembly-CSharp (Universal Windows)** project 下。


> Note: 确认您已经在Xbox Live 中登陆了一个测试账号，即 [authorized test account](https://docs.microsoft.com/en-us/windows/uwp/xbox-live/get-started-with-creators/authorize-xbox-live-accounts).

## 测试项目
您已经做好了在您的 Unity 项目中使用 Xbox Live 的全部工作！请尝试在 **Xbox Live / Examples** 文件夹中打开场景以查看插件的实际使用方式，以及有关如何使用这些功能的示例。


测试 **SignInAndProfile** scene 来登陆您的MSA账号 , **Leaderboard** scene 来创建一个一个leaderboard, 以及 **UpdateStat** scene 来展示stats的更新.
