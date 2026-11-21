# A2.2 – Networking Services

## Introduction

Networking services allow students and administrators to access the university result portal. The network should provide secure communication between users, the web server and the database.

## IP Addressing

The university should use private IP addresses for internal servers. A proposed network design is:

| Component | Example IP address | Purpose |
|---|---|---|
| Nginx server | 192.168.10.10 | Receives student requests |
| Python application server | 192.168.10.20 | Runs the result portal |
| Database server | 192.168.10.30 | Stores student records |
| Administrator computer | 192.168.10.50 | Server administration |

These are example addresses for the proposed design. Actual addresses must be assigned according to the university network.

The database server should not be directly accessible from the public internet.

## DNS Configuration

DNS converts domain names into IP addresses.

The university can use a domain name such as:

`results.university.edu`

The DNS record should point to the public IP address of the university's load balancer or reverse proxy.

Students can access the portal using the domain name instead of remembering an IP address.

## Nginx Reverse Proxy

Nginx is a web server that can also work as a reverse proxy. It receives incoming student requests and forwards them to the Python application.

Proposed request flow:

1. A student opens `https://results.university.edu`.
2. DNS resolves the domain name.
3. The request reaches the Nginx server.
4. Nginx forwards the request to the Python application.
5. The application retrieves the required information from the database.
6. The result is returned to the student through Nginx.

Example Nginx configuration:

```nginx
server {
    listen 80;
    server_name results.university.edu;

    location / {
        proxy_pass http://127.0.0.1:8000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
        proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
}
```

For production, HTTPS should be configured using a valid TLS certificate. HTTP requests should be redirected to HTTPS.

## Firewall Rules

A firewall controls incoming and outgoing network traffic.

The university server should allow only the required network services.

| Port | Protocol | Purpose |
|---|---|---|
| 22 | TCP | SSH administration, restricted to administrator IPs |
| 80 | TCP | HTTP access and HTTPS redirection |
| 443 | TCP | Secure HTTPS access |
| 8000 | TCP | Internal Python application access only |
| 5432 | TCP | PostgreSQL database access only from authorized application servers |

The application and database ports should not be exposed publicly.

Example UFW commands:

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing

sudo ufw allow from 192.168.10.50 to any port 22 proto tcp
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp

sudo ufw enable
sudo ufw status
```

The SSH rule should be adjusted to the real administrator IP address before enabling the firewall. This avoids accidentally blocking remote administration.

## SSH Access with Keys

SSH provides secure remote access to the Linux server. Key-based authentication is safer than relying only on passwords.

Steps:

1. Generate an SSH key pair on the administrator's computer.
2. Copy the public key to the server.
3. Test login using the private key.
4. Restrict SSH access to authorized administrator accounts.
5. After confirming key access, disable password-based SSH login if the administration policy permits it.

Example commands:

```bash
ssh-keygen -t ed25519
ssh-copy-id admin@192.168.10.10
ssh admin@192.168.10.10
```

The private key must remain on the administrator's computer and must never be shared.

## Evaluation for the Result Portal

The proposed network separates public access from internal application and database communication. Nginx handles incoming web requests, DNS provides a simple domain name, firewall rules restrict access and SSH keys protect remote administration.

## Conclusion

A secure networking design helps students access the result portal while protecting the application server, database and administrative access.
