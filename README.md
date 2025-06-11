# What Happens When You type google.com and Click Search / Press Enter

This document provides a detailed breakdown of the steps your browser and network take when you type google.com* and click the *Search* / *enter* button.


## 1. Entering the Query:google.com

When you type the query into your browser (e.g., Chrome) and press Enter, a sequence of network and browser-level events is triggered to retrieve, display and deliver the relevant search results.


## 2. DNS Lookup (Domain Name Resolution)

- *Browser cache check:* The browser first checks if it has a recent DNS record for google.com.

- *If not cached:*
  1. The browser contacts the *local DNS resolver* (typically provided by your ISP).
  2. The resolver may query:
     - A *Root nameserver, which provides the address of a **TLD server* (e.g., .com).
     - The *TLD server, which provides the **authoritative nameserver* for google.com.
     - The *authoritative nameserver, which returns the actual **IP address* of google.com.


## 3. Establishing a TCP/IP Connection (Handshake)

- The browser uses the IP address to initiate a *TCP connection* with the server.
- A *three-way handshake* occurs:
  1. *SYN* – Browser requests to start a connection.
  2. *SYN-ACK* – Server acknowledges the request.
  3. *ACK* – Browser confirms the connection.


## 4. Firewall Checks

- *Client-side firewall:* Verifies if the outgoing request is permitted.
- *Server-side firewall:* Verifies if the incoming request is safe.


## 5. SSL/TLS (HTTPS Encryption)

- The browser and server perform a *TLS handshake* to:
  - Agree on encryption protocols.
  - Exchange and verify digital certificates.
  - Establish an encrypted connection.
- This ensures that all communication is *secure and private*.



## 6. Load Balancer

- Google's *load balancer* receives your request.
- It:
  - Distributes traffic across multiple backend servers.
  - Selects a server based on current load, location, or a scheduling algorithm.



## 7. Web Server

- The chosen *web server* handles the request.
- It returns *static assets* including:
  - HTML (structure)
  - CSS (styling)
  - JavaScript (interactivity)



## 8. Browser Renders the Homepage

The browser processes and renders the received files:

- Builds the *DOM tree*.
- Applies *CSS* for layout and design.
- Executes *JavaScript* for interactivity.
- Displays the Google homepage with a *search box*.


## Clicking *Search* / *Enter*


## 9. JavaScript Captures the Search Term

- You type a query (e.g., bby) and click *Search*.
- JavaScript captures the input and sends a *new HTTPS request* to the server with your search query.



## 10. Request Reaches Web Server Again

The new search request follows the same secure path:

- Firewall - TLS/SSL - Load Balancer - Web Server



## 11. Application Server Handles the Query

- The *application server* processes the dynamic request:
  - Parses your search term.
  - Determines the type of results (web, images, videos, etc.).
  - May call external services or APIs.



## 12. Database Query (If Needed)

- If required, the application server:
  - Queries Google's *database infrastructure*.
  - Retrieves data such as webpages, snippets, and ads.



## 13. Response Is Built and Sent Back

- The application server prepares the *response page*.
- The *web server* sends it back through:
  - Load Balancer - TLS connection - Browser


## 14. Browser Renders Search Results

- Parses and displays the *HTML*.
- Executes *JavaScript* for dynamic elements.
- Applies *CSS* for visual styling.
- Loads and displays additional resources like:
  - Thumbnails
  - Maps
  - Ads
  - Autocomplete suggestions


## 15. User Interaction

- The user now see search results
- You can interact by clicking links, refining your query, or using features like image or video search.-

**Below is a Diagram baiscally showing the flow ;**

![diagram](/images/diagram.jpg)
