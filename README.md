# Ax project

1. About This Code
The project code consists of two main parts:
app.py: A Flask-based web server that provides a remote control interface via a web browser.
motors.py: Contains functions that use the Raspberry Pi’s GPIO pins to control motors for vehicle movement, a robotic arm, a seed dispenser, and a water sprayer.
 Important Aspects
Modular Design: The separation between control logic (motors.py) and the web interface (app.py) improves scalability and maintainability.
Real-Time Operation: The debug=True setting and short sleep durations enable responsive manual control during testing.
IoT Connectivity: The use of Flask and dynamic IP ensures the system can be accessed and operated remotely, a key requirement for modern smart farming.
Education and Research Potential: The project is an excellent platform to explore embedded systems, robotics, IoT, and AI in agriculture.


2. How It Works
When a user accesses the web interface (served by Flask), they see buttons for controlling the vehicle.
Clicking a button sends a command (number) via a URL (/<changepin>), which is handled by Flask and mapped to motor functions in motors.py.
The corresponding GPIO pins are activated to:
Move the vehicle forward, backward, or turn.
Lift or lower the arm (up(), down()).
Open/close the robotic arm gripper (aopen(), aclose()).
Start/stop seed dispensing (son(), soff()).
Start/stop water spraying (won(), woff()).
The dynamic IP setup using the socket module ensures the vehicle’s live camera feed and controls are accessible remotely on the local network.

3. Future Scope
AI & ML Integration:
Use computer vision (with models like YOLO or MobileNet) to automatically detect weed plants in the camera feed.
Automate arm control to target and remove weeds using precise coordinates from the vision model.
Implement ML-based decision systems to optimize watering and seeding based on soil and plant conditions.

Project Summary:

This project presents the design and development of an IoT-based smart agricultural vehicle aimed at automating key farming operations such as weeding, seeding, ploughing, and watering. The system is powered by a Raspberry Pi and integrates motor control with a Flask-based web application to enable remote operation via a mobile device or computer.
The vehicle is equipped with multiple DC motors to facilitate directional movement and a robotic arm capable of lifting, gripping, and performing mechanical tasks like weed removal. Seed dispensing and water spraying modules are also controlled through the web interface. The Python-based backend uses the GPIO library for real-time hardware interaction, while dynamic IP configuration ensures reliable remote access within a local network.
Looking ahead, the project has strong potential for expansion through artificial intelligence and machine learning. Integrating AI-based vision systems can enable automatic weed detection and targeted removal using the robotic arm, further reducing the need for manual intervention. Additionally, incorporating environmental sensors can support smart decision-making for precision agriculture.
This prototype lays the foundation for a scalable and sustainable farming solution that addresses labor shortages and promotes automation in modern agriculture.
