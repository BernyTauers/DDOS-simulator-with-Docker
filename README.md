#  DDoS Simulator with Docker

This project simulates a distributed denial-of-service (DDoS) attack in a controlled environment using Docker containers. Multiple Kali-based bots use `hping3` to flood a target Nginx server with different attack types over a custom Docker network.

---

## Technologies Used

-  **Docker & Docker Compose**
-  **Kali Linux (leplusorg/kali)**
-  **hping3** – for generating TCP/UDP/ICMP traffic
-  **Nginx** as the target server
-  **iftop** for live traffic monitoring
-  Custom Docker bridge network (`ddos_network`)

---

##  Project Structure

ddos-simulator/ ├── docker-compose.yml ├── server/ │ ├── Dockerfile │ ├── index.html │ └── style.css ├── attackers/ │

