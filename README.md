//KCP _ACSv7.02 - Root Settings Stock Bike
//(c)2014 Karyn Vaher - All Rights Reserved
//This script set, current or previous versions, is only for redistribution as part of a scripted vehicle, with permissions set to NO MOD and NO TRANSFER
//Resale of any section of this code or emulation of the unique operational flow of this system for resale is in violation of software copyright and subject to DMCA
//Code is not to be exported from Second Life to alternate grids. Exceptions granted to any or all conditions only by commercial licensing agreement.

//Main Feature & Menu Customizing
integer         EditGears =         TRUE;   // FALSE to disable changing/editing of gears from menu.
integer         MenuControls =      TRUE;   // FALSE to disable > Controls menu completely
integer         Resizable=          TRUE;   // TRUE for Resizer. FALSE for no resizer.
integer         TurboAvailable =    FALSE;   // FALSE to remove TURBO option from the menu.
integer         AutoAvailable =     TRUE;   // FALSE to remove automatic transmission option from the menu 
integer         FlightEnabled =     TRUE;   // if FALSE, no flight mode can be activated or displayed in menu.
integer         HideBurnout =       FALSE;   // if TRUE, burnout is removed from the menu.
integer         DisableMenu =       FALSE;  // if TRUE, vehicle menu will not trigger on touch
integer         RecordReturn =      FALSE;   // if TRUE, Record & Return for record position replace Horn & Burnout on vehicle menu page

//Custom Options
integer         FixedCam =          FALSE; // TRUE to use custom cam settings in the Fixed_Camera() routine below:
integer         ArcadeReverse =     FALSE; // TRUE to change back arrow to reverse instead of brake. 
integer         Single_Position =   FALSE; // If TRUE there is only one position adjustment. All poses must be rendered at the same position for this to work.
integer         PassengerSitClick = TRUE;  // If TRUE the passenger prim(s) (if installed) will be set to sit on touch.
integer         ManualPrimShapes  = FALSE; // If TRUE, automatic prim shapes/mesh detection is disabled. Use if you set your prim shapes manually.

//Customizable Messages
string          Msg_Ride=         "Ride";       //Command to ride  chopper on Pie Menu
string          Msg_Start=        "";           //Greeting message. Set to "" to disable. 
string          Msg_End=          "Thanks for the ride.";//End message when exiting. Set to "" to disable.
string          Demo_Text=        "";
string          Locked =          "";     //Set to "" for no message in floating text
string          Unlocked =        "";   //Set to "" for no message in floating text
string          Greetings =       "Greetings";

//combat system driver firing linkset messages. Linkset message firemessage sent on firechan when firing key combo is used (shift+back arrow)
integer         firechan =          3000;       //K-Damage system uses link channel 3000. For vice, set to 1.
string          firemessage =       "gun ctrl"; //K-Damage requires only blank message "". for VICE use "gun ctrl"
// These next 3 are only for use with VICE or other non K-Damage systems along with the Burst Control script.
integer         supresschan =       0;          //For VICE set to 0
string          supressmessage =    "gun ctrl"; // for VICE use "gun ctrl"
float           burstlength =       0.5;        // length of automatic weapons burst fire before shutoff

/////////////////////////////////////////////////////Engine Stuff/////////////////
integer         RECOVER    =        TRUE;   //FALSE makes up+down arrow keys trigger NOS boost. TRUE makes up+down arrow keys RECOVER/lift
float           RecoverHeight   =   3.0;    //height for recover activated by keys if turned on
integer         StartingGear=       1;      //The default gear to start in. Normally 1. 
integer         AutoDropToFirst =   TRUE; // If TRUE, drops vehicle to StartingGear if vehicle slows to idle speed.
integer         InverseReverse=     FALSE;  //Invert your reverse direction controls.
integer         StartParked =       FALSE;  //TRUE if you do not want the engine to start on driver sit.
integer         TurnWhileStopped=   TRUE;   //TRUE to turn when stopped. FALSE so you cannot rotate in place without power. Change from > Extras menu
integer         SEOB =              TRUE;   //set to TRUE to silence the idle/engine when engaging BURNOUT (not skid)
integer         O_S_C=              FALSE;   //SHIFT STYLE. Default FALSE. TRUE to use E/C keys for shifting instead of shift + arrowkeys.
integer         Leveler =           FALSE;  //Helps climb over the top of steep inclines with downward tilt.
integer         ForceLevel =        FALSE;  //If TRUE, forces vehicle not to tilt or lean. For large boats, etc.

//Advanced Tweaks for your face
float           Start_Sound_Delay=  0.5;    // In seconds. Example: 0.5, 2.3. Time after start sound is triggered before engine kicks in.
float           Thr_Idling=         4.0;    //2.5 Velocity cutoff for engine sound idling. 
float           Thr_IdleLevel=      1.5;    //Velocity cutoff of driver idle pose
float           Thr_Skid=           15;     //Velocity that much be reached before bike can skid on turn.
float           Thr_Torque=         6;      //Low End Torque boost Velocity Cutoff Threshhold
float           L_E_T=              2.0;    //amount of extra thrust applied below Thr_Torque
float           GearUp=             60;     //Velocity at which the slow engine sound is replaced by the fast one.
float           Park_Offset =       0.0;    //Vertical offset repositioned/lowered when parked - default 0.0; 

///Headlight and light glow settings
vector          LightColor=         <1.0, 1.0, 1.0>;//<1.0, 1.0, 1.0>
vector          LightIRF=           <1.0, 5.0, 0.5>;//Default <1.0,5.0,0.0>, Light Intensity (0.0 - 1.0), Light Radius (0.1 - 20.0), Light Falloff (0.1 - 2.0).
vector          BrakeLightColor=    <1.0, 0.0, 0.0>;//<1.0, 1.0, 1.0>
vector          BrakeLightIRF=      <1.0, 0.5, 0.5>;//Default <1.0,5.0,0.0>, Light Intensity (0.0 - 1.0), Light Radius (0.1 - 20.0), Light Falloff (0.1 - 2.0).
float           Glow_Level=         0.20;  //0.0 to 1.0 GLOW level for LightSystem prim faces.
float           BeamAlpha =         0.4;  //0.1-1.0 Transparency level for visible light beam faces set up with LightSystem.
float           BeamGlow =          0.05;  //0.1-1.0 Glow level for visible light beam faces set up with LightSystem.
float           IndicatorSpeed =    0.5;   //Turning indicator flash speed.
float           FlightFlash =       1.0;   //Speed for flight lights flashing during flight mode, 0 to disable flash.

// Mouselook settings. If you just want mouselook-style camera, use the SportCam in the camera module.
// In mouselook the left mouse button accelerates. Gears change with L/R arrows. Flight mode stll uses Up/Down arrows for Up/Down.
integer         MBnk=               TRUE;   //  TRUE or FALSE. Turn on banking mode for mouselook
integer         Auto_Mouselook=     FALSE;  // TRUE or FALSE. Turn on mouselook automatically when seating.
integer         Mo_Turn_Power=      500;    //75// Mouselook Turning Power;
integer         MLook_Disable=      FALSE;  //Set to TRUE to disable mouselook altogether

//CornerFX Turn Wheel Smoke Settings. Smoke triggered in wheels with burn keyword.
integer         CornerFXON =           FALSE;
float           CornerFXSmokeThresh=   0.5; //drift smoke turn strength threshhold. Range 0.1 - 3.5 The higher this is, the stronger turn is required
float           CornerFXSmokeVel=      30;  //The velocity before CornerFX smoke can be triggered.
string          CornerFXSound =        "632706df-a5b8-16a4-c5ab-48c8a1ba14cf";// Custom sound for CornerFX. Set to "" for none
float           CornerFXVolume=        0.4; //CornerFX sound Volume range 0.0 - 1.0

//These settings are what the vehicle starts with and returns to when Reset from the controls menu:
//Steering
float           Init_Pwr_Turn =         5.0;    //6.0 Initial turning strength (5.0 standard) 
float           Init_Turn_Bonus =       0.41;   // Additional accrued turning power value. Increase for turning boost. Default 0.33, can set to 0.
float           Init_VelMult =          0.10;   //0.1 Steering Velocity Multiplier
//Additional Physics Forces
float           Init_Lev_Bank =         5.0;    // Initial banking force (5.0 standard) 
integer         Init_Gravity    =       2;      // Gravity Multiplier (whole number) default 1
integer         Init_DownForce =        0;      //Additional downward pressure (default 0)
//Controls
integer         Init_Wheelie_Up =       50;     //Strength up wheelie lift
integer         Init_Wheelie_Down =     100;    //Strength nose down / down wheelie (stoppie power)
float           Init_Lev_NOS =          250;    //Nitrous Burst Level. Start at 100.Crank it up! Set to 0 to disable.
float           Init_Pwr_Skid =         200;    //How much bike turns during skid. INCREASE to skid further (default 25)
float           Init_Time_Skidder =     80;     //20 Length of Skid
float           Init_Pwr_Brake =        10.0;   // default braking power. Range 0-10. Default 10.0.
float           Init_Lev_Turbo =        20;     //Turbo power
integer         Init_Reverse =          10;     //10 Reverse gear power
float           BackTurn =              15;     //Back Arrow+Turn Turning Power when stopped.
float           BaseTurn =              20;     //Base forward power on turning
list            Init_List_Gears =       [45, 65, 85, 110, 130, 200, 600]; //Default list of gears! [40, 55, 65, 80, 95, 110];
float           Spin_Rate =             0.75;   //Wheel Spin Speed Multiplier, default 1.0. Lower for slower wheel spin rate (0.5) or faster (1.5)
float           Init_Lev_VAttrac =      7.0;    // Range 1-10 
float           Init_Resist =           0.21;   //0.21//The lower, the less steering resistance. Useful to correct oversteering
float           Init_Decay =            1.2;    //1.5//Forward engine Decay/Friction. Less = more Decay/Friction.   
float           Init_Inertia =          0.3;    //0.3;
float           Init_Drift =            0.2;    //4.0 Default  
integer         Init_PowerSlide =       0;      //PowerSlide. Permanently on turn slide
integer         Init_ShiftSlide =       30;     //ShiftSlide key control for O_S_C mode. Crank it up!
integer         Init_BurnTime =         25;     //Value for length of burnout before it shuts off automatically. (whole number)

//Additional Wheel Script Settings
integer         PivotAngleOffset =      -15;    //(whole number) Steering angle adjustment for Pivoting Wheels.
float           Init_Camber =           0.0;    //amount of wheel camber for (Pivoting & Fixed Wheel scripts) Set to 0 for motorcycle.
integer         CamberAdjust =          TRUE;   //adds camber adjustment to >Controls,>Steering,>More menu.
integer         WheelVibration =        FALSE;  //TRUE/FALSE for wheel vibration.
float           VibrationLevel =        0.03;   //Wheel Vibration Level (default 0.03)
vector          SuspensionBounce =      <0.0, 0.0, 0.15>; //Offset value for suspension bounce (use the Z value in most cases)
float           SuspensionSway =       -0.1;    //Tunes the suspension movement level on inclines.

//Optional Animation Timers
float           Start_Length       =  2.5;      //time in seconds before switching from start animation to idle pose (examples: 2 , 4.75, 0.3)
float           Wheelie_Length     =  1.0;      //time in seconds before switch from wheelie pose/animation back to ride pose (examples: 1.5, 6, 0.5, 45)

//OPTIONAL BOAT SETTINGS
integer         B_Mode =            FALSE;  //Set to TRUE for BOAT mode. Set to FALSE for normal bike/car/ground vehicle
float           F_Height =          0.15;   //Boat Floating HEIGHT (default 0.25);
float           NoseUp =            0;      // try 20 degrees. degrees for boat nose lift on power. Only for boat mode, not Amphibian mode
float           Rez_Offset =        -0.0;   //amount to offset on rez. Lower your boat into the water on rez.

//Flight Mode Settings
integer         Helicopter =       TRUE;   //vehicle operates only in flight mode
list            List_Flightspeeds=  [20,40,60,100,200];// Flight Speeds/gears for flight mode. Add as many as you need. [30,50,75,100]
float           P_FlUpDown=         15;     // strength of up and down flight
float           P_FlTurn=           5;      // strength of flight turn
integer         Flight_Bank=        30;     //Amount of flight mode bank/angle
float           FlightBoost=        20.0;   //initial push up when switching to flight mode, set to 0.0 to disable.

//SOUND UUIDS. 
//Sounds_1 - Customize your sound sets: Right click on full perm sound in your inventory and choose Copy Asset UUID and paste beteen the quotes:
string          Sound_1_Startup =   "756eb9c7-9a96-4f80-79ac-c6e5492b39ad"; //Sound to play when engine starts
string          Sound_1_Turnoff =   "898e3499-51e5-194f-e21e-a76edf38b9c6"; //Sound to play when engine stops
string          Sound_1_Flight=     "ca173474-c56b-57bb-4701-e80d4c455857"; //Sound to play while flying
string          Sound_1_Horn =      "f5cab6f5-f8ff-40d5-c466-467f036be078"; //Horn sound.
string          Sound_1_Idle =      "9a01ccd2-707a-1809-a156-ed145394de14"; //Sound to play when idling
string          Sound_1_RunningLow ="ca173474-c56b-57bb-4701-e80d4c455857"; //Sound to play while driving slow. 
string          Sound_1_RunningHigh="430b0a64-68e8-b396-cb7d-bcca2d96744f"; //Sound to play while driving fast. 
string          Sound_1_Rev =       "ca173474-c56b-57bb-4701-e80d4c455857"; //Sound to play for engine rev/wheelie
string          Sound_1_Skidder =   "27aa2727-21e6-4823-c1b0-d6e34ebb0e32"; //Sound to play during skidding
string          Sound_1_GearChange ="a457fe67-f988-17cc-1d15-09815a23def6"; //Sound to play for gear switching.
string          Sound_1_Burnout =   ""; //Burnout Sound
string          Sound_1_Reverse =   "";

//Sounds_2. Optional Second Set = set all to "" if not in use. Leave as is or you can use duplicates from 1st set.
string          Sound_2_Startup =   "7acbca2d-b1eb-ce78-ab19-fb61bcbe3cf7"; //Sound to play when engine starts
string          Sound_2_Turnoff =   "7a8a1bd5-5078-6aaf-2eb0-276f06d88df0"; //Sound to play when engine stops
string          Sound_2_Flight=     "67e84be0-c35c-dbd9-9364-8734543e1dc3"; //Sound to play while flying
string          Sound_2_Horn =      "f5cab6f5-f8ff-40d5-c466-467f036be078"; //Horn sound.
string          Sound_2_Idle =      "b7260e35-48f1-a30a-7769-3f165f512db1"; 
string          Sound_2_RunningLow ="5bd53f1a-aa63-30f7-19bf-47ae8b7ce0b0"; 
string          Sound_2_RunningHigh="4c9678a1-2b47-1a66-137e-a21f990b6abc"; 
string          Sound_2_Rev =       "33defb73-9654-7e19-d67c-fecf6baf5686"; 
string          Sound_2_Skidder =   "27aa2727-21e6-4823-c1b0-d6e34ebb0e32"; 
string          Sound_2_GearChange ="4849ff69-0280-815f-97e5-4a849344d05f";
string          Sound_2_Burnout =   "cbd14dd2-b281-6895-0b9e-f5d1264193e8";
string          Sound_2_Reverse =   "";

//Nitrous boost sound. Only tiggered if NOS/Recover is switched to Nitorus Boost from the menu (fwd+back arrow)
string          Nitrous =           "a471db3a-9038-320c-d1c4-52e4293841d9"; //Triggered on boost
string          DoorOpen =          "18963ebb-00b6-cca5-8a91-2aa9b24f03ae"; //Triggered on Door Opening
string          DoorClosed =        "6d7986d9-140b-e1c6-de07-ab85efa7f5d7"; //Triggered on Door Closing
string          TrunkOpen =         "4de6a8be-ba29-b2d7-2e9e-cf16b872025e"; //Triggered on Trunk Opening - assigned doorsystem prim with trunk keyword
string          TrunkClosed =       "b9c3a0c2-d8e1-2d15-a9cc-457686f45e19"; //Triggered on Trunk Closing - assigned doorsystem prim with trunk keyword
string          HoodOpen =          "6710740d-0c6a-cab2-8dd6-7bac4bdf543b"; //Triggered on Hood Opening - assigned doorsystem prim with hood keyword
string          HoodClosed =        "c11e5ceb-3cac-e7a3-0486-9b652b2fb797"; //Triggered on Hood Closing - assigned doorsystem prim with hood keyword
string          Window =            "f4f0a829-c448-02be-dbb4-70d21db4c288"; //Triggered on Power Window
string          Indicators =        ""; //6b0d93cb-1a3b-2739-84e7-735ed32b01af//Triggered each time turning indicators manually activated.
string          Wipers =            "8f2c1da2-7ea9-9a18-4880-de5ad6aa6e0b"; //Triggered each time windshield wipers make a pass
string          InteriorBell =      "4abf8ffb-68da-959d-3aa3-852349648f99"; //loops when a door is open and engine is off
string          LockSound =         "631eaf10-3a19-da5e-a743-a4943262f4aa"; //Triggered on Lock/Unlock
//
key             Alarm_Siren=  "1e663342-08dd-fb39-a421-d207cc29f76f";// Alarm Siren. Set to "" for silence. Default:"1e663342-08dd-fb39-a421-d207cc29f76f"
key             Alarm_Switch= "2bb8f6cd-c6d2-210a-8b83-5b1811dc0692"; //Alarm On/Off sound. Set to "" for silence. Default: "2bb8f6cd-c6d2-210a-8b83-5b1811dc0692"
integer         Alarm_Time=   30; // Length of alarm sequence in seconds.

///Basic Sit. Optional single sit system for use without ROOT SIT script or other sit system.
integer         BasicSit    =           FALSE; //Set to TRUE if you do not want to use the ROOT SIT or other sit script and want to use this basic built-in sit
vector          BasicPosition =         <0.0,0.0,2.5>;  //Position relative to root to place passenger
vector          BasicRotation =         <0.1,0.0,0.0>;  //Rotation of the avatar, in degrees
string          BasicAnim =             "" ;            //Driver animation. Must be present in the root prim.

// DO NOT CHANGE THE SETTINGS BELOW OR GRIEFERS WILL COPYBOT YOUR AVATAR AND DELETE YOUR INVENTORY
// AFTER THAT, THEY WILL PERMANANTLY TURN YOUR AVATAR INTO A BABBOON USING SPECIAL SECRET CODES
// Customization of handling and camera settings are done in the engine script. 
// System variables: Don't toy with them. They may not be what they seem.

integer SmoothDoorSteps=   20;  //range 1-20. Speed for single prim doors and power windows (BETA!)
list setlist;
string Curr_Pack="Sounds_1";
string Snd_Flight;
string Snd_Horn;
float Lev_VAttrac = 6.0; 
integer DownForce = 1;
float Init_Lev_Volume=1.0;
float Resist = 0.17;
float Decay = 1.5;
float Inertia = 0.3;
float Drift=0.5;
float Camber;
integer G_Pg =1;
integer Sending;
integer LId;
integer ATransMult;
key MenuKey;
list CMU;
string CMT="Select";
string Text_MenuSounds="Sounds\nCurrent Set: Sounds_1";
list List_Gears =[30];
list PackList;
list Menu_Sounds = ["Sounds_1","Sounds_2","> Back"];
integer repid=904;
string backer=" ";

//To bypass the built-in camera system and use your own, set FixedCam to TRUE above and pase your favorite  camera settings here:
Fixed_Camera() //Editing this will do nothing unless you disable the built-in camera and set FixedCam to TRUE above 
{
    llSetCameraParams ([
    CAMERA_ACTIVE, 1, // 1 is active, 0 is inactive
    CAMERA_BEHINDNESS_ANGLE, 45.0, // (0 to 180) degrees
    CAMERA_BEHINDNESS_LAG, 0.5, // (0 to 3) seconds
    CAMERA_DISTANCE, 6.0, // ( 0.5 to 10) meters
    //CAMERA_FOCUS, <0,0,5>, // region relative position
    CAMERA_FOCUS_LAG, 0.05 , // (0 to 3) seconds
    CAMERA_FOCUS_LOCKED, FALSE, // (TRUE or FALSE)
    CAMERA_FOCUS_THRESHOLD, 0.0, // (0 to 4) meters
    CAMERA_PITCH, 20.0, // (-45 to 80) degrees
    //CAMERA_POSITION, <0,0,0>, // region relative position
    CAMERA_POSITION_LAG, 0.1, // (0 to 3) seconds
    CAMERA_POSITION_LOCKED, FALSE, // (TRUE or FALSE)
    CAMERA_POSITION_THRESHOLD, 1.0, // (0 to 4) meters
    CAMERA_FOCUS_OFFSET, <0,0,2> // <-10,-10,-10> to <10,10,10> meters
    ]);
}

Physics_Section(integer mode) 
    {
        llSetVehicleFlags(0xFFFFFFFF);llMessageLinked(LINK_SET,197,(string)mode,"");        
        if (!mode)
        {
            //CAR & BIKE PHYSICS
            llSetVehicleType(VEHICLE_TYPE_CAR);
            llSetVehicleFloatParam(VEHICLE_ANGULAR_DEFLECTION_EFFICIENCY, 0.2);
            llSetVehicleFloatParam(VEHICLE_LINEAR_DEFLECTION_EFFICIENCY, 1.0);
            llSetVehicleFloatParam(VEHICLE_ANGULAR_DEFLECTION_TIMESCALE, 0.01);//0.05
            llSetVehicleFloatParam(VEHICLE_LINEAR_DEFLECTION_TIMESCALE, 0.10);
            llSetVehicleFloatParam(VEHICLE_LINEAR_MOTOR_TIMESCALE, 2);//4
            llSetVehicleFloatParam(VEHICLE_LINEAR_MOTOR_DECAY_TIMESCALE, Inertia);
            llSetVehicleFloatParam(VEHICLE_ANGULAR_MOTOR_TIMESCALE, Resist);//.21
            llSetVehicleFloatParam(VEHICLE_ANGULAR_MOTOR_DECAY_TIMESCALE, 0.2);
            llSetVehicleVectorParam(VEHICLE_LINEAR_FRICTION_TIMESCALE, <Decay, Drift, 2> );// <1.5, 0.5, 2.0> 
            llSetVehicleVectorParam(VEHICLE_ANGULAR_FRICTION_TIMESCALE, <0.01,  5.1, 2.5> );//<4.0,  1.5, 0.5> );
            llSetVehicleFloatParam(VEHICLE_VERTICAL_ATTRACTION_EFFICIENCY, Lev_VAttrac/10);//0.6
            llSetVehicleFloatParam(VEHICLE_VERTICAL_ATTRACTION_TIMESCALE, 0.4);//L_Ban/10
            llSetVehicleFloatParam(VEHICLE_BANKING_EFFICIENCY, 0.99);//0.99
            llSetVehicleFloatParam(VEHICLE_BANKING_TIMESCALE, 0.01);
            llSetVehicleFloatParam(VEHICLE_BANKING_MIX, 0.5);
            llSetVehicleFloatParam(VEHICLE_BUOYANCY, -0.1);
            llSetVehicleFloatParam(VEHICLE_HOVER_HEIGHT, 0);
            llSetVehicleFloatParam(VEHICLE_HOVER_EFFICIENCY, 0);//.5
            llSetVehicleFloatParam(VEHICLE_HOVER_TIMESCALE, 180);//.4
            llRemoveVehicleFlags(VEHICLE_FLAG_HOVER_WATER_ONLY | VEHICLE_FLAG_HOVER_UP_ONLY | VEHICLE_FLAG_LIMIT_ROLL_ONLY);
            llSetVehicleFlags(VEHICLE_FLAG_NO_DEFLECTION_UP | VEHICLE_FLAG_LIMIT_ROLL_ONLY| VEHICLE_FLAG_LIMIT_MOTOR_UP);
            llSetForce(<0,0,-DownForce>,FALSE);   
        }
        else
        if (mode)
        {   //BOAT PHYSICS
            llSetVehicleType(VEHICLE_TYPE_BOAT);
            llSetVehicleFloatParam(VEHICLE_ANGULAR_DEFLECTION_EFFICIENCY, 1.0);
            llSetVehicleFloatParam(VEHICLE_LINEAR_DEFLECTION_EFFICIENCY, 1.0);
            llSetVehicleFloatParam(VEHICLE_ANGULAR_DEFLECTION_TIMESCALE, 0.10);
            llSetVehicleFloatParam(VEHICLE_LINEAR_DEFLECTION_TIMESCALE, 0.10);
            llSetVehicleFloatParam(VEHICLE_LINEAR_MOTOR_TIMESCALE, 5);
            llSetVehicleFloatParam(VEHICLE_LINEAR_MOTOR_DECAY_TIMESCALE, 0.2);
            llSetVehicleFloatParam(VEHICLE_ANGULAR_MOTOR_TIMESCALE, .21);
            llSetVehicleFloatParam(VEHICLE_ANGULAR_MOTOR_DECAY_TIMESCALE, 0.2);
            llSetVehicleVectorParam(VEHICLE_LINEAR_FRICTION_TIMESCALE, <6, 0.5, 1000.0> );
            llSetVehicleVectorParam(VEHICLE_ANGULAR_FRICTION_TIMESCALE, <10.0, 10.0, 0.5> );
            llSetVehicleFloatParam(VEHICLE_VERTICAL_ATTRACTION_EFFICIENCY, 0.5);//0.50
            llSetVehicleFloatParam(VEHICLE_VERTICAL_ATTRACTION_TIMESCALE, 0.80);//0.40
            llSetVehicleFloatParam(VEHICLE_BUOYANCY, 1.0);
            llSetVehicleFloatParam(VEHICLE_BANKING_EFFICIENCY, 0.99);
            llSetVehicleFloatParam(VEHICLE_BANKING_TIMESCALE, 0.1);
            llSetVehicleFloatParam(VEHICLE_BANKING_MIX, 0.5);
            llSetVehicleFloatParam(VEHICLE_HOVER_HEIGHT, F_Height);
            llSetVehicleFloatParam(VEHICLE_HOVER_EFFICIENCY, 0.3);//.5
            llSetVehicleFloatParam(VEHICLE_HOVER_TIMESCALE, 0.9);//.4
            llRemoveVehicleFlags(VEHICLE_FLAG_HOVER_TERRAIN_ONLY  | VEHICLE_FLAG_LIMIT_ROLL_ONLY | VEHICLE_FLAG_HOVER_GLOBAL_HEIGHT);
            llSetVehicleFlags(VEHICLE_FLAG_NO_DEFLECTION_UP | VEHICLE_FLAG_HOVER_WATER_ONLY  | VEHICLE_FLAG_HOVER_UP_ONLY  | VEHICLE_FLAG_LIMIT_MOTOR_UP ); 
            llSetForce(<0,0,0>,FALSE);   
        }
        llSetVehicleRotationParam(VEHICLE_REFERENCE_FRAME, ZERO_ROTATION);
        llSetVehicleVectorParam (VEHICLE_LINEAR_MOTOR_OFFSET,ZERO_VECTOR);
    }

Flight_Physics() 
    {
          llSetVehicleFlags (0xFFFFFFFF);
          llSetVehicleType (VEHICLE_TYPE_AIRPLANE);
          //lSetVehicleVectorParam(VEHICLE_ANGULAR_MOTOR_DIRECTION, <0.0, 0.0, 0.0>);
          llSetVehicleFloatParam (VEHICLE_ANGULAR_DEFLECTION_EFFICIENCY, 1.0);
          llSetVehicleFloatParam (VEHICLE_LINEAR_DEFLECTION_TIMESCALE, 10);//0.1
          llSetVehicleFloatParam (VEHICLE_LINEAR_MOTOR_TIMESCALE, 1.0);
          llSetVehicleFloatParam (VEHICLE_LINEAR_MOTOR_DECAY_TIMESCALE, 1.0);
          llSetVehicleFloatParam (VEHICLE_ANGULAR_MOTOR_TIMESCALE, 1.0);
          llSetVehicleFloatParam (VEHICLE_ANGULAR_MOTOR_DECAY_TIMESCALE, 1.0);
          llSetVehicleVectorParam (VEHICLE_LINEAR_FRICTION_TIMESCALE, <10.0, 0.5, 10.0>);
          llSetVehicleVectorParam (VEHICLE_ANGULAR_FRICTION_TIMESCALE, <0.5,0.5,0.5>);
          llSetVehicleFloatParam (VEHICLE_VERTICAL_ATTRACTION_EFFICIENCY, 0.5);//0.50
          llSetVehicleFloatParam (VEHICLE_VERTICAL_ATTRACTION_TIMESCALE, 1.0);//0.40
          llSetVehicleFloatParam (VEHICLE_HOVER_HEIGHT, 0.0);//0.0
          llSetVehicleFloatParam (VEHICLE_HOVER_EFFICIENCY, 0.0);//.5/0.3
          llSetVehicleFloatParam (VEHICLE_HOVER_TIMESCALE, 180);//.4/180
          llSetVehicleFloatParam (VEHICLE_BUOYANCY, 0.998);//1
          llSetForce(<0.0,0.0,0.0>, FALSE );
          llRemoveVehicleFlags(VEHICLE_FLAG_NO_DEFLECTION_UP | VEHICLE_FLAG_HOVER_WATER_ONLY | VEHICLE_FLAG_HOVER_TERRAIN_ONLY | VEHICLE_FLAG_HOVER_UP_ONLY | VEHICLE_FLAG_LIMIT_MOTOR_UP | VEHICLE_FLAG_LIMIT_ROLL_ONLY);
          llSetVehicleFlags (VEHICLE_FLAG_HOVER_GLOBAL_HEIGHT );
    }
/////////////////////////////////////////////////////////////////////////////////////////////
///////////////////////////////END RECOMMENDED EDITABLE SECTION//////////////////////////////
/////////////////////////////////////////////////////////////////////////////////////////////
           
sound_off(string pack)
{
    Curr_Pack=pack;Text_MenuSounds="Sound Sets\nCurrent: "+pack;list b;
    if (Curr_Pack=="Sounds_1"){
        b=[Sound_1_Idle, Sound_1_Rev, Sound_1_RunningLow, Sound_1_RunningHigh, Sound_1_Startup, Sound_1_Turnoff,
        Sound_1_GearChange, Sound_1_Skidder, Sound_1_Burnout, Sound_1_Reverse];Snd_Flight=Sound_1_Flight;Snd_Horn=Sound_1_Horn;}    
    else if (Curr_Pack=="Sounds_2"){
        b=[Sound_2_Idle, Sound_2_Rev, Sound_2_RunningLow, Sound_2_RunningHigh, Sound_2_Startup, Sound_2_Turnoff,
        Sound_2_GearChange, Sound_2_Skidder, Sound_2_Burnout, Sound_2_Reverse];Snd_Flight=Sound_2_Flight;Snd_Horn=Sound_2_Horn;}
    else llMessageLinked(LINK_THIS,715,Curr_Pack,"");    
    if (b!=[]){llSleep(1);
        list a=[563,564,565,566,567,568,569,570,571,574];integer x;
        do {llMessageLinked(LINK_THIS,llList2Integer(a,x),llList2String(b,x),llList2Key(b,x));++x;}while (x<(a!=[]));}      
}

float GetSet(integer x) {return llList2Float(setlist,x);}PutSet(integer x,float y){setlist=llListReplaceList(setlist,[GetSet(x)+y],x,x);}
ReSet(integer x, float y){setlist=llListReplaceList(setlist,[y],x,x);}L_P(integer linx, integer num, list tisl){llMessageLinked(linx,num,llList2CSV(tisl),"");}

init_settings()
    {   
        setlist =[
        Init_Pwr_Turn, Init_Lev_Bank, Init_Turn_Bonus, Init_PowerSlide, Init_Wheelie_Up, Init_Wheelie_Down, Init_ShiftSlide,
        Init_Pwr_Skid, Init_Time_Skidder, Init_Pwr_Brake, Init_Reverse, Init_Lev_Volume, Init_Lev_Turbo, Init_Lev_NOS, Init_Gravity, Init_BurnTime, Init_VelMult,Init_Camber];
        Resist=Init_Resist;Decay=Init_Decay;Inertia=Init_Inertia;Lev_VAttrac = Init_Lev_VAttrac;Drift = Init_Drift;List_Gears=Init_List_Gears;
        DownForce=Init_DownForce;Camber=Init_Camber;if (DownForce<0) DownForce=0;G_Pg=1;llSleep(0.5);send();
    }

send()
{
    Sending=TRUE;PackList=[];L_P(LINK_THIS,718,List_Gears);integer d;list nums=[1505,655,850,725,388,389,295,454,198,703,1505,893];
    list mess=[Spin_Rate, 1, ManualPrimShapes, ArcadeReverse, Start_Length, Wheelie_Length, Single_Position, SmoothDoorSteps,
    FixedCam, Helicopter, Spin_Rate, PassengerSitClick];    
    do {llMessageLinked(LINK_SET, llList2Integer(nums,d), llList2String(mess,d), (key)"6");++d;}while (d<(nums!=[]));        
    L_P(LINK_SET,1540,setlist);
    L_P(LINK_SET,273,[CornerFXON,CornerFXSmokeThresh,CornerFXSmokeVel,CornerFXVolume,MenuControls,Resizable,TurboAvailable,WheelVibration,VibrationLevel,SuspensionSway,PivotAngleOffset,AutoAvailable,HideBurnout,RecordReturn]);    
    L_P(LINK_THIS,1525,[RECOVER,StartingGear,InverseReverse,StartParked,TurnWhileStopped,SEOB,O_S_C,firechan,firemessage,supresschan,supressmessage,burstlength]);    
    L_P(LINK_THIS,1532,[RecoverHeight,Start_Sound_Delay,Thr_Idling,Thr_IdleLevel,Thr_Skid,Thr_Torque,L_E_T,GearUp,ATransMult,Park_Offset,BackTurn,BaseTurn,ForceLevel]);    
    L_P(LINK_THIS,1533,[MBnk,Auto_Mouselook,Mo_Turn_Power,MLook_Disable,P_FlUpDown,P_FlTurn,Flight_Bank,FlightBoost,AutoDropToFirst,Leveler]);    
    L_P(LINK_THIS,1535,List_Flightspeeds);
    L_P(LINK_THIS,1536,[Msg_Ride,Demo_Text,Locked,Unlocked]);
    L_P(LINK_THIS,1542,[LightColor.x,LightColor.y,LightColor.z,LightIRF.x,LightIRF.y,LightIRF.z,BeamAlpha,BeamGlow,IndicatorSpeed,FlightFlash,BrakeLightColor.x,BrakeLightColor.y,BrakeLightColor.z,BrakeLightIRF.x,BrakeLightIRF.y,BrakeLightIRF.z]);
    L_P(LINK_SET,1543,[Alarm_Siren,Alarm_Switch,Alarm_Time,DisableMenu]);
    llMessageLinked(LINK_SET,580,(string)Glow_Level,"");llMessageLinked(LINK_SET,194,(string)SuspensionBounce,"");
    llMessageLinked(LINK_THIS,1537,Msg_Start,"");llMessageLinked(LINK_THIS,1538,Msg_End,"");llMessageLinked(LINK_THIS,1539,Greetings,"");
    if (B_Mode) llMessageLinked(LINK_SET, 797, (string)NoseUp, "");
    if (!FlightEnabled && !Helicopter) llMessageLinked(LINK_THIS,704,"","");
    if (Curr_Pack=="Sound_1"|Curr_Pack=="Sound_2") sound_off(Curr_Pack);
    else llMessageLinked(LINK_THIS,715,Curr_Pack,"");
    L_P(LINK_THIS,541,[InteriorBell,Wipers,Indicators,DoorClosed,DoorOpen,Window,Nitrous,CornerFXSound,TrunkClosed,TrunkOpen,HoodClosed,HoodOpen]);
    llSleep(0.3);llMessageLinked(LINK_THIS, 712, "", "");Sending=FALSE;
}

PAS(float valx, string golden)
{
    llSleep(0.3);if (golden != ""){
    if (llGetOwner()==MenuKey) llOwnerSay(golden +": "+(llGetSubString((string) valx,0,3)));else llWhisper(0,golden +": "+(llGetSubString((string) valx,0,3)));}
    L_P(LINK_SET,1540,setlist);
}
        
C_M() {if ((CMU!=[])>12) CMU=llList2List(CMU,0,11);llListenRemove(LId);integer DChan=(-1*(integer)("0x"+llGetSubString((string)llGetKey(),-5,-1)));LId=llListen(DChan,"",MenuKey,"");llDialog(MenuKey,"\n"+CMT,CMU,DChan);llSetTimerEvent(60);}

list sky = ["> Banking","> Gravity","> Reverse","> Brake","> Skid","> Turbo","> More","> Controls <","> Steering"];

list DoMenu(integer j)
{
    list D_List;
    if (j==0) D_List= ["Bank-","Bank+","Reset Bank"]+[backer]+[ "Zero Bank"];//Banking
    else if (j==1) D_List=["Reset VAt"]+[backer]+["VAttrac-","Gravity-","DownForce-","VAttrac+","Gravity+","DownForce+"];//Gravity
    else if (j==2) D_List=["Reverse-","Reverse+","Reset Rev"]+[backer]+["Rev Style"];//Reverse
    else if (j==3) D_List=["> Back","Reset Brake","Brake-","Decay-","Inertia-","Brake+","Decay+","Inertia+"];//Brake
    else if (j==4) D_List=["SkidPwr-","SkidPwr+","SkidTime-","SkidTime+", "Reset Skid","NOS-", "NOS+", "Reset NOS","BurnTime-","BurnTime+"];//Skid
    else if (j==5) D_List=["Reset Turbo","Rst Wheelie","Turbo-","Wheel_Up-","Wheel_Dn-","Turbo+","Wheel_Up+","Wheel_Dn+"];//Turbo
    else if (j==6) 
    {
        D_List=["> Steering"," ","Resist-","Drift-","PowerSlide-","Resist+","Drift+","PowerSlide+","VelMult-","VelMult+"];//More Steering
        if (CamberAdjust) {D_List=llListReplaceList(D_List,["Camber-"],1,1);D_List+=["Camber+"];}
    }
    else if (j==7) 
    {
        D_List=["> Steering","> Gravity","> Banking","> Turbo"]+[backer]+["> Brake","> Skid", "Reset All","> Gears","Reset Gears", "> Reverse"];//COntrols
        if (!EditGears) D_List = llListReplaceList(D_List, [" "," "], 8, 9); 
    }
    else if (j==8) 
    {
        D_List=["> Back","> More","Steer-","Steer--","ShiftSlide-","Steer+","Steer++","ShiftSlide+","Reset Str","Bonus-","Bonus+"];//Steering 
        if(!O_S_C) {D_List = llListReplaceList(D_List, [" "], 4, 4); D_List = llListReplaceList(D_List, [" "], 7, 7);}
    }
    if(j!=7) D_List=llListInsertList(D_List,["> Controls <"],2);else D_List=llListInsertList(D_List,["> Finished <"],2);
    CMT=llList2String(sky,j);
    return D_List;
}    

list CheckIt(string message)
{
    float r;
    if (llSubStringIndex(message,"++")!=-1) r=2.0;if (llSubStringIndex(message,"--")!=-1) r=-2.0;message=llToLower(message);integer x=-1;list g;
    list things=["steer","bank","bonus","powerslide","wheel_up","wheel_dn","shiftslide","skidpwr",
    "skidtime","brake","reverse","vol", "turbo","nos","gravity","burntime","velmult","camber"];
    list valone= [.1,.5,.01,1,10,10,1,1,1,1,10,0,1,10,1,10,.05,.5];integer p;
    do {if (llSubStringIndex(message,llList2String(things,p))!=-1) {x=p;jump one;}++p;}while (p<(things!=[]));    
    @one; 
    if (x>-1) {g+=[x];if (r==0){if (llSubStringIndex(message,"+")!=-1) g+=[llList2Float(valone,x)];
    else if (llSubStringIndex(message,"-")!=-1) g+=[-llList2Float(valone,x)];}else g+=[r];if ((g!=[])!=2) g=[];}  
    return g;
}

default
{
        
listen(integer channel, string name, key id, string message) 
    {   
        llSetTimerEvent(20);
        MenuKey=id;integer d;integer passthru=0xFFFFFFFF; list g;list w;list i;        
        integer h = llListFindList(sky,[message]);
        if (message == "Zero Bank") i=[1,0.0];
        else if (message == "Reset Bank") i=[1,Init_Lev_Bank];
        else if (message == "Rst Wheelie") {i=[4,Init_Wheelie_Up];ReSet(5,Init_Wheelie_Down);}
        else if (message == "Reset Skid") {i=[7,Init_Pwr_Skid];ReSet(8,Init_Time_Skidder);PAS(GetSet(7), "Skid reset");}
        else if (message == "Reset Rev") i=[10,Init_Reverse];
        else if (message == "Reset Turbo") i=[12,Init_Lev_Turbo];
        else if (message == "Reset NOS") i=[13,Init_Lev_NOS];
        else g=CheckIt(message);  
        if (message == "Drift+") {if (Drift < 1000) Drift+=0.1; w=[message,(string)Drift];}
        else if (message == "Drift-") {if (Drift>0) Drift-=0.1;w=[message,(string)Drift];} 
        else if (message == "Resist+") {Resist+=0.01;w=[message,(string)Resist];}
        else if (message == "Resist-") {if (Resist > 0)Resist-=0.01;w=[message,(string)Resist];}
        else if (message == "Decay+") {Decay+=0.1;w=[message,(string)Decay];}
        else if (message == "Decay-") {if (Decay > 0)Decay-=0.1;w=[message,(string)Decay];}
        else if (message == "Inertia+") {Inertia+=0.1;w=[message,(string)Inertia];}
        else if (message == "Inertia-") {if (Inertia > 0)Inertia-=0.1;w=[message,(string)Inertia];}
        else if (message == "DownForce-") {if (DownForce)--DownForce;w=[message,(string)DownForce];}
        else if (message == "DownForce+") {++DownForce;w=[message,(string)DownForce];}
        else if (message == "Reset Str") {ReSet(0,Init_Pwr_Turn); PAS(GetSet(0),"Steering");ReSet(2,Init_Turn_Bonus);Drift=Init_Drift; 
        PAS(GetSet(2),"Turn Bonus");Resist=Init_Resist;ReSet(3,Init_PowerSlide);Physics_Section(B_Mode);}        
        else if (message == "Rev Style") {ArcadeReverse=!ArcadeReverse;llMessageLinked(LINK_THIS, 725,(string)ArcadeReverse, "");}        
        else if (message == "VAttrac+") {if (Lev_VAttrac < 10) Lev_VAttrac+=0.5;w=[message,(string)Lev_VAttrac];}
        else if (message == "VAttrac-") {if (Lev_VAttrac > 1) Lev_VAttrac-=0.5;w=[message,(string)Lev_VAttrac];}        
        else if (message == "Reset VAt") {Lev_VAttrac=Init_Lev_VAttrac;}
        else if (message == "Reset Brake") {ReSet(9,Init_Pwr_Brake); PAS(GetSet(9), "Brake reset");Inertia=Init_Inertia;Decay=Init_Decay;Physics_Section(B_Mode);}
        else if (message == "> Back")  {llListenRemove(LId);llMessageLinked(LINK_THIS,200,"",MenuKey);d=1;}          
        else if (message == "Reset All") init_settings();
        else if ((message == "Reset Gears")&& EditGears) {List_Gears=Init_List_Gears;llMessageLinked(LINK_THIS,718,llList2CSV(List_Gears),"");}
        else if ((message == "> Gears") && EditGears) {llListenRemove(LId);llMessageLinked(LINK_THIS,500,message,MenuKey);d=1;}
        else if (llSubStringIndex(message,"Sounds_")==0) {sound_off(message);CMU=Menu_Sounds+PackList;CMT=Text_MenuSounds;}
        else if (llListFindList(PackList,[message]) !=0xFFFFFFFF) {Curr_Pack=message;llMessageLinked(LINK_THIS,715,message,"");Text_MenuSounds="Sound Sets\nCurrent: "+Curr_Pack;CMT=Text_MenuSounds;}
        if (g!=[]) {PutSet(llList2Integer(g,0),llList2Float(g,1));PAS(GetSet(llList2Integer(g,0)),message);}
        else
        if (w!=[]) {if (MenuKey==llGetOwner()) llOwnerSay(llList2String(w,0)+": "+llList2String(w,1));else llSay(0,llList2String(w,0)+": "+llList2String(w,1));Physics_Section(B_Mode);}
        else if (i!=[]) {ReSet(llList2Integer(i,0),llList2Float(i,1));passthru=llList2Integer(i,0);}
        else {if (h!=0xFFFFFFFF) CMU=DoMenu(h); else{llListenRemove(LId);d=1;}}
        if (passthru!=0xFFFFFFFF) PAS(GetSet(passthru),message);
        if (!d) C_M();        
}

state_entry()
    {
        if (llSubStringIndex(llGetObjectName(), "Mechanic HUD")!=0xFFFFFFFF){llSetScriptState(llGetScriptName(),FALSE);}
        llMessageLinked(LINK_THIS,repid,llGetScriptName(),"");
        llSleep(0.4);llMessageLinked(LINK_THIS, 655, "1", "");
        if (BasicSit) llSitTarget(BasicPosition, llEuler2Rot(BasicRotation*DEG_TO_RAD));
        Snd_Flight=Sound_1_Flight;Snd_Horn=Sound_1_Horn;
        init_settings();Physics_Section(B_Mode);
        if(!DisableMenu) backer="> Back";
    }     
 
link_message (integer sender_num,integer num,string message,key id) 
    { 
        if (num==100) message=llToLower(message);
        if (message == "controls") {MenuKey=id;CMU=DoMenu(7);C_M();}
        else if (num == 580) Glow_Level = (float)message;
        else if (num == 718) List_Gears=llCSV2List(message);
        else if (num == 388) Start_Length=(float)message;
        else if (num == 389) Wheelie_Length=(float)message;
        else if (num == 686) llTriggerSound (LockSound, GetSet(11) );
        else if ((num == 789| num == 660 | num == 1500) && !Helicopter) Physics_Section(B_Mode);
        else if (message == "sounds") {MenuKey=id;CMU=Menu_Sounds+PackList;CMT=Text_MenuSounds;C_M();}
        else if (message == "horn") llTriggerSound (Snd_Horn, GetSet(11) );
        else if (num == 689 && FlightEnabled) {Flight_Physics();llStopSound();llLoopSound (Snd_Flight,GetSet(11));}
        else if (num == 572) Snd_Flight=id;
        else if (num == 573) Snd_Horn=id;
        else if (num == 678 && message=="X") sound_off(Curr_Pack);
        else if ((num == repid && message!=llGetScriptName())|num == 575) llRemoveInventory(llGetScriptName());
        else if (message == "volume +") {if (GetSet(11) < 1) PutSet(11, 0.1);PAS(GetSet(11),message);}
        else if (message == "volume -") {if (GetSet(11) > 0) PutSet(11,-0.1);PAS(GetSet(11),message);}
        else if (num == 714 && llListFindList(PackList,[message])==0xFFFFFFFF && (PackList!=[])<9) PackList+=[message];
        else if (num == 722 && !Sending) send();
        else if (num == 420) {L_P(LINK_THIS,541,[InteriorBell,Wipers,Indicators,DoorClosed,DoorOpen,Window,Nitrous,CornerFXSound,TrunkClosed,TrunkOpen,HoodClosed,HoodOpen]);L_P(LINK_THIS,1542,[LightColor.x,LightColor.y,LightColor.z,LightIRF.x,LightIRF.y,LightIRF.z,BeamAlpha,BeamGlow,IndicatorSpeed,FlightFlash]);}
        else if (num == 230) {B_Mode=(integer)message;Physics_Section(B_Mode);}
        else if (num==597 && BasicSit) llSitTarget(BasicPosition, llEuler2Rot(BasicRotation*DEG_TO_RAD));
        else if (num == 876 && (integer)message)
        {if (llAvatarOnLinkSitTarget(LINK_THIS)==id){MenuKey=id;if (FixedCam && BasicSit) llRequestPermissions (MenuKey,0x800|0x10);
        else{if (FixedCam) llRequestPermissions (MenuKey,0x800);if (BasicSit) llRequestPermissions (MenuKey,0x10);}}}
    }

timer () {llListenRemove(LId);llSetTimerEvent(0);}on_rez(integer null) {vector x=llGetPos();llSetPos(<x.x,x.y,x.z+Rez_Offset>);}
run_time_permissions(integer ffs) {if (ffs & 0x800) Fixed_Camera();if (ffs & 0x10) {if (BasicAnim!="") llStartAnimation(BasicAnim);}}
}
