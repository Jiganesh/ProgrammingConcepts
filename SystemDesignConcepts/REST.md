# REST

REST - REpresentation State Transfer is not a protocol or a standard, it is an architectural style.

A Web API or Web Service conforming to the REST architectural style is called REST API ( RESTful API)


**The SIX Guiding Principles of REST**

- Uniform Interface : REST defines a consistent and uniform interface for interactions between clients adn servers. For example HTTP based REST API's make use of the standard HTTP methods (GET, POST, PUT, DELETE etc) and URIs (Uniform Resource Identifiers) to identify resources
- Client-Server : The client-server design pattern enforces the separation of concerns which helps the client and the server components evolve independently.
- Stateless :It mandates each request from the client tot the server must contain all of the information necessary to understand and complet the request. 
- Cacheable : The cacheable constraint requires that a response should implicitly or explicitly label itself as cacheable or non-cacheable. If the response is cacheable, the client application gets the  right to reuse the response data later for equivalent requests and a specified period.
- Layered System : The layered system style allows an architecture to be composed of hierarchical layers by constraining component behavior. In a layered system, each component cannot see beyond the immediate layer they are interacting with. 
- Code on Demand (Optional) : REST also allows client functionality to be extended by downloading and executing code in the form of applets or scripts. The downloaded code simplifies clients by reducing the number of features required to be pre-implemented. Servers can provide part of the features delivered to the client in the form of code, and the client only needs to execute the code.


**Resource**


The key abstraction of information in REST is a resource. Any information that we can name can be a resource. For example, a REST resource can be a document or image, a temporal service, a collection of other resources, or a non-virtual object (e.g., a person).

The state of the resource at any particular time is known as the resource representation. The resource representations consist of:

    the data
    the metadata describing the data
    and the hypermedia links that can help the clients transition to the next desired state.


**REST and HTTP are Not the Same**


All these principles help RESTful applications to be simple, lightweight, and fast.