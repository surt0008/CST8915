# Lab 2 – CST8915 Full-stack Cloud-native Development

## Demo Video
[Watch the demo video here](<https://youtu.be/sznJP2BrYWw>)

---

## Service Repositories
- [Order Service Repo](<https://github.com/surt0008/order-service-lab2-demo>)
- [Product Service Repo](<https://github.com/surt0008/product-service-lab2-demo>)
- [Store Front Repo](<https://github.com/surt0008/store-front-lab2-demo>)

---

## Reflection Questions

**1. What changes did you make to the order-service and product-service to comply with the Configurations and Backing Services factors of the 12-Factor App methodology?**  

I moved all hard-coded values like ports and RabbitMQ connection strings into .env files and made the services load them using environment variables. In the order-service, I installed and used the dotenv package to read configs, and in the product-service I added the dotenv crate in Rust to achieve the same. For backing services, I connected the order-service to RabbitMQ running on a separate VM using the connection string instead of keeping it local or embedded.

---

**2. Why is it important to use environment variables instead of hard-coding configurations in your application?**  

Environment variables make applications more flexible and portable. They allow the same code to run in different environments (development, testing, production) without changing the code itself. This prevents sensitive information like passwords, API keys, and connection strings from being exposed in the codebase, and it makes scaling or moving services much easier.

---

**3. Why is it important to have separate repositories for each microservice? How does this help maintain independence and scalability of each service?**  

Having separate repositories ensures each microservice has its own codebase, version control, and deployment lifecycle. This makes the services independent-teams can update, fix, or scale one service without affecting the others. It also improves scalability because each service can be deployed on different machines or scaled differently depending on its workload.

---

