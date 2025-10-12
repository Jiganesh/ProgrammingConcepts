## ROM ROM BHAIYO, SYSTUM PHAAD DENGE !



### Topics covered below
- Horizonatal Scaling
- Vertical Scaling
- Master-Slave Architecture
- Load Balancer
- Throttling
- Rate Limiting
- Session Id
- Authentication
- Authorization
- Cookies
- JSON Web Tokens (JWT)
- Functional Requirements
- Non Functional Requirements
- Cache
- Content Delivery Network
- Hashing 
- Consistent Hashing
- Time To Live (TTL) / Hop Limit
- OSI Model
- Thundering Herd Problem





**Horizontal Scaling** - Adding new machines to cope with computational demands
- Example : A Diner is always crowded (high number of requests), to satisfy customer demand they open different Diner Franchise to serve (adding more restuarants).

**Vertical Scaling** - Adding resources to existing machine to cope with computational demands.
- Example : A Diner is always crowded (high number of requests), to serve the customers you hire more servers and chefs (adding more resources like processor, storage etc).

**Master-Slave Architecture** - A computational model / design pattern for distributed systems where master node coordinates and controls slave nodes.
- Example : A Diner has head chef (master), due to unforeseen circumstances he was not able to work. You can bring a backup chef (slave), where head chef can instruct and backup chef can execute his tasks.

**Load Balancer** - A device or service that distributes network traffic dynamically across resources
- Example : A Diner has two head chefs (two servers). Giving all orders to single chef would not be efficient. The manager (Load Balancer) gives half orders to chef1 and half orders to chef2


**Throttling** - Technique to control the rate at which API requests are processed.
- Example : A Diner has three tables (capacity to process request), if 5 people (requests) are visiting the diner three people will be let in and other two have to wait (throttled).

**Rate Limiting** - Technique to restrict API requests a client can make.
- Example : A Diner has three table (capacity to process request), with 5 people in queue, one person asks for all tables but a person can occupy only one table (rate limited). After rejecting the request 3 people will be let in.

**Session Id** - An unique identifier that a web server assigns to a user
- Example : You visited a Diner and gave your order to a waiter. The waiter will provide you a orderid (unique) which will map to all items you ordered at that visit. You will be billed on that order id. Another orderid will be created for your next visit. 

**Authentication** - Process of application or service has to prove their identity before gaining access.
- Example : A Diner hires its staff after authenticating their background and legal documents.

**Authorization** - Process of giving someone the ability to access a resource.
- Example : A Diner will only authorize its staff members (authorized users) to access kitchen

**Cookies** - small pieces of code that a website stores in your browser to track who you are and what you are doing.
- Example : A Diner has a challenge to eat most amount of burgers, you completed the challenge and now you are on wall of fame. The photo (cookie) on wall of fame (browser)  provides information about you and your record in that diner (session). If you remove the photo (clear cookie) that information will be gone.


**JSON Web Token (JWT)**  - Self-contained, stateless tokens that carry all the necessary information for authentication and authorization within the token itself.
- Example : A Diner has to authenticate its staff and staff can access kitchen. The guard cannot allow unauthenticated staff. To avoid redundant authentication, staff is provided a badge (JWT) which allows them to access kitchen instead of going through authentication process everyday.


**Functional Requirements** - Requirements that describe behaviour, functionality and operations of the system.
- Example : A Diner should serve Burgers and Steak.


**Non Functional Requirements** - Requirements that describe performance, quality and constraints under which system should operate
- Example : A Diner should serve best steaks in town.

**Cache** - Storage layer between application and datastore storing frequently accessed data for easy and quick access.
Caching is strategy to reduce latency and improve efficiency of data retrival
- Example : A Diner delivers food. For fast delivery diner opens cloud kitchens and keeps best seller and frequently ordered dishes ready so they can be delivered faster.

**Content Delivery Network (CDN)** - Geographically dispersed servers used to deliver static content like images, videos, JS files etc.
- Example : A Diner delivers food. Greater the distance, Longer the wait time resulting in bad customer experience. The Diner opens cloud kitchens in strategic locations and keeps best seller dishes ready to go to deliver faster.


**Hashing** - Process of transforming provided data with a hash function resulting hash key
- Example : A Diner has multiple sub brands like Fasoos (famous for frankie's), Oven Story (famous for pizza's), Behrouz(famous for Biryani's) under one roof on different floors. Our Manager (hash function) will process the user request and send them to respective floor (hash key - floor 0, floor 1, floor 2 etc).


**Consistent Hashing** - Distributed hashing technique to load balance and minimize rehashing when the number of nodes in a system change.
- Example :   A Diner has 4 chefs specializing in different cuisines, each handling orders based on a customer's table number. If one chef calls in sick, traditional hashing would reassign all tables, causing confusion. With consistent hashing, only a portion of that chef's tables get redistributed to other chefs, while most tables keep their original chef assignments.


**Time to live (TTL) / Hop Limit** - mechanism (generally a value) used for data validity and expiration in network
- Example : A Diner has best seller fried icecream on the menu. The fried icecream has to be served within 10 minutes else it starts melting and crispy coat becomes moist. TTL of fried icecream is 10 minutes.


**Open Systems Interconnection (OSI Model)** - framework to understand how network commmunication work.

Let's understand our Diner's Application with OSI Model

`Application Layer`- Layer 7 (User Friendly Interface) - top layer where actual application and service reside.
- Exampler : Diner's Web Application 

`Presentation Layer` - Layer 6 (Data Translation) - translate data into format receiving device can understand
- Example : Encryption of customer / admin data, Compression of files uploaded to Binary Large Object, Data Conversion

`Session Layer` - Layer 5 (Managing Session)  - maintains, and ends communication between devices. Also manages checkpoints, to pause and resume conversations.
- Example : Customer added few dishes to order and closed the application, after opening the application he can resume with same order.

`Transport Layer` - Layer 4 (Managing Conversations) - ensures reliable communication between devices
- Example : Customer placed an order for biryani when the data is received on the other end it should place order for biryani.

`Network Layer`- Layer 3 - (Routing) routes data packets between different networks using IP addresses
- Example : Searching with Diner's url on web


`Data Link Layer` - Layer 2 - (Addressing and Framing): this layer adds unique addresses (MAC addresses) to data packets, ensuring they reach the correct destination on a local network
- Example : Order placed from Jiganesh to Diner for Biryani


`Physical Layer` - Layer 1 - (Envelope): lowest layer, deals with the actual physical connection between devices, such as cables, switches, and hubs. responsible for transmitting raw bits (0s and 1s) over the network medium
- Example : Wifi connection 

**Thundering Herd Problem** - all failed requests retry at identical intervals leading to cascading failures or no chances of recovery.
- Example : A customer in Diner asks server regarding his order, the server fails to retrieve his order. The customer keeps probing and asking the server regarding his order which overwhelms the server.

**Domain Name System** - protocol that translates human friendly domain name to IP Address

![DNS.png](/SystemDesignConcepts/DNS.png)