# 🏭 Automated Product Counting System using CODESYS + Simumatik + Node-RED

This project demonstrates a fully automated product counting system developed using **CODESYS** for PLC logic, **Simumatik** for virtual simulation, and **Node-RED** for HMI visualization. The system automates the detection, counting, and handling of products (boxes) on a conveyor belt. It uses real-time feedback from sensors and indicator lamps to simulate a realistic industrial environment.

---

## 🎥 Demo Video
[![Watch the Demo](https://img.youtube.com/vi/9ufg_MycdEk/0.jpg)](https://youtu.be/9ufg_MycdEk)  
▶️ [Click here to watch on YouTube](https://youtu.be/9ufg_MycdEk)

---

## 🔍 What is Simumatik?

**Simumatik** is a cloud-based virtual commissioning platform that allows users to create and simulate industrial systems. It provides digital twins of real automation components such as conveyors, sensors, motors, and controllers.

With Simumatik, you can:
- Simulate automation systems before deploying them physically.
- Test PLC logic in a safe, virtual environment.
- Integrate with real industrial tools using communication protocols like **OPC UA**.

---

## 🧠 Project Objective

To create an automated system that:
- Detects and counts boxes on a conveyor using a photoelectric sensor.
- Stops the conveyor and product feeder when 28 boxes have been counted.
- Uses indicator lamps and HMI to display system status.

---

## 🧰 Tools & Technologies

- **CODESYS v3.5+** – For creating and running the PLC logic (Ladder Diagram).  
- **Simumatik.io** – For building the 3D simulation environment and testing logic.  
- **OPC UA** – For real-time communication between CODESYS and Simumatik.  
- **Node-RED** – For building a simple HMI dashboard to visualize system status and counts.  

---

## ⚙️ System Components

- 📦 **Product Entry** – Feeds boxes onto the conveyor.  
- 🏃 **Conveyor Motor** – Moves the boxes forward.  
- 🔦 **Photoelectric Sensor** – Detects boxes as they pass.  
- 💡 **Green Lamp** – Indicates that the system is running.  
- 💡 **Yellow Lamp** – Turns ON when a product is detected by the sensor.  
- 💡 **Blue Lamp** – Turns ON when the box count reaches 28.  
- 🖥️ **Node-RED HMI Dashboard** – Displays count, sensor status, and system alarms.  

---

## 🔄 System Workflow

1. The system starts when the Start condition is activated via PLC logic.  
2. Boxes are spawned onto the conveyor using the Product Entry component.  
3. As each box passes the photoelectric sensor, the PLC counts it.  
4. The Green Lamp indicates the system is active.  
5. The Yellow Lamp lights up when a box is being detected.  
6. When the count reaches 28, the Blue Lamp is turned ON.  
7. Both the Product Entry and Conveyor Motor stop.  
8. Node-RED HMI displays the live count, system status, and indicator states.  

---

## 🔗 Connecting CODESYS, Simumatik, and Node-RED (OPC UA Integration)

1. In **Simumatik**:  
   - Add a PLC device to your environment.  
   - Assign OPC UA variables to each component (e.g., motor, sensor, lamps).  
   - Start the emulation.  

2. In **CODESYS**:  
   - Enable OPC UA client functionality.  
   - Configure the OPC UA server address (usually from Simumatik).  
   - Create matching variables in CODESYS and bind them using the OPC UA address space.  
   - Download the PLC program to the CODESYS SoftPLC runtime.  

3. In **Node-RED**:  
   - Install OPC UA nodes.  
   - Connect to the CODESYS or Simumatik OPC UA server.  
   - Bind variables to dashboard widgets (e.g., indicators, counters, lamps).  
   - Deploy the flow and access the HMI dashboard.  

---

## ✅ Result

This setup simulates a fully functional industrial scenario where a PLC precisely controls material handling equipment based on sensor input and system logic. The Node-RED HMI provides a real-time dashboard for monitoring box counts, lamp states, and system status.  

It’s ideal for learning industrial automation and testing control strategies before deploying them in physical systems.
