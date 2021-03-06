Include lists of assumptions and requirements to run software.

4.1.1 User Classes and Characteristics
 Various users will have access to the developed Vibration Analysis Tool. These users
differ based on their frequency of use of the tool, the subset of functions they access,
and their technical expertise. Mainly, the users will either be technicians acquiring
data on site, or expert engineers who would like to look at the acquired data more in
depth and produce the reports containing recommendations to the client. Based on
that, the tool will have to be designed in such a way that allows the technicians to
acquire data easily, at the same time allowing expert engineers to access more detailed
functions. Such detailed functions include adjusting the filter parameters, changing
the predefined acceptance levels used in the reports, adding additional bearings with
new diameters and producing the final reports after making certain expert decisions.
4. Requirements Specification 41
4.1.2 User Documentation
In addition to the Vibration Analysis Tool software, user documentation is provided.
This documentation is in the form of a user manual detailing the various functions
in the tool and how they are used. In addition, the user manual explains how the
various plots are to be read, and how the reports are to be generated and interpreted.
4.1.3 Assumptions
The following is a list of assumptions that the design of the Vibration Analysis Tool
is based on:
1. The tool shall only connect to at most eight sensor units at a time.
2. The sensor units must operate normally at any temperature between -40 and
50 degrees Celsius.
3. The sensor units must operate normally under the circumstances expected at
sites where the analysis is performed.
4. The sensor units must detect g forces anywhere between 0 g and 10 g with a
resolution of 0.01 g.
5. The sensor units must have the capability to read the battery level on the unit
and send it to the computer with the vibration analysis tool.
6. The sensor units must have the capability to read the temperature level surrounding
the unit and send it to the computer with the vibration analysis tool.
7. The sensor units must allow for the changing of the g select upon receiving a
command from the computer with the vibration analysis tool.
8. Data on the sensor unit is to be sampled at a rate of 1000Hz.
9. The PDA interface is designed for a specific PDA.
42 4. Requirements Specification
4.2 Functional Requirements
An application’s functional requirements are those describing its behaviour and are
most likely implemented as functions in the implementation stage. The following are
the functional requirements related to the Vibration Analysis Tool. The requirements
and have been separated into sections based on the feature they deal with.
4.2.1 Communication Requirements
The following are requirements pertaining to the communication with the sensor units.
1. The application shall discover all available sensor units within the range of the
bluetooth device.
2. The application shall connect to the selected devices.
3. The application shall read each device’s ID.
4. The application shall read data coming from each of the sensor units.
5. The application shall send the selected g value back to the sensor unit.
6. The application shall read the battery level coming from the sensor unit.
7. The application shall read the temperature level from coming from the sensor
unit.
4.2.2 Mode Requirements
The following are requirements related to the two modes that the application can be
in.
1. The application shall allow the user to choose between two different modes: File
Simulation and Data Acquisition.
4. Requirements Specification 43
2. In the File Simulation mode, the application shall allow the user to a list of
files to play back data from.
3. In the Data Acquisition mode, the application shall allow the user to choose
which devices to connect to from the available bluetooth devices.
4.2.3 Signal Processing Requirements
The following are requirements that deal with the signal processing part of the application.
They describe the type of calculations that need to be performed on the
acquired data before it is displayed.
1. The application shall perform use the sensors’ calibration information to calibrate
the data so that it appears within the selected g range.
2. The application shall pass the raw data through a DC filter prior to plotting it
in order to eliminate the effect of gravity on the sensor unit.
3. The application shall apply a filter on the raw data in order to eliminate noise.
4. The application shall perform an FFT on the data in order to determine the
fundamental frequency.
5. The application shall perform an ellipse fitting on the data in order to determine
the phase and eccentricity of the machine’s elliptical motion.
6. The application shall perform a calculation to determine the machine’s RPM.
7. The application shall perform a calculation to determine the strokes in all three
axes as well as the main stroke.
8. The application shall perform a calculation to determine the g force in all three
axes as well as the main g force.
44 4. Requirements Specification
4.2.4 Logging Requirements
The following are requirements describing how the data is logged on the machine,
and how it is thereafter read. The logging involves storing the raw data, as well as
logging the acquisition information, such as the customer, the machine number, etc.
1. The application shall log the calibrated unfiltered data into a file.
2. The application shall allow the user to determine when the logging should start
and when it should end.
3. The application shall create a separate file each of the used sensor locations for
logging its data.
4. The application shall log information related to the acquisition into a separate
file. This information is to include at least the following: Customer, machine
model, date and number of bearings on the machine.
5. The application shall log information related to the sensor units used. This
information should include at least the following for each used sensor: Sensor
ID, location on machine, orientation (on the top or on the side of the machine),
battery level and temperature level.
6. The application shall log the start and end times of the acquisition.
7. The application shall log the g force level used throughout the acquisition.
4.2.5 Display Requirements
The following requirements apply to how the data is displayed on the screen. The
display of data can be in two forms: graphical and numerical.
1. The application shall display plots of the machine’s motion in the XY, XZ, and
YZ planes.
4. Requirements Specification 45
2. The application shall allow for displaying the orbits based on both the filtered
and unfiltered data.
3. The application shall display small views of the orbits of all the locations used
to perform the acquisition at the same time.
4. The application shall display values related to all the locations used to perform
the acquisition at the same time.
5. The application shall display plots representing the FFTs in all three axes for
each of the sensors. The frequencies displayed shall be of a minimum of 10Hz
and a maximum of the Nyquist frequency given by half the sampling rate.
6. The application shall display plots of the signals (waveforms) in all three axes
for each of the sensors.
7. The application shall display the machine’s RPM computed from each of the
sensors.
8. The application shall display the stroke in all three axes for each of the sensors,
as well as the average stroke.
9. The application shall display the g force in all three axes for each of the sensors,
as well as the avergae g force.
10. The application shall display the phase and eccentricity after performing the
ellipse fitting on each of the sensor locations.
11. The application shall display the information related to the acquisition. This
includes the customer, the machine model, the date, the start and end times,
and the number of bearings.
4.2.6 Graphical User Interface Requirements
The following are requirements pertaining to the Graphical User Interface, and describe
the types of menus, controls and messages that are to be used.
46 4. Requirements Specification
1. The application shall allow the user to choose the g force the machine is operating
on.
2. The application shall allow the user to pick a sensor to display its enlarged orbit
plot, FFT plots and waveform plots.
3. The application shall allow for the pausing and resuming of the data display.
4. The application shall allow for initiating and stopping the recording of the data.
5. The application shall allow for the adjusting of the filter bandwidth.
6. The application shall allow for the adjusting of the FFT frequency range.
7. The application shall allow the user to change the orientation of the orbit plots
between the XY, XZ and YZ planes.
8. The application shall allow the user to choose whether the enlarged orbit shall
display filtered or unfiltered data.
9. The application shall allow for adjusting the centre frequency used for the filter.
10. The application shall allow the user to choose the unit used to display the stroke
(mm or inches).
11. The application shall allow the user to view generated reports directly from
within the application.
4.2.7 Reporting Requirements
The application must allow for the generation of three types of reports as required
by the client. The following is a description of these reports:
4. Requirements Specification 47
Single Point Report
Such a report is generated for each of the mounted sensors, providing in depth analysis
on each of the individual measuring points. An FFT plot, a waveform plot and an
orbit plot (with both filtered and unfiltered data) is generated along with a summary
of the numerical values for that specific location.
Orbit Summary Report
This report must contain orbit plots of all the mounted sensors, as well as their
numerical values. The orbits shall appear in their filtered state, allowing the user
to determine whether or not the machine is performing normally. The machine’s
behaviour is deemed normal if the orbits have the same size, the left side of the
machine mirrors the right side, and the overall acceleration levels are within their
expected range.
Tuning Report
This report summarizes the vertical and the horizontal strokes and g forces for the
entire set of sensors mounted to the machine. It is mainly used to determine any
deviations between the measured data and the expected machine behaviour. The
results of the deviations are used to provide tuning recommendations to the client
based on physical principles that apply to any vibrating machine.
The following are requirements that relate to the reporting part of the application.
1. The application shall allow for the creation and storage of a single point report
for each sensor location.
2. The application shall allow for the creation and storage of an orbit summary
report summarizing the behaviour that all of the mounted sensor units acquired.
3. The application shall allow for the creation and storage of a tuning report
detailing the machine’s behaviour and providing recommendations for adjusting
48 4. Requirements Specification
the machine.
4. The application shall allow for the adjustment of the values used to generate the
turning report before the report is actually generated. Such values include the
bearing diameter, the friction compensation, the inclination angle. and other
important parameters.
5. In the tuning report, the application shall allow the user to manually enter
values for missing sensors based on their location and the readings from the
other sensors.
6. The application shall allow for the viewing of the reports if they have already
been created, and the creation of reports otherwise.
7. The application shall generate reports in the formats predetermined by the
client.
8. The application shall include a header section on each of the reports with the
customer, machine, date and time information as well as the company logo.
4.3 Nonfunctional Requirements
An application’s non-functional requirements are those not related directly to its behaviour,
but are more concerned with its properties or characteristics. The following
are the non-functional requirements that have been found to be related to the Vibration
Analysis Tool.
4.3.1 Performance Requirements
Performance requirements are most important in hard real-time systems, where failing
to meet a time requirement causes the entire system to fail. This is not exactly the
case in vibration analysis, since not meeting a deadline will not cause a system failure,
4. Requirements Specification 49
however, it may cause unreliable data. For this reason, the following requirements
are necessary:
1. The application shall generate plots and display data read from the sensor at a
frequency defined by the user and not exceeding 1000Hz.
2. The application shall log all data read from all sensors.
4.3.2 Platform Requirements
The following are requirements related to the operating system and devices that the
application will run on.
1. The application shall operate on Linux (for the PDA application) and Windows
(for the PC application).
2. The application shall run on both a PDA device selected by the client, as well
as a PC (laptop or desktop) with no less than a 12” display.
4.3.3 Safety Requirements
Since the vibration analysis tool is not a safety critical application, not many requirements
exist in terms of safety. The following is a requirement on the connection with
the sensor units.
1. The application shall connect to the sensor units via bluetooth. This will allow
for a wireless connection that increases the safety of the person acquiring the
data, since they will no longer be holding a device that is connected by a wire
to the vibrating machine.
4.3.4 Maintainability Requirements
The maintainability requirements focus on both the maintenance of the application
as well as the ability of adding features later on.
50 4. Requirements Specification
1. The application shall be designed in a manner allowing for easy maintenance,
as well as in an easy way to add features in the future.
4.3.5 Reliability Requirements
  Informally, a software is reliable if the user can depend on it [7]. The reliability in
  the vibration analysis tool comes from the reliability of the data being read. The
  following are requirements concerning the reliability of the application.
    1. The application shall read the data coming from the sensor in a reliable manner,
    meaning that data shall not be dropped or misread.
    2. The application shall produce reliable plots as determined by the engineers at
    the company.
    3. The application’s signal processing calculations shall deliver reliable results as
    determined by the engineers at the company.
    4. The reports produced by the application shall contain reliable results as determined
    by the engineers at the company.
4.3.6 Usability Requirements
A software system is usuable if its human users find it easy to use [7]. As discussed
earlier, more than one type of users may be using the application, and therefore, the
application should be usable for every type. The following are requirements on the
usability of the application.
1. The application shall have a Graphical User Interface (GUI) and shall use controls
that allow the user to access its various functions.
2. The application’s interface shall be easy to use as determined by its various
types of users.
4. Requirements Specification 51
3. The application shall allow for the display of text (on labels, button, etc.) in
any of the predefined languages.
4. The application shall use fonts that are legible to an average user.
5. The application shall use colours that convey meanings to the user while maintaining
the look of the application.
6. The application shall use consistent colours, fonts and designs.
