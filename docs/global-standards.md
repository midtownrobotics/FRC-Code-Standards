# Global Standards
This section provides standards that govern the setup and maintence of robot code projects.

## Global Dependencies
* [WPIlib](https://github.com/wpilibsuite/allwpilib) is the framework that teams use to write code for FRC robots.
* [AdvantageKit](https://github.com/Mechanical-Advantage/AdvantageKit) is a logging framework created by [FRC team 6328](https://www.thebluealliance.com/team/6328/) which has been released for public use.
* [Gversion](https://github.com/lessthanoptimal/gversion-plugin) is an [AdvantageKit](https://github.com/Mechanical-Advantage/AdvantageKit) dependency that creates the [```BuildConstants.java```](BuildConstants.java) file which is important for log replay.
* [Lombok](https://projectlombok.org/) is an annotation based java library that helps reduce boilerplate code by automatically generating getters, setters, etc.
* [Spotless](https://github.com/diffplug/spotless) is a code formatter that automatically formats the entire project when compiled.

These dependencies should be present in the [build.gradle](build.gradle) file in each robot project.

## Objects
### Naming Conventions
* Classes and Enumerations should follow PascalCase.
* Variables should follow camelCase. Member reference variables should begin with `m_`.
* Constants should follow SNAKE_CASE.
* Directories should follow snake-case.

### Instantiation
Any object that can be instantiated without relying on constructor arguments, (e.g. constants and member variables) should be instantiated at declaration. These objects should be declared and instantiated above any variables that require a constructor for instantiation:

```java
...

public class SomeClass {

  private int someVariable = 0;

  private SomeOtherClass m_someRobotVariable;

  public SomeClass(SomeOtherClass someRobotVariable) {
    this.m_someRobotVariable = someRobotVariable;
  }

  ...
}
```

### Modifiers
Member variables should always be private with ```@Getter```/```@Setter``` annotations if they require getters and/or setters. Static variables should always come before non-static variables

Constants should always have the ```public static final``` modifiers.


### Null Checks
All variables which may be null should be wrapped in an Optional Type. Ideally have null analysis running as well.

Being null-safe is crucial in software development as it prevents unexpected runtime errors and enhances code reliability. Without proper null checks, programs risk NullPointerExceptions, leading to crashes and a poor user experience. By using optional types and performing checks, developers can create more predictable, error-resistant code, simplifying debugging and improving maintainability for future development.

## Default Units
1648 uses these default units for all robot code:

|Measurement | Unit|
|------------|------|
|Linear Position|Meters|
|Linear Velocity|Meters per Second|
|Linear Acceleration|Meters per Second Squared|
|Angluar Position|Radians|
|Angular Velocity|Radians per Second|
|Angular Acceleration|Radians per Second Squared|
|Mass|Kilograms|
|Moment of Inertia|Kilogram Meters Squared|
|Force|Netwons|
|Torque/Moment|Newton Meters|
|Voltage|Volts|
|Current|Amps|
|Temperature|Fahrenheit|
