# Lab 8 - CST8915 Full-stack Cloud-native Development  

## Demo Video  
[Watch Demo Video on YouTube](https://www.youtube.com/watch?v=lsOCmvhjlEg)  

---

## Task 2 – Written Explanation (MongoDB + RabbitMQ Persistence)

### MongoDB Replica Set + Persistence  
For Task 2, MongoDB was deployed as a **StatefulSet with 3 replicas** using a **headless service** to support replica-set networking.

Each pod receives its own persistent disk through a PVC:

- `mongodb-0`
- `mongodb-1`
- `mongodb-2`

This ensures data is not lost when pods are deleted or recreated.

#### Steps I Performed
- Connected to the primary MongoDB pod using the `mongo` shell  
- Inserted test data into the `orderdb` database  
- Deleted the primary pod (`mongodb-0`)  
- Kubernetes recreated the pod  
- MongoDB automatically elected a new PRIMARY  
- Verified that the inserted data persisted 

## For the rabbitmq part, I was not able to login to the localhost as it was saying not authorized even if I was entering right username and password.

