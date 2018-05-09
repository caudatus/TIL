# SCNPhysicsVehicle
A physics behavior that modifies a physics body to behave like a car, motorcycle, or other wheeled vehicle.

선언된 physics body 객체가 차, 오토바이, 다른 바퀴달린 탈 것들 처럼 움직이도록 물리적인 움직임을 만드는 객체

## Overview
To build a vehicle, designate an SCNPhysicsBody object as its chassis and an array of SCNPhysicsVehicleWheel objects as its wheels

vehicle 객체를 만들기 위해서는 chassis에 SCNPhysicsBody객체와 wheels array에 [SCNPhysicsVehicleWheel][wheel] 객체가 지정되어야 한다.

## Example
```Swift
let scene = SCNScene(named: "Car-Scene.scn")
let chasiss = (scene?.rootNode.childNode(withName: "chasiss", recursively: false))!

let frontLeftWheel = (chasiss.childNode(withName: "frontLeft", recursively: false))!
let frontRightWheel = (chasiss.childNode(withName: "frontRight", recursively: false))!
let rearLeftWheel = (chasiss.childNode(withName: "rearLeft", recursively: false))!
let rearRightWheel = (chasiss.childNode(withName: "rearRight", recursively: false))!

let vehicleFrontLeftWheel = SCNPhysicsVehicleWheel(node: frontLeftWheel)
let vehicleFrontRightWheel = SCNPhysicsVehicleWheel(node: frontRightWheel)
let vehicleRearLeftWheel = SCNPhysicsVehicleWheel(node: rearLeftWheel)
let vehicleRearRightWheel = SCNPhysicsVehicleWheel(node: rearRightWheel)

let body = SCNPhysicsBody(type: .dynamic, shape: SCNPhysicsShape(node: chasiss, options: [SCNPhysicsShape.Option.keepAsCompound: true]))
chasiss.physicsBody = body

self.vehicle = SCNPhysicsVehicle(
   chassisBody: chasiss.physicsBody!,
   wheels:
   [vehicleFrontLeftWheel, vehicleFrontRightWheel, vehicleRearLeftWheel, vehicleRearRightWheel])
self.sceneView.scene.physicsWorld.addBehavior(self.vehicle)

self.sceneView.scene.rootNode.addChildNode(chasiss)
```

[Apple Documents][apple]

[wheel]: https://developer.apple.com/documentation/scenekit/scnphysicsvehiclewheel
[apple]: https://developer.apple.com/documentation/scenekit/scnphysicsvehicle
