---
description: Use Docker to set up Hyperswitch app server
---

# 🐳 Run app server

{% hint style="info" %}
Let's hit the ground running – within five minutes, you’ll see a complete end-to-end example of installing Hyperswitch and making a Payment via a Payment provider of your choice. So, let’s get started!
{% endhint %}

{% embed url="https://www.loom.com/embed/a9b2b42fb72e4691a06e6121b330ebe9?sid=76bf9484-8f0f-462e-95a2-b4f551cd51ed" %}

## **Setting up with Docker**

If you don't already have Docker, you can [download](https://docs.docker.com/get-docker/) it from the official Docker website. Once Docker is installed, launch the Docker app, then use the following commands at the command line to clone the Hyperswitch repository.

```
git clone https://github.com/juspay/hyperswitch
```

Once the repository is cloned, switch to the project directory.

```
cd hyperswitch
```

Now, we'll start all services using Docker Compose. This will pull Hyperswitch Docker images and then start the server. Wait for the `migration_runner` container to finish running migrations (approximately 2 minutes) before proceeding further.

```
docker compose up -d
```

Congratulations! You've now setup Hyperswitch in your local machine. In order to verify that the server is up and running hit the health endpoint.

```
curl --head --request GET 'http://localhost:8080/health'
```

The expected response here is `200 OK` status code. This indicates that the server and all of its dependent services such as the database and Redis are functioning correctly.

In the next chapter, we'll run payments through your local Hyperswitch setup by setting up the necessary accounts, API credentials and try out payments and refunds.

**Note** : In case you want to set up Hyperswitch from scratch in your local system, please goto this tutorial - [Setup Hyperswitch from scratch](broken-reference)&#x20;

