
This Code is based on 2021 code from team 1614's very good zero to Autonomous Swerve drive example.

0 to autonomous made the video up top, here is their code https://github.com/SeanSun6814/FRC0ToAutonomous
see also https://github.com/Ellipse6814
please watch the 0 to autonomous Video it has great explantions of concepts in swerve code https://www.youtube.com/watch?v=0Xi9yb1IMyA


If you get errors compiling..
You may need to update vendor libraries, look here for newest json files
https://docs.wpilib.org/en/stable/docs/software/vscode-overview/3rd-party-libraries.html



Note I think they use PWM Analog, and we use SRX encoder so must use DIO port and DutyCycleEncoder class instead of Absolute Analog encoder.

The orig code here uses CanCoder which is deprecated. It should update to CanEncoder I think, or spark max built in encoder.
actually from REV : https://docs.revrobotics.com/sparkmax/software-resources/spark-max-api-information
    C++/Java: Deprecated classes in favor of renamed versions
    C++ users will get cannot declare field to be of abstract type errors until they replace their object declarations with ones for the new classes. Java users will be able to continue to use the old classes through the 2022 season.
    AlternateEncoderType is replaced by SparkMaxAlternateEncoder.Type.
    CANAnalog is replaced by SparkMaxAnalogSensor.
    CANDigitalInput is replaced by SparkMaxLimitSwitch.
    Java: CANEncoder is replaced by RelativeEncoder.
    C++: CANEncoder is replaced by SparkMaxRelativeEncoderandSparkMaxAlternateEncoder`.
    CANPIDController is replaced by SparkMaxPIDController.
    CANSensor is replaced by MotorFeedbackSensor.
    ControlType is replaced by CANSparkMax.ControlType.
    EncoderType is replaced by SparkMaxRelativeEncoder.Type.