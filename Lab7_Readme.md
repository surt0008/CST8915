# Lab 7 – Introduction to Kubernetes Basics
**Course:** CST8915 – Full-stack Cloud-native Development  
**Name:** Rohan Surti  

---

##  Demo Video
[YouTube Link](https://youtu.be/btDXoNv6cmU)

---
## RabbitMQ Configuration Analysis

### 1. Is RabbitMQ stateless or stateful?
RabbitMQ is stateful because it stores messages and queue data inside the container.  
If the pod restarts or gets deleted, the stored messages will be lost unless we use some kind of permanent storage.

---

### 2. What happens when the RabbitMQ pod is deleted or restarted?
When the RabbitMQ pod is deleted or restarted, all the data inside it gets deleted too.  
That means all the messages in the queues will disappear.  
The app will start again, but the old data will not come back.

---

### 3. Implications of running without persistent storage
Without persistent storage:
- All queue data is lost when the pod restarts or moves.
- It can cause message loss and problems in the system.
- The app may not work properly if RabbitMQ is holding important messages.

---

### 4. Possible solutions
To fix this, RabbitMQ should have persistent storage.  
We can do that by:
- Using a StatefulSet instead of a Deployment.
- Adding a PersistentVolumeClaim (PVC) so data is saved even after restart.

This way, RabbitMQ will keep its data safe.

---

### 5. Would Azure Service Bus solve the issue?
Yes, using Azure Service Bus would solve this issue.  
It is a managed service from Microsoft that already stores messages safely.  
We don’t have to manage pods or storage by ourselves.  
But it may cost more and require some changes in the app code.

---

### 6. Summary
Right now, RabbitMQ in the YAML file is stateless.  
If the pod restarts, messages are lost.  
To fix it, we can add storage or use Azure Service Bus for reliable message handling.