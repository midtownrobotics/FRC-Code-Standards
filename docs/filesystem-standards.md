# Robot Filesystem
```plaintext
frc/
│
├── lib/
│
├── robot/
│   │
│   ├── command/
│   │   ├── auton/
│   │   │   └── SomeAutonCommand.java
│   │   └── SomeCommand.java
│   ├── sensors/
│   │   └── some-sensor/
│   │       ├── SomeSensor.java
│   │       ├── SomeSensorConstants.java
│   │       ├── SomeSensorIO.java
│   │       ├── SomeSensorIOSim.java
│   │       └── SomeSensorIOType.java
│   ├── subsystems/
│   │   └── some-subsystem/
│   │       ├── some-mechanism/
│   │       │   ├── SomeMechanismIO.java
│   │       │   ├── SomeMechanismIOSim.java
│   │       │   └── SomeMechanismIOType.java
│   │       ├── SomeSubsystem.java
│   │       └── SomeSubsystemConstants.java
│   ├── utils/
│   │
│   ├── BuildConstants.java
│   ├── Constants.java
│   ├── FieldConstants.java
│   ├── Main.java
│   ├── Robot.java
│   ├── RobotContainer.java
│   └── RobotState.java
```

## Description of Structure

- **`frc/`**: The root directory for your FRC robot project.
- **`lib/`**: A directory designated for libraries/files which are not year specific.
- **`robot/`**: Contains the main code and organization for the robot.
  - **`command/`**: Directory for command classes that control robot actions.
    - **`auton/`**: Subdirectory for autonomous commands.
  - **`sensors/`**: Directory for sensor-related classes and functionality.
    - **`some-sensor/`**: Subdirectory for a specific sensor's implementation.
      - **`SomeSensor.java`**: Class representing the sensor's public facing functionality.
      - **`SomeSensorConstants.java`**: Contains constant values related to the sensor's operation.
      - **`SomeSensorIO.java`**: Input/Output handling class for the sensor.
      - **`SomeSensorIOSim.java`**: Simulation version of the sensor's I/O handling.
      - **`SomeSensorIOType.java`**: Real version of the sensor's I/O handling.
  - **`subsystems/`**: Directory for subsystem classes that manage various robot mechanisms.
    - **`some-subsystem/`**: Subdirectory for a specific subsystem's implementation.
      - **`some-mechanism/`**: Subdirectory for a particular mechanism within the subsystem.
        - **`SomeMechanismIO.java`**: I/O handling class for the mechanism.
        - **`SomeMechanismIOSim.java`**: Simulation version of the mechanism's I/O handling.
        - **`SomeMechanismIOType.java`**: Real version of the mechanism's I/O handling.
      - **`SomeSubsystem.java`**: Class representing the subsystem's public facing functionality.
      - **`SomeSubsystemConstants.java`**: Contains constant values related to the subsystem's operation.
  - **`utils/`**: A directory for year-specific utility classes.
  - **`BuildConstants.java`**: Class holding build-specific constants.
  - **`Constants.java`**: Class containing general constants used throughout the robot code.
  - **`FieldConstants.java`**: Class defining constants related to the field and game elements.
  - **`Main.java`**: The entry point of the robot code where execution begins.
  - **`Robot.java`**: Main class managing the overall robot functionality and lifecycle.
  - **`RobotContainer.java`**: Manages the robot's subsystems and command structure, defining how they interact.
  - **`RobotState.java`**: Represents the current operational state of the robot.