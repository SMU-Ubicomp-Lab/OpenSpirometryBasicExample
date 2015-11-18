#Open Spirometer in iOS

This is an example of using the [OpenSpirometryCore]:https://github.com/SMU-Ubicomp-Lab/OpenSpirometryCore in a basic iOS implementation. Please see that repository for a more detailed explanation of the core library. This project uses the OpenSpirometryCore as a submodule. If you want to clone this repository be sure that you clone while recursing submodules:
``` 
git clone --recursive https://github.com/SMU-Ubicomp-Lab/OpenSpirometryBasicExample.git
``` 

The ViewController has an example of how to use every public function for the given model: make it a property in your class and set yourself as the delegate. If the delegate is a UIViewController, then some additional functionality is provided for asking permission to use the microphone (i.e., recording). Use the "askPermissionToUseAudioIfNotDone" function to access this.

Since you are the delegate for the model (of type "SpirometerEffortDelegate") you get access to some notifications of the progress of the test. All notifications are given to you on the main thread because they are mostly meant to be used for updating UI. So if you want to do some intense processing from one of these notifications, you should do it on a separate queue (see Apple's documentation for *concurrency*, if you are unsure what I mean here). 

## Third Party Frameworks/Libraries

* [Novocaine]:https://github.com/alexbw/novocaine . I manipulated this for iOS8 and built completely for objective-c in iOS. It isn't really backwards compatible with Alex's library anymore--although you should definitely check out Novocaine. I use it in my iOS course here at SMU.  



