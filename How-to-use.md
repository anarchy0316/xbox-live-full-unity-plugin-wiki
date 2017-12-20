* If your title is created on [Windows Dev Center (UDC)](http://dev.windows.com/), no matter you are using the Xbox Live Creators Program or ID@Xbox, you can use this plugin like [Configure Xbox Live In Unity](https://docs.microsoft.com/en-us/windows/uwp/xbox-live/get-started-with-creators/configure-xbox-live-in-unity).
For more information, please refer to [Develop in Unity](https://docs.microsoft.com/en-us/windows/uwp/xbox-live/get-started-with-creators/develop-creators-title-with-unity).

* If your title is created on [Xbox Developer Portal (XDP)](https://xdp.xboxlive.com/), then you can not use Xbox Live Association Wizard. After importing the Unity plugin, please follow below steps:
  1. __Build the project__
      1. Open the __Build Settings__ window by selecting __File > Build Settings__ or by pressing __Ctrl+Shift+B__.
      2. Make sure that you have the scene that you want to test included in your build under __Scenes In Build__. If it's not listed, open the scene and select __Add Open Scenes__.
      3. Switch to the __Universal Windows Platform__ by selecting __Universal Windows Platform__ under __Platform__ and clicking __Switch Platform__.  
		(For Unity 5.x, Switch to the __Windows Store__ platform by selecting __Windows Store__ under __Platform__ and clicking __Switch Platform__, then set __SDK__ to __Universal 10__)
      4. To enable script debugging check __Unity C# Projects__.
      5. Click __Build__ and specify the location of the project.     
  2. [__Associate your Visual Studio project with your UWP app__](https://docs.microsoft.com/en-us/windows/uwp/xbox-live/get-started-with-partner/get-started-with-visual-studio-and-uwp#3-associate-your-visual-studio-project-with-your-uwp-app)

      Open the generated UWP project in Visual Studio, then right click on the Project in Visual Studio and choose __Store > Associate App with the Store__.
  3. [__Add Xbox Live configuration to the UWP app__](https://docs.microsoft.com/en-us/windows/uwp/xbox-live/get-started-with-partner/get-started-with-visual-studio-and-uwp#4-associate-your-visual-studio-project-with-your-xbox-live-enabled-title)
  4. [__Add Internet capabilities to your Visual Studio Project__](https://docs.microsoft.com/en-us/windows/uwp/xbox-live/get-started-with-partner/get-started-with-visual-studio-and-uwp#6-add-internet-capabilities-to-your-visual-studio-project)
  5. [__Change the sandbox of your target device__](https://docs.microsoft.com/en-us/windows/uwp/xbox-live/xbox-live-sandboxes#switch-your-pcs-development-sandbox)
  6. __Compile and run the UWP app from Visual Studio__