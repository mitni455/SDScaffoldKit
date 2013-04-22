SDScaffoldKit
=======

###Check out [SDScaffoldSync](https://github.com/stevederico/SDScaffoldSync)- Create a cloud syncing mobile app in 3 minutes.
> [SDScaffoldSync](https://github.com/stevederico/SDScaffoldSync)- Create a Cloud Syncing Mobile App in 3 Minutes

**Scaffolding for Core Data Models**

UIKit can be tedious and repeative to build simple CRUD interfaces. SDScaffoldKit is a simple library that provides Create, Read, Update, and Delete views/viewcontrollers out-of-the-box. Just create your Core Data model, hand it your Entity's name, a field to sort by, and BAM! You are ready to start creating and managing objects.

> SDScaffoldKit is named after Ruby on Rails's [scaffolding](http://guides.rubyonrails.org/getting_started.html#getting-up-and-running-quickly-with-scaffolding).

SDScaffoldingKit is meant to save you time so you can focus on what matters, application logic. The library is still a little green behind the ears and I would love to see any issues or pull request you may have. There is a sample project if you have any question on how it all works.

Overall, this is a great way to get your project up and running then you can go from there.

> If you enjoy this project, I would encourage you to check out [Mattt Thompson's](http://www.github.com/mattt) series of open source libraries covering the mission-critical aspects of an iOS app's infrastructure. Be sure to check out its sister projects: [GroundControl](https://github.com/mattt/GroundControl), [SkyLab](https://github.com/mattt/SkyLab), [CargoBay](https://github.com/mattt/CargoBay), and [houston](https://github.com/mattt/houston).

## Getting Started

### Create Core Data Models

1. Add `CoreData.framework` into your project
2. Create Core Data Model
3. `#import "SDScaffoldKit.h"` and create an instance with desginated initializer `initWithEntityName:sortBy:context:andStyle:`

```objective-c
  SDScaffoldIndexViewController *scaffoldViewController = [[SDScaffoldIndexViewController alloc] 
    initWithEntityName:@"User" sortBy:@"lastname" context:[self managedObjectContext] andStyle:UITableViewStyleGrouped];
```
Then wrap your `SDScaffoldIndexViewController` instance in a `UINavigationController`

```objective-c 
 UINavigationController *navController = [[UINavigationController alloc] 
    initWithRootViewController:scaffoldViewController];
```
Done!


## Example Usage
```objective-c
- (BOOL)application:(UIApplication *)application didFinishLaunchingWithOptions:(NSDictionary *)launchOptions
{
     // Override point for customization after application launch.
    self.window = [[UIWindow alloc] initWithFrame:[[UIScreen mainScreen] bounds]];
   
    SDScaffoldIndexViewController *scaffoldViewController = [[SDScaffoldIndexViewController alloc] initWithEntityName:@"User" 
     sortBy:@"lastname" context:[self managedObjectContext]];
    
    UINavigationController *navController = [[UINavigationController alloc] initWithRootViewController:scaffoldViewController];
  
    self.window.rootViewController = navController;
    self.window.backgroundColor = [UIColor whiteColor];
    [self.window makeKeyAndVisible];
    
    return YES;
}
```
## Sample Images
![User Index](http://cl.ly/Lh6Q/iOS%20Simulator%20Screen%20shot%20Dec%2018,%202012%209.14.11%20PM.png) Index
![Add User](http://cl.ly/Lgcq/iOS%20Simulator%20Screen%20shot%20Dec%2018,%202012%208.55.31%20PM.png) Create
![Show User](http://cl.ly/LgTc/iOS%20Simulator%20Screen%20shot%20Dec%2018,%202012%209.30.35%20PM.png) Show
![Edit User](http://cl.ly/Lfeo/iOS%20Simulator%20Screen%20shot%20Dec%2018,%202012%209.30.46%20PM.png) Update
![Delete User](http://cl.ly/LgRo/iOS%20Simulator%20Screen%20shot%20Dec%2018,%202012%209.31.55%20PM.png) Delete

## Contact

Steve Derico

- http://github.com/stevederico
- http://twitter.com/stevederico
- steve@deri.co

## License


SDScaffoldKit is available under the MIT license. See the LICENSE file for more info.
