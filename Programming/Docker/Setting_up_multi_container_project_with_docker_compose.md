
**File Structure Overview: docker-compose.yml**

Here are the containers I want to create :

```
    redis-server
        Make it using 'redis' image
    node-app
        Make it using the Dockerfile in the current directory
        Map port 4001 on local machine to 8081 on container
```

**Docker-Compose file**
