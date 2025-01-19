# Non-Web Services: Outside the Web

The internet is not just a collection of web pages and browsers; it is a global network interconnecting millions of computing devices. Some of these devices are traditional, like desktops and laptops, while others are not, like mobile phones, IoT devices, and servers. The internet also serves as an infrastructure offering services-functionalities that enable systems, applications and users to communicate and achieve their goals.

But not all of these services involve the web as we know it. Many are non-web services  operating on protocols and architectutes that most likely, do not rely on HTTP (HyperText Transfer Protocol) but are still incolved in shaping our everyday online experiences. We will explore the structural layers that make computer interactions possible, the architectures that support them, and how they intersect with the web.


## Internet Protocol Layers: Where Services Begin

Protocols are communication standards that define how data transfer occurs between *systems*.

At the core of the Internet is the *Internet Protocol Stack*, a designed to organize communication into layers.

1. Application Layer: The Application layer is the highest level protocol layer which is responsible for handling communication between end-user systems. These protocols include HTTP, FTP (File Transfer Protocol), and SMTP (Simple Mail Transfer Protocol).

2. Transport Layer: Responsible for the data transfer between systems using protocols like TCP (Transmission Control Protocol) and UDP (User Datagram Protocol).

3. Network Layer: This handles the routing and transfer of data packets, its protocols implement the techniques for effective data transmission amd is responsible for addressing as each device on a networks needs to be identified uniquely. Some examples include, the popular IPv4 and IPv8 as well as ARP (Address Resolution Protocol) and RARP (Reverse Resolution Protocol).


4. Link Layer: Manages communication over specific physical links, like Ethernet or Wi-Fi.

5. Physical Layer: Transmits raw bits across network cables or wireless signals.

Each layer provides services to the one above it. FTPs and HTTPs popularly rely on transport and network layers to enable reliable data transfer.


## Architectures: How Systems Communicate

To build applications, we need programs that run on computing devices to communicate with each other over a network. There are two main architectural paradigms for structuring these communications:


1. Client-Server Architecture
In this model, one host (the server) provides services to multiple clients. Think of a web browser requesting a webpage from a server. Here’s a practical example:

Use Case: An FTP client interacts with a server to upload website files. A web designer creates HTML and CSS files locally, then uses FTP to transfer these files to the hosting server. The server, in turn, makes these files available over HTTP for visitors to view on the web.

Challenge: As the number of clients grows, a single server can become overwhelmed. To handle this, data centers—clusters of servers—are used, though they come with high costs and infrastructure complexity.


2. Peer-to-Peer (P2P) Architecture
In this decentralized model, devices (peers) communicate directly without relying on centralized servers. A classic example is BitTorrent:

Use Case: A software company might distribute a large operating system update via BitTorrent to reduce server load. Peers downloading the update also upload it to others, creating a scalable distribution network.

While P2P is cost-effective and scalable, it faces challenges like security vulnerabilities and coordination complexities.


## Transport Protocols: The Gateway Between Worlds

The transport layer ensures data reaches its destination. These protocols act as networks/sockets which connect two processes/systems to each other. Two dominant protocols are the TCP and the UDP:

- TCP: Although extremely reliable data transfer, as data losses may occur causing the TCP to resend data packets, it is slower because of this advantage. It is ideal for file transfers, messaging systems and email.

- UDP: Faster but less reliable and only suitable for real-time applications, where data losses are more permitted. For example, Video calls (Zoom, Google Meet) and Voice over IP (Zoom, Skype).


## Non-Web Services in Action

The core concept of non-web services is its lack of reliance on web protocols like HTTP. It may not always  interact directly with browsers, but they often support or enhance web-based workflows. A few examples:

1. FTP and Web Hosting

- Scenario: You’re designing a website and need to upload assets (images, scripts, etc.) to a server. While the site is accessed over HTTP, the upload process involves FTP.

- Behind the Scenes: The developer’s FTP client communicates with the server, transferring files securely. Once uploaded, the server serves these files to users via the web.

- FTP operates differently from HTTP in some ways:
    - Dual Connections: FTP uses two TCP connections: A control connection for user authentication and commands (e.g., login, change directory) and data connection for transferring files.
    - Out-of-Band Communication: Control information is sent on a separate channel (control connection) from the data being transferred, unlike HTTP, which combines them in a single channel (in-band communication).
    - Stateful Sessions: FTP servers maintain session information, such as user credentials and current directory state, throughout a session. This stateful nature limits scalability compared to stateless protocols like HTTP.


2. SMTP and WebMail

- Scenario: When you send an email using Gmail or Outlook, it’s not just the web interface at work. Behind the scenes, the email is sent using SMTP (Simple Mail Transfer Protocol).

- Behind the Scenes: The web interface communicates with the server to package and send the email. Similarly, IMAP or POP3 protocols might be used to retrieve emails when accessing them offline.

3. VoIP and Web Conferencing

- Scenario: During a Zoom call, you’re using a combination of web and non-web services.

- Behind the Scenes: The Zoom interface operates over HTTP, but the voice and video streams rely on RTP (Real-time Transport Protocol) over UDP. This hybrid interaction ensures a seamless user experience.

- In comparison to other protocols, VoIP leverages the Session Initiation Protocol (SIP) for establishing, modifying, and terminating voice sessions. The actual audio data is transferred using RTP (Real-time Transport Protocol) over UDP to minimize latency.  VoIP prioritizes speed over reliability. Data loss is tolerated to maintain call continuity, ensuring minimal delays in conversations.


4. DNS (Domain Name System) 
- Scenario:  When you type a URL into your browser, you’re indirectly interacting with DNS, a non-web service.

- Behind the Scenes: DNS resolves the human-readable domain name (e.g., google.com) into an IP address that your browser can use to fetch the site. This resolution happens using UDP for speed.

# Conclusion

While we often interact with web-based interfaces, many of the most critical functions—like file transfers, voice communication, and email—happen outside the browser. By learning how these services operate and integrate with the web, we can build systems that are not only practical but also scalable and secure.

Understanding when, where and how to implement these protocols, services and architecture is important when dealing with Computer Networking tools.