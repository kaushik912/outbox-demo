# Transactional Outbox Pattern — Spring Boot demo

A minimal, runnable example of the **transactional outbox** pattern.

`POST /register` writes a **user row** and an **outbox row** in the *same* DB
transaction. A scheduled **relay** later reads unprocessed outbox rows, publishes
them to **Kafka**, and marks them processed. A **consumer** subscribes to the
topic to prove the fan-out.
