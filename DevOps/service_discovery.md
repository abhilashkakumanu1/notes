## Resources

1. Great starting point for service discovery - [link](https://www.getambassador.io/resources/service-discovery-microservices/)

Service discovery is how applications and (micro)services locate each other on a network. In the case of microservices, instead of hard coding the config (ip, port, etc) we can setup a central system that helps in the lookup. So, if anything changes it only has to be changed in one place.

### client-side service discovery vs server-side service discovery

**Client-side discovery**: When using client‑side discovery, the client is responsible for determining the network locations of available service instances and load balancing requests across them. The client queries a **service registry**, which is a database of available service instances. The client then uses a load‑balancing algorithm to select one of the available service instances and makes a request.

The service instance’s registration is typically refreshed periodically using a heartbeat mechanism.

**Server-side discovery**: The client makes a request to a service via a load balancer. The load balancer queries the service registry and routes each request to an available service instance.

Examples - [Netflix's Eureka](https://github.com/Netflix/eureka) (REST API based service registry), [etcd](https://github.com/etcd-io/etcd) (used in kubernetes), [cosul](https://www.consul.io/), Apache Zookeeper
