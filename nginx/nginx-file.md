```bash
# Define an upstream group named "backend_servers"
upstream backend_servers {
    server backend1.example.com:8080;
    server backend2.example.com:8080;
    server backend3.example.com:8080;
}

# Server configuration
server {
    listen 80;
    server_name yourwebsite.com;

    location / {
        # Proxy incoming requests to the "backend_servers" upstream group
        proxy_pass http://backend_servers;
    }
}
```

In this example:

We define an upstream block named backend_servers to group multiple backend servers. In this case, we have three backend servers `(backend1.example.com, backend2.example.com, and backend3.example.com)` listening on port 8080. You can replace these with your actual backend server addresses.

The server block listens on port 80 and specifies the server name `(yourwebsite.com)` that this configuration applies to. Adjust the server_name directive to match your domain.

In the location / { ... } block, we use the proxy_pass directive to proxy incoming requests to the backend_servers upstream group. Nginx will automatically load balance requests among the specified backend servers.

This configuration is a basic example of using Nginx for load balancing and reverse proxying. Requests to yourwebsite.com will be distributed among the backend servers defined in the upstream block. You can expand this configuration to include additional directives and fine-tune load balancing options as needed for your specific use case.