# Firewall Configuration

## 1. Allow SSH

```bash
sudo ufw allow ssh
```

This rule allows incoming SSH traffic for remote administration.

## 2. Configure Default Policies

```bash
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

These commands block incoming connections by default while allowing outgoing connections.

## 3. Enable the Firewall

```bash
sudo ufw enable
sudo ufw status verbose
```

These commands activate the firewall and display its current status and default policies.

## 4. Allow the Web Application

```bash
sudo ufw allow 8080/tcp
sudo ufw status numbered
```

This rule allows incoming TCP connections to port 8080 for the web application.

## 5. Security Explanation

If `sudo ufw enable` is executed before `sudo ufw allow ssh`, incoming SSH connections may be blocked, potentially preventing remote administrators from accessing the server.

## 6. Verification

The Nginx application was tested using:

```bash
curl -I http://localhost:8080
```

Record the actual response and any troubleshooting performed during the laboratory.
