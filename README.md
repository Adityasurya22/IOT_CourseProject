## IOT COURSE PROJECT

# IoT-Enabled Precision Agriculture System

## Project Overview

This IoT project aims to create a robust and efficient system designed to enhance Precision Agriculture through real-time data monitoring, analysis, and automation. The system leverages the MQTT protocol, known for its lightweight and efficient message distribution, to establish seamless communication between multiple IoT nodes and a central server.

## System Architecture

### IoT Nodes
Each IoT node in the system is built using **ESP32 devices**, chosen for their versatility, low power consumption, and integrated Wi-Fi and Bluetooth capabilities. These nodes are responsible for collecting various environmental data such as temperature, humidity, soil moisture, and more. Once the data is collected, the node sends it to the central server via MQTT, ensuring reliable and timely data transmission even in resource-constrained environments.

### Central Server
The central server plays a critical role in processing the data received from the IoT nodes. Upon receiving the data, the server performs real-time analysis, comparing it against a secondary dataset that include historical data, weather predictions and optimal crop conditions. Based on this analysis, the server generates actionable insights and warnings.

### Data Feedback and Display
After processing the data, the server sends the analysis results back to the respective IoT node using MQTT. The node then displays relevant warnings or notifications on its screen, allowing for immediate action to be taken by farm operators or devices. This feedback loop ensures that decisions are data-driven and timely, minimizing risks and optimizing farm management.

### Data Storage
In addition to real-time analysis, all data received from the IoT nodes is stored in a structured manner within an **SQL database** hosted locally on the server. This database acts as a repository for long-term data storage, enabling detailed historical analysis, trend identification, and reporting. The locally hosted database ensures that the system remains functional and secure, even without continuous internet access.

## Application in Precision Agriculture

This system is particularly suited for **Precision Agriculture**, where continuous monitoring and timely interventions are crucial. By automating data collection, analysis, and feedback, the system allows farmers to maintain optimal growing conditions, efficiently allocate resources, and respond swiftly to potential issues. This level of automation and insight contributes to increased agricultural sustainability, higher crop yields, and reduced environmental impact.

## Technologies Used

- **ESP32 Devices**: For IoT nodes
- **MQTT Protocol**: For lightweight, efficient communication
- **SQL Database**: For data storage and management
- **Server-Based Analysis**: For real-time data processing and feedback


For running the system, these steps need to be followed:

1. Start a Mosquitto MQTT message broker.
2. Run the file `device.py` on the ESP32 device after changing the ssid and password of the wifi connection.
```bash
wlan = connect_to_wifi('device', 'password')
```
3. The folder named server should be copied the sever which is recieving the data. 
4. Host a MySQL server on the server, and set appropriate host, username, password and database name in the file `sql.py`
```bash
mydb = mysql.connector.connect(
            host="localhost",
            user="device",
            password="password",
            database="iot"
        )
```
5. Finally, run the file `server.py` on the server.





