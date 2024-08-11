# Network-Traffic-Analysis
 # Security Audit

## Objective

To analyze DNS and ICMP traffic in transit using data from a network protocol analyzer tool and  identify which network protocol was utilized in assessment of the cybersecurity incident. 


## Scenario

Review the scenario below. Then complete the step-by-step instructions.

You are a cybersecurity analyst working at a company that specializes in providing IT services for clients. Several customers of clients reported that they were not able to access the client company website www.yummyrecipesforme.com, and saw the error “destination port unreachable” after waiting for the page to load. 

You are tasked with analyzing the situation and determining which network protocol was affected during this incident. To start, you attempt to visit the website and you also receive the error “destination port unreachable.” To troubleshoot the issue, you load your network analyzer tool, tcpdump, and attempt to load the webpage again. To load the webpage, your browser sends a query to a DNS server via the UDP protocol to retrieve the IP address for the website's domain name; this is part of the DNS protocol. Your browser then uses this IP address as the destination IP for sending an HTTPS request to the web server to display the webpage  The analyzer shows that when you send UDP packets to the DNS server, you receive ICMP packets containing the error message: “udp port 53 unreachable.” 

 <img src="https://d3c33hcgiwev3.cloudfront.net/imageAssetProxy.v1/LKXsnNIhT0e1mAz5AEvxog_d363c94e0a4f4a8b90b0be403f6ee1f1_mMBaLWLyXG2omYBcSdjuR8y5_S59zow1ZEPYdjNyJzA1B0r55nI9KmDosI8QHXcEwE51NxM3N5gNtMgSOyVDHyJVLZvZA7_jJtkzUKfxuqFUJPHs57vVVES-LbG5teR8eir4idaqsxFaYJhhVJZn-a_S-txb7zQNIZq07XESgSkqDHuzfvALfYk3lipGVBY?expiry=1723507200000&hmac=8-YkfsaZXM-0OkQvKnnpzmh-jkP3stG5LLV6uCLtaNA" />

 In the tcpdump log, you find the following information:

The first two lines of the log file show the initial outgoing request from your computer to the DNS server requesting the IP address of yummyrecipesforme.com. This request is sent in a UDP packet.
The third and fourth lines of the log show the response to your UDP packet. In this case, the ICMP 203.0.113.2 line is the start of the error message indicating that the UDP packet was undeliverable to port 53 of the DNS server.
In front of each request and response, you find timestamps that indicate when the incident happened. In the log, this is the first sequence of numbers displayed: 13:24:32.192571. This means the time is 1:24 p.m., 32.192571 seconds.

After the timestamps, you will find the source and destination IP addresses. In the first line, where the UDP packet travels from your browser to the DNS server, this information is displayed as: 192.51.100.15 > 203.0.113.2.domain. The IP address to the left of the greater than (>) symbol is the source address, which in this example is your computer’s IP address. The IP address to the right of the greater than (>) symbol is the destination IP address. In this case, it is the IP address for the DNS server: 203.0.113.2.domain. For the ICMP error response, the source address is 203.0.113.2 and the destination is your computers IP address 192.51.100.15.

After the source and destination IP addresses, there can be a number of additional details like the protocol, port number of the source, and flags. In the first line of the error log, the query identification number appears as: 35084. The plus sign after the query identification number indicates there are flags associated with the UDP message. The "A?" indicates a flag associated with the DNS request for an A record, where an A record maps a domain name to an IP address. The third line displays the protocol of the response message to the browser: "ICMP," which is followed by an ICMP error message.

The error message, "udp port 53 unreachable" is mentioned in the last line. Port 53 is a port for DNS service. The word "unreachable" in the message indicates the UDP message requesting an IP address for the domain "www.yummyrecipesforme.com" did not go through to the DNS server because no service was listening on the receiving DNS port.

The remaining lines in the log indicate that ICMP packets were sent two more times, but the same delivery error was received both times. 
Now that you have captured data packets using a network analyzer tool, it is your job to identify which network protocol and service were impacted by this incident. Then, you will need to write a follow-up report. 

As an analyst, you can inspect network traffic and network data to determine what is causing network-related issues during cybersecurity incidents. Later in this course, you will demonstrate how to manage and resolve incidents. For now, you only need to analyze the situation. 

This event, in the meantime, is being handled by security engineers after you and other analysts have reported the issue to your direct supervisor. 



**Supporting Materials :**

<a href="https://docs.google.com/document/d/1BSFXPX70UED_cYKbUe5jnBe0VpLI_9aaqVWAKu5U3eI/edit?usp=sharing&resourcekey=0-h3gHkqD6OCiMDCK79TRWRg"><img src="https://img.shields.io/badge/-GoogleDOC:Incident Report Template-FFFF?&style=for-the-badge&logo=Google&logoColor=white" /></a>
<a href="https://docs.google.com/document/d/1RquiQsvvIAV-eGE3YTlmhWDF_EWIRno532ZnlLe6i1Q/edit?usp=sharing"><img src="https://img.shields.io/badge/-GoogleDOC:Example of an Incident Report-FFFF?&style=for-the-badge&logo=Google&logoColor=white" /></a>


## Completed Analysis of Network Traffic 

<a href="https://docs.google.com/document/d/11YIrN6R3fTqw7AWeh_4YCB4QXK8VnO4_CYPSK2MU5xc/edit?usp=sharing "><img src="https://img.shields.io/badge/-GoogleDOCS:Network Traffic Analysis -FFFF?&style=for-the-badge&logo=Google&logoColor=white" /></a>


### Skills Learned

Analyzing tcdump logs and Finding root cause of Network Traffic.



### Tools Used

tcdump logs  


## Steps

1.**Access the template** 

2.**Access supporting materials**

3.**Provide a summary of the problem found in the tcpdump log**

4.**Explain your analysis of the data and provide one solution to implement**
