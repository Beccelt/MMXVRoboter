package org.usfirst.frc.team20.robot;

import edu.wpi.first.wpilibj.CANTalon;
import edu.wpi.first.wpilibj.CANTalon.FeedbackDevice;
import edu.wpi.first.wpilibj.Gyro;
import edu.wpi.first.wpilibj.IterativeRobot;
import edu.wpi.first.wpilibj.Joystick;
import edu.wpi.first.wpilibj.smartdashboard.SendableChooser;
import edu.wpi.first.wpilibj.smartdashboard.SmartDashboard;
import edu.wpi.first.wpilibj.command.Command;
//import edu.wpi.first.wpilibj.communication.FRCNetworkCommunicationsLibrary;
//import edu.wpi.first.wpilibj.DriverStation;
//import edu.wpi.first.wpilibj.command.Command;
//import edu.wpi.first.wpilibj.command.Scheduler;
//import edu.wpi.first.wpilibj.networktables2.util.Stack;
public class Robot extends IterativeRobot {
	
	private SendableChooser chooser;
	Command autonomousCommand;
	Gyro g1;
	Joystick stick = new Joystick(0);
	CANTalon tal1 = new CANTalon(2);
	
	
	//window motor PID values
	double g1value;
	double p = .5;
	double i = 0.0001;
	double d = .5;
	double ramp = 1500;
	double test;
	double position = 0;

	boolean auto1=false;
	boolean auto2=true;
	boolean auto3=true;

	public void robotInit() {
		
		chooser = new SendableChooser();
		chooser.addDefault("Command 1", 1);
		chooser.addObject("Command 2", 2);
		SmartDashboard.putData("Autonomous Selector", chooser);
		SmartDashboard.putString("DB/String 0", "My 21 Char TestString");
		tal1.setFeedbackDevice(FeedbackDevice.QuadEncoder);
		tal1.changeControlMode(CANTalon.ControlMode.Position);
		tal1.setPosition(0);
		tal1.setPID(p, i, d);
		tal1.setCloseLoopRampRate(ramp);
		tal1.enableControl();
		
		Gyro g1 = new Gyro(1);
		g1.initGyro();
		g1.reset();
		chooser = new SendableChooser();
		
		
		
	}


	public void teleopPeriodic() {

		auto1=true;
		auto2=true;
		auto3=true;
		
		auto1 = SmartDashboard.getBoolean("DB/Button 1");
		if (auto1)
		{
		 SmartDashboard.putString("DB/String 0", "auto***1");
		 SmartDashboard.getString("DB/String 0", "myDefaultData");
		 //Insert Auto1 Code here
		 Autonomous1();
		} 
		else{
			auto1 = false;
		}
		
	
		auto2 = SmartDashboard.getBoolean("DB/Button 2");
		if (auto2)
		{
		 SmartDashboard.putString("DB/String 0", "auto***2");
		 SmartDashboard.getString("DB/String 0", "myDefaultData");
		 //Insert Auto2 Code here
		 Autonomous2();
		}
		else{
			auto2 = false;
		}
		
		
		
		auto3 = SmartDashboard.getBoolean("DB/Button 3");
		if (auto3)
		{
		 SmartDashboard.putString("DB/String 0", "auto***3");
		 SmartDashboard.getString("DB/String 0", "myDefaultData");
		//Insert Auto2 Code here
		 Autonomous3();
		}
		else{
			auto3 = false;
		}
		
		if (stick.getRawButton(1))
			tal1.set(85000 * .25);
		if (stick.getRawButton(2))
			tal1.set(85000 * .50);
		if (stick.getRawButton(4))
			tal1.set(85000 * .75);
		if (stick.getRawButton(3))
			tal1.set(85000);
		if (stick.getRawButton(5))
			tal1.set(0);

		SmartDashboard.putString("Position", "" + stick.getRawAxis(0) * 1);
		SmartDashboard.putString("Encoder Position", "" + tal1.getEncPosition());
		SmartDashboard.putString("Current Position", "" + tal1.getPosition());
		g1value = Math.round(g1.getAngle() * 100) / 100;
		SmartDashboard.putString("DB/String 3", "angle = " + g1value);
		SmartDashboard.getString("DB/String 3", "myDefaultData");
		
	}
	public void Autonomous1(){
		
	}
	public void Autonomous2(){
		
	}
	public void Autonomous3(){
		
	}

	/**
	 * This function is called periodically during test mode
	 */
	public void testPeriodic() {

	}

	/**
	 * This function is called periodically during autonomous
	 */
	public void autonomousInit(){
		
	}
	public void autonomousPeriodic() {
		
	}

}
