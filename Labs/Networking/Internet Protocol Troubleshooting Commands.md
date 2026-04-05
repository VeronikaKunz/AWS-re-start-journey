## Lab Overview

In this lab, I focused on practicing common troubleshooting commands and understanding how they can be applied in real customer scenarios. The goal was to build confidence in identifying and diagnosing issues by using command-line tools.

I explored how different commands can be used to check connectivity, inspect system behavior, and gather useful information when something is not working as expected. This hands-on practice helped me understand how to approach troubleshooting in a structured and efficient way.

By the end of the lab, I gained practical experience in using these commands to analyze problems and apply them in real-world support situations.

### Steps:

1. To understand how troubleshooting works in practice, I used several commands that correspond to different layers of the OSI model.
   At the network layer, I tested connectivity using the **ping** command to verify that the instance can reach external resources. This helped confirm whether ICMP traffic is allowed and whether basic network communication is functioning.

   <img width="456" height="173" alt="Screenshot 2026-04-05 at 17 16 00" src="https://github.com/user-attachments/assets/d52936c1-7ccb-4fe7-b5d1-7b3b2d7252af" />


2. I also used **traceroute** to analyze the path packets take to reach a destination and identify where latency or packet loss might occur.

   <img width="500" height="171" alt="Screenshot 2026-04-05 at 17 17 05" src="https://github.com/user-attachments/assets/1588b9c1-b736-4be6-acd3-46c9e46ab849" />


3. At the transport layer, I used **netstat** to review active connections and check which ports are listening on the system. This provided visibility into the instance’s network activity.

   <img width="500" height="88" alt="Screenshot 2026-04-05 at 17 18 46" src="https://github.com/user-attachments/assets/5a4910e8-07d5-4921-a945-567d0dde1df4" />


4. I also used **telnet** to test connectivity to specific ports, which helped determine whether traffic is being blocked by security groups or firewalls.

   <img width="431" height="137" alt="Screenshot 2026-04-05 at 17 20 23" src="https://github.com/user-attachments/assets/31411313-6e24-4892-b028-9a5075c3b456" />


5. At the application layer, I ran the **curl** command to test communication with a web server and verify that it responds correctly. This allowed me to confirm that services are reachable and functioning as expected.

   <img width="500" height="407" alt="Screenshot 2026-04-05 at 17 23 01" src="https://github.com/user-attachments/assets/9514a52b-5e14-4684-824d-56e757d8b98f" />


This lab helped me understand how to use different commands together to troubleshoot issues at multiple layers and quickly identify where a problem might be occurring.
