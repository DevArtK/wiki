
**What are Microservcies**
- Small targeted services
- Each service has it's own reppository
- Isolated from other services
    - Should not be bundled with other services when deployed
- Microservcies are loosely coupled
- Interacting with other services, should be done in a technology agnostic
  manner
    - RESTful webservices - HTTP / JSON



**Microservice Architecture**
- Applications are composed using individual microservices
- Each service will typically have it's own database
- Each microservice is independently deployable
- Scaling of individual serves is now possible
- CI/CD becomes easier since services are smaller and less complex to deploy



**Benefits of Microservices**
- Easier to understand + develop
- Software quality
- Scalability
- Reliability
- Technology flexibility



**Cons of Microservices**
- Integration testing can be difficult
- Deployments are more complex
    - Rather than one application to deploy, you now have many
- Operational cost with each service
    - Each service is a small application
    -  Needs own repo, own deployment process, own database, etc
- Additional hardware resources to run on



**How 'Big' Should a Microservice Be ?**
- A microservice can be as small as a single API endpoint
- Can be several or even dozens of API endpoints
- A microservice should be supported by a team you ca
