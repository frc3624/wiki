# Software Implementation

* Table of Contents

    * [Ways to Implement Gear Shifting](#Ways-to-Implement-Gear-Shifting)
      * [Pneumatics](#**Pneumatics**)
      * [Software Multipliers (Speed Shifting)](#**Software-Multipliers**)
    * [When to Implement Which Type](#When-to-Implement-Which-Type)
    * [Past Code Examples](#Past-Code-Examples)
      * [Solenoid Shift](#**Solenoid-Shift**)
      * [Software Multipliers (Speed Shifting)](#**Software-Multipliers-(Speed-Shifting)**)
    * [Advanced Usages](#Advanced-Usages)
    * [Former Director Comments](#Former-Director-Comments-(only-edit-if-you-are-a-current-director))

## Ways to Implement Gear Shifting

### **Pneumatics**

In order to utilize gear shift, you must create a subsystem and a command. Within the subsystem, you must create a DoubleSolenoid object (for information on what a double solenoid exactly is, consult [this](Hardware_Aspects.md)). Along with this, you must create a method to set/toggle the gears (preferably toggle as there will most likely only be 2 gears using this style of gear shifting).

This style of gear shifting will most commonly be used on simpler robot designs. The more complex the robot becomes, the harder it is for build to utilize the pneumatics required for the gear shifting. Usually this style will be used (as it has been the main style throughout our team's history) but it may not be used if the robot design gets too complex.

// Can be longer in the future, just leaving it barebones and pretty simple for now since this is going to be a first draft

### **Software Multipliers**

Software speed shifting works by applying a multiplier to the speed parameter in the `arcadeDrive()` method in our Drive subsystem. This should make sense since all software speed shifting does is slow down the motors for the robot.

The first time the team used software speed shifting was with the robot for Infinite Recharge which used Falcon 500s. These motors are incredibly powerful and incredibly fast, so a multiplier was used to simplify the building process and to simply adjust the speed of the robot.

After creating the method, create as many commands as necessary in the commands folder (most likely 1-3, depending if you want a toggle command, or buttons to switch between individual modes).

// Can be longer in the future, just leaving it barebones and pretty simple for now since this is going to be a first draft

## When to Implement Which Type

**Pneumatic Style** \
This style will most likely be decided entirely by build. It is mostly dependent on the pneumatic setup and how it will interact with the rest of the robot, along with other factors build has to take into account. Luckily, this is a simple style to implement into the code.

**Speed Multipliers** \
This style will also be decided by build for the same aforementioned reasons. It is slightly harder to implement in some cases if some members are unfamiliar with enums. However, it is still relatively simple, and has the added benefit of being a part of the Drive subsystem, and does not need to be a separate subsystem.

**NOTE:** DO NOT ADD MULTIPLIERS TO THE DRIVETRAIN / JOYSTICKDRIVE COMMAND, KEEP THE MULTIPLIERS TO THE DRIVE CLASS. This is more of an organization thing, not that your code will break. It makes more sense to put the multiplier in the Drive subsystem itself instead of the command.

## Past Code Examples

### **Solenoid Shift**

In a separate GearShift class, a DoubleSolenoid object must be created, similar to this:

```java
private final DoubleSolenoid gearPiston = new DoubleSolenoid(PCM_ID, GEARSHIFT_FORWARD_CHANNEL, GEARSHIFT_REVERSE_CHANNEL);
```

and an accompanying method to toggle/set gears. A potential `toggleGear()` method can be seen below:

```java
public void toggleGear() {
    if (gearPiston.get() == Value.kReverse)
        gearPiston.set(Value.kForward);
    else if (gearPiston.get() == Value.kForward)
        gearPiston.set(Value.kReverse);
    else
        gearPiston.set(Value.kReverse);
}
```

Note: Value.kOff also exists, it turns off the solenoid for either being set forward or backwards.

Finally, a command to toggle/set the gears must be created. This would be accomplished by calling the method in the `initialize()` method of a command.

// This section is going to be more oriented towards reference material and less so explaining how it works, some code examples can help with the reference, and we could add some more in the future if you want. I think this is good enough since we shouldn't be giving exactly how to do it, but we're just giving some good reference material

### **Software Multipliers (Speed Shifting)**

The most barebones implementation of this technique is in this example below:

```java
public void arcadeDrive(double xSpeed, double zRotation) {
    diffDrive.arcadeDrive(speedMultiplier * xSpeed, zRotation);
}
```

As seen in the [drive class](https://github.com/frc3624/infinite-recharge/blob/master/src/main/java/frc/robot/subsystems/Drive.java) for infinite recharge, we used an enum to create the multipliers for the `arcadeDrive()` method. {Maybe include some explanation as to wtf an enum is, I don't know if you want that here or in a future lesson} This enum enabled us to have 3 distinct speeds for the robot, so this implementation may be useful for further robots.

**NOTE:** If you are viewing the source code for the drive class prior to revisions of the code on GitHub, the 0.9x multiplier was added for the zRotation due to members of the Drive team wanting the robot to turn slightly slower and we never got around to making it obvious in the code why we did that.

## Advanced Usages

Sometimes, both standard gear shifting and software speed shifting can be implemented into the same robot (seen in the Infinite Recharge robot). This can be achieved 

## Former Director Comments (only edit if you are a current director)

### Kyle

I am Kyle Bobert Diaz and I approve of this message.

### Matt & Talha

Haadi is such a great person and I love him so much - Matt