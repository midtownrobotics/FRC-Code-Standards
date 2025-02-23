# Subsystem Standards
This section provides standards that govern how subsystems are written and maintained.

## Subsystems Overview
Subsystems are how FRC teams split up the logic for the different parts of the robots. Each subsystem must:

* Extend ```SubsystemBase```.
* Not include any [constants](constants-standards.md).
* Override the ```periodic()``` method.
    * Subsystem logic.
    * Update IO implementation with inputs - this must come before processing the inputs.
    * Process the subsystem inputs.
    * Update the mechanism widget.
    * Update any [tunable numbers](logging-standards.md).
    * Update any Real Outputs
* Contain all logic for that subsystem.
<!-- * Contain all necessary command factories. -->

```java
package frc.robot.subsystems.accelerator;

import edu.wpi.first.wpilibj2.command.Command;
import edu.wpi.first.wpilibj2.command.SubsystemBase;
import org.littletonrobotics.junction.Logger;

public class Accelerator extends SubsystemBase {
  
  private final AcceleratorIOInputsAutoLogged inputs = new AcceleratorIOInputsAutoLogged();
  private final AcceleratorIO io;

  public Accelerator(AcceleratorIO io) {
    this.io = io;
  }

  @Override
  public void periodic() {
    io.updateInputs(inputs);
    Logger.processInputs("Accelerator", inputs);
  }

  private void stop() {
    io.setVoltage(0.0);
  }
}
```
