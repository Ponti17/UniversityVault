For our project we wanted to create a complete embedded smartwatch solution from the ground up, called Wristmate.

We based Wristmate on the ESP32-C3 microcontroller which is low power and features built-in WiFi. We use a 1.2" inch Sharp Memory Display which was choosen for its round size and low power consumption. The watch features a built-in accelerometer for step-counting and a temperature and pressure sensor. 

After optimizing sleep states for the ESP32 the watch consumes less than 1.3mA on average, which results in a battery life of up to 2 weeks.

The schematic and PCB was designed from start to finish in Altium and was manufactured and assembled by JLCPCB. 

After we received the PCB's we immediately started programming them to implement various features. When turned on Wristmate connects to the internet and download time, weather and calendar events. 

The project turned out as a succes, and we implemented all features we wanted. The future possibilities are however endless. The ESP32 chip is powerful, and with bluetooth and Wifi connectivity anything is possible. 

