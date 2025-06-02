## System Design Jargon ft. Running a restaurant


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

**Content Delivery Network** - Geographically dispersed servers used to deliver static content like images, videos, JS files etc.
- Example : A Diner delivers food. Greater the distance, Longer the wait time resulting in bad customer experience. The Diner opens cloud kitchens in strategic locations and keeps best seller dishes ready to go to deliver faster.


**Time to live / Hop Limit** - 



