# SingleViewApp ![Swift 4.2](https://img.shields.io/badge/Swift-4.2-orange.svg)

Xcode helps us to create a single view application with AppDelegate and storyboard. 
For this reason, many developers does not know the basic app luanching flow. 
This demo intrduces how to create an iOS single view application demo created by code, which can help us to understand the app luanching.

### Create a Project
Create a single view application and delete ViewController, AppDelegate and Main.storyboard files.
Set the Main Interface in the Development Info to empty.

### Luanch App with main.swift
Create a new file named `main.swift` and add the following code.

```Swift
import UIKit

UIApplicationMain(
    CommandLine.argc,
    CommandLine.unsafeArgv,
    NSStringFromClass(UIApplication.self),
    NSStringFromClass(AppDelegate.self)
)
```

In the `UIApplicationMain` method, we passed the argc and argv parameters like the C language at first.
Then we passed the UIApplication and AppDelegate.
We can create a subclass of UIApplication for some customized demand.

Then we add a file named `AppDelegate.swift` and add the following code.

```Swift
import UIKit

class AppDelegate: UIResponder, UIApplicationDelegate {

    var window: UIWindow?

    func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
        window = UIWindow()
        window?.rootViewController = ViewController()
        window?.makeKeyAndVisible()
        return true
    }

}
```

It seems to the AppDelegate created by Xcode automatically.
We defined a `UIWindow` property and initialzed it in the `application(_ application: didFinishLaunchingWithOptions)` method.
We set the `rootViewController` for `UIWindow` and make it visable at last.

### Run it
Because we have defined a ViewController and set its background to light gray, we can see a light gray screen in the simulator after lunching the app.
