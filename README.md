# Real-Life-Example-TCP-IP-and-OSI-Model-in-Action

This documentation explains how I performed a real-life example using the TCP/IP and OSI models to understand how data flows across a network when accessing a website.


Scenario Overview: 

I used one of my computers to browse the internet and access a website called networklarry.com. During this process, I observed how the TCP/IP model and OSI model worked together to handle the data flow from the computer to the website and back.

Step-by-Step Process

	1.	Start with the TCP/IP Model Layers
	•	Application Layer:
	•	The process started with the Application Layer when I accessed networklarry.com using HTTPS, as that is the protocol the website supports.
	•	Encapsulation Process:
	•	Transport Layer: The data was encapsulated into segments.
	•	Network Layer: The segment was further encapsulated into a packet.
	•	Data Link Layer: The packet was encapsulated into a frame.
	•	Physical Layer: The frame was sent across the network using a physical medium (RJ45 Ethernet cable).

	2.	At the Switch
	•	The data first reached the switch. Since the switch operates at Layer 2 (Data Link Layer), it used the MAC address to forward the frame to the next destination, the router.
	•	The switch does not understand IP addresses (Layer 3); it only works with MAC addresses.

	3.	At the Router
	•	The router operates at Layer 3 (Network Layer). It:
	•	Read the IP address from the packet to determine where the data needed to go.
	•	Sent out an ARP (Address Resolution Protocol) request to find the MAC address associated with the IP address of networklarry.com.
	•	Once the ARP request was broadcasted, the MAC address of networklarry.com was discovered and paired with its IP address.

	4.	At the Destination (networklarry.com)
	•	Once the packet reached networklarry.com:
	•	The server decapsulated the packet layer by layer, working backward:
	•	Physical Layer → Data Link Layer → Network Layer → Transport Layer → Application Layer.
	•	The website checked if all the data matched the request criteria (e.g., correct IP, protocol, and port).
	•	After verification, the website provided access, and the data (the webpage) was sent back to the computer.

	5.	Return Process
	•	The reverse process occurred when the response data was sent back:
	•	networklarry.com encapsulated the response starting from the Application Layer and sent it down the TCP/IP stack.
	•	The router ensured the packet reached the switch, and the switch forwarded it to the correct computer using its MAC address.

Key Takeaways

	•	The switch operates at Layer 2 and uses MAC addresses for forwarding.
	•	The router operates at Layer 3 and uses IP addresses for routing between networks.
	•	Encapsulation and Decapsulation occur at each layer of the TCP/IP model to ensure data is properly packaged for transport and interpreted correctly upon arrival.
	•	The process happens seamlessly, ensuring reliable communication between devices.

Commands Used

	•	ARP Process: The router broadcasted ARP requests to resolve IP addresses into MAC addresses.
	•	Encapsulation Process: The TCP/IP stack added headers at each layer to properly package the data.

 Conclusion 

 By using Cisco Packet Tracer, I was able to observe the process and learn how the TCP/IP model operates in a real-world scenario.
