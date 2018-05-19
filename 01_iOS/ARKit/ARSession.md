# ARSession
A shared object that manages the device camera and motion processing needed for augmented reality experiences.

AR 환경을 위한 디바이스 카메라와 모션 프로세싱을 관리하는 싱글톤 객체.

## Overview
An ARSession object coordinates the major processes that ARKit performs on your behalf to create an augmented reality experience. These processes include reading data from the device's motion sensing hardware, controlling the device's built-in camera, and performing image analysis on captured camera images. The session synthesizes all of these results to establish a correspondence between the real-world space the device inhabits and a virtual space where you model AR content.
Every AR experience built with ARKit requires a single ARSession object. If you use an ARSCNView or ARSKView object to easily build the visual part of your AR experience, the view object includes an ARSession instance. If you build your own renderer for AR content, you'll need to instantiate and maintain an ARSession object yourself.
Running a session requires a configuration. Subclasses of the abstract ARConfiguration class determine how ARKit tracks a device's position and motion relative to the real world, and thus affect the kinds of AR experiences you can create. For example, use ARWorldTrackingConfiguration for experiences that augment the user's view of the world around them though the device's back camera.

[Apple Documents][apple]

[apple]: https://developer.apple.com/documentation/arkit/arsession
