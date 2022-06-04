# SBA-5G

**Microservices** 

When the large applications are broken down into the different small services it's known to be microservices. Each service is performing the desired task and they can communicate with each other through an interface which is known as the SBI (service-based interface). By using the microservices architecture, they provide flexibility like different services performing their tasks and communicating with each other also. 

Suppose, if we want to add a few more services. Then these services will be added to an existing architecture without affecting the previous services. It helps in scalability, suppose if services are overloaded then instead of adding another service to make architecture larger, a new instance is created of that particular service. 



**Reference Point Representation 

The different elements represented are known as nodes or network elements and each node is built as a physical network function. That means they consist of a hardware box and each hardware box represents a particular physical network function to make it run. And they also have a different interface between the nodes. But it is not flexible. Suppose there was some scenario where we need to add one more physical network function then we need to configure the network element connection explicitly and other network elements to make them communicate. And if we create let's say a new instance of an existing network element or node. In that case, also we need to perform configuration over the entire network element. 



**Service-Based Architecture 

Instead of nodes or network elements here we call the elements as a network function. In the reference point architecture, we have physical network function and in service-based architecture, we have network function virtualization. This means that the network function can run on a server. So that, they don't need a hardware box to run their devices. It does not contain a unique interface and protocol instead of that, they use web-based interfaces. 
If we want to create one more network function or instance then it will be easily created or made and communication between the other network function is also provided, which makes it more flexible.



**Network Functions

It is generally considered a self-contained software module. It provides the set of services and then this service is offered through the web-based interface. They consist of two modes. First, suppose there was one network function that is producing a set of services and now for other services other network functions that produced services are now consumed by them. In brief, let's say there were two network functions. 

Network function-1 requests a service to be consumed from network function-2. Now the network function-2 produces the service and then sends back a response that contains the services to be consumed by the requested network function. This is a request-response based system.

Now there was another method in which let's say network function-1 subscribes to a network function-2. So that whenever the criteria are met. It will provide the service to the network function-1. Through this, one thing is clear it is not necessary to send a request every time to get the desired services. 


**Interfaces

In a 5G system, the network function uses an HTTP REST (representational state transfer) based interface. It was defined by the set of design rules through which they know how the communication between the different software modules is to be done in the network architecture. It is a list of the most commonly used HTTP REST commands as follows 

i) GET (To send the data from the server) <br />
ii) POST (To send the data to the server)<br />
iii) PUT (To send the data and also replace the data from the server) <br />
iv) DELETE (To remove the data from the server )<br />

By using these commands, the network function can communicate with each other. 



**Service Discovery (NRF)

As we discussed previously, the network function has the role of the consumer as well as the producer. Now, there is a phenomenon known as service discovery under which there was a function known as NRF (network repository function). And it tracks all the network functions including the network function which were newly added to the network.

So, the network function should know about the NRF. The NRF is considered a dictionary because when one network function wants to know something about another network function. They can reach the NRF and get the information. 

**Example: Service registration 

In this scenario, we have added a new PCF to the network. Now, service registration is performed by using the HTTP PUT command for adding the information to their database. Now the NRF stores the information coming from the PCF. After that, it sends back a response containing information that now, knows where the new PCF is located in the network. 

Step second, the service discovery is performed. Here AMF wants to communicate with PCF but it does not have an idea where it was located in the network. But all the network function knows the NRF. Now, the AMF sends a request to the NRF for getting information about the PCF which provides the requested services. Then, the NRF search in its database and see if there is any information matching the requested message. 
When the NRF finds the PCF, it sends back the response to the AMF that contained information about the list of PCFs that matches the requested criteria. 

After that request will check the policy of the requested device by providing the device ID. Then PCF will search into its database and find the policies related to that particular device and then send back the response to the AMF that contains pieces of information related to the policy of that device.
