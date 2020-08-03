# Unity in Flutter

- Use unity 2019.3 or higher for ios and make sure you install the required plugins for andriod and mac see the 
[pub.dev page](https://pub.dev/packages/flutter_unity_widget)
- If you want to run this on a simulator use unity 2018.3 (It suppors x86 while newer versions of unity do not)

1. Create a unity folder in your projects root
2. Place the unity project in that folder
3. Open unity, change the platform device to android
4. Change the player settings so that looks like this ![Unity Settings](https://raw.githubusercontent.com/snowballdigital/flutter-unity-view-widget/master/Screenshot%202019-03-27%2007.31.55.png)
5. Export to flutter (android 2019.3)
6. Go back to flutter you should have a unity export folder. Create a `unity-classes` folder and place all the files from `/unity export/lib/`
7. Create a build.gradle and include `configurations.maybeCreate("default")` and `artifacts.add("default", file('unity-classes.jar'))`
8. In the `/andriod/settings.gradle` include `include ":UnityExport"` and `project(":UnityExport").projectDir = file("./UnityExport")` and also add `include ':app', ':unity-classes'` [see this link](https://github.com/snowballdigital/flutter-unity-view-widget/issues/111) 
9. In the `/andriod/app/build.gradle` make sure minsdk is = > 19
10. Now the project should run
