
This Code is based on 2021 code from team 1614's very good zero to Autonomous Swerve drive example.

0 to autonomous made the video up top, here is their code https://github.com/SeanSun6814/FRC0ToAutonomous
see also https://github.com/Ellipse6814
please watch the 0 to autonomous Video it has great explantions of concepts in swerve code https://www.youtube.com/watch?v=0Xi9yb1IMyA


If you get errors compiling..
You may need to update vendor libraries, look here for newest json files
https://docs.wpilib.org/en/stable/docs/software/vscode-overview/3rd-party-libraries.html



Note I think they use PWM Analog, and we use SRX encoder so must use DIO port and DutyCycleEncoder class instead of Absolute Analog encoder.

The orig code here used REV CANCoder which is deprecated. It should update to CanEncoder I think, or spark max RelativeEncoder.
actually from REV : https://docs.revrobotics.com/sparkmax/software-resources/spark-max-api-information

to get the 2021 code to compile in late 2022:
    CANCoder was replaced with RelativeEncoder
    normalizeWheelSpeeds was replaced with desaturateWheelSpeeds
    must also replace AnalogInput with DutyCycleEncoder
and of course had to add vendor libs for REV, NavX, Phoenix (might not have needed Phoenix?)

OFFSETS and BUTTONS AND Customizations
Look at Constants.java and update at least:
1. Motor and Encoder indexes to match your chassis
2. Joystick axis and buttons to match your controller
3. Gear ratio and wheel size etc.

Driving:
Robot has 3 modes:
1. Field Oriented AKA Field Centric , joystick controls Robot relative to initial powerup.
2. Robot Oriented AKA Robot Centric AKA Body Fixed, joystick controls Robot relative to Front of Robot, as if driver was sitting in Robot, I believe you hold down a joystick button to force this mode.
3. Autonomous Command, contains a pathing in meters to follow, notice it can turn during pathing if you put in a facing command as an argument. You have to send this command mode, outside of teleop typically.

Joystick Axis (modify in Constants.java)
0/1 for X/Y
4 for steering
Joystick Buttons
1 hold down for Robot Oriented, otherwise Field Oriented.
2 for zero heading (dangerous during competition? consider 2 button press or cover that button ?)



