# Lab 3 - CST8915 Full-stack Cloud-native Development  

## Demo Video  
[Watch Demo Video on YouTube](https://youtu.be/ZNufnGnxebU)  

---
## Service Repositories  

- [Order-Service Repository](https://github.com/surt0008/order-service-lab2-demo)  
- [Product-Service Repository](https://github.com/surt0008/product-service-lab2-demo-py)  
- [Store-Front Repository](https://github.com/surt0008/store-front-lab2-demo)  

---
## Reflection Questions  

**1. What challenges did you encounter when configuring environment variables in the GitHub Actions workflow?**  
At first it was confusing because unlike the backend, the frontend (Vue.js) cannot read variables at runtime. I had to learn that the variables must be added inside the GitHub Actions workflow so they get built directly into the app. The challenge was finding the right place in the workflow file and making sure the URLs matched my deployed services.  

**2. How does deploying microservices on Azure Web App Service differ from running them locally?**  
Running locally was simple because everything used `.env` files and ran on my machine. On Azure Web App Service, I had to set environment variables in the portal, push code to GitHub, and let Azure handle deployment. The main difference is that Azure manages the servers, scaling, and setup, so I didn’t have to worry about VMs, but I had to carefully configure things in the cloud.  

**3. Why is it important to use environment variables for configurations in a cloud environment?**  
Environment variables make the app flexible and secure. They let us change things like service URLs or connection strings without editing the code. This is important in the cloud because services can move or scale, and we don’t want to hardcode sensitive info like passwords or URLs into the code.  

---
## Notes  
This lab showed me how to move from VM-based deployment to Azure managed services. I learned how to use environment variables in GitHub Actions and Azure App Service, and how everything connects together with RabbitMQ.  
