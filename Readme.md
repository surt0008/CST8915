# Lab1_25F_CST8915_Algonquin_Pet_Store
## Youtube Link For the Demo: https://youtu.be/FwYZ1uCoTBI
## Explantions about each services
* **Order Service** → Node.js (`index.js`, `package.json`)
* **Product Service** → Rust (`Cargo.toml`, `src`)
* **Store Front** → Vue.js (`src`, `vue.config.js`)

### Order Service (Node.js)

The order service is like the “order manager” of the pet store app. Its main job is to take care of everything related to orders  when a customer buys something, this service is the one handling it. It’s written in Node.js, which is a JavaScript runtime that makes it easy to build server applications.

This service talks with other parts of the system using things like APIs and RabbitMQ (a message queue that lets services send messages to each other without being directly connected). For example, when someone places an order from the store front, that request comes here. Then it might send a message to the product service to check product details, or use RabbitMQ to update other parts of the system.

---

### Product Service (Rust)

The product service is like the “catalog” for the pet store. It knows about all the products like what’s available, what their details are, and helps answer questions like “do we have this item in stock?” It is built in Rust, a programming language that is fast and safe, so this service can handle product information very efficiently.

It interacts with the other services by receiving requests (like from the order service when an order is placed) and sending back product details. Sometimes it communicates through APIs, and sometimes through RabbitMQ messages. Basically, if the system needs to know something about a product, this service is the one that answers.

---

### Store Front (Vue.js)

The store front is what customers actually see when they visit the pet store online. It’s the front-end part of the system, built with Vue.js, which is a JavaScript framework for building user interfaces. This is the website that shows the products, lets users add them to the cart, and place orders.

It connects to the other services (like the order service and product service) through APIs. For example, when a customer clicks “Buy,” the store front sends that request to the order service. When it needs to display products, it asks the product service. So, the store front is the “face” of the system, while the other services work behind the scenes.


