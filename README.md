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


##  What This Project Does

- Simulates a **botnet** using multiple attacking containers (`bot1`, `bot2`, `bot3`.)
- Performs attack types:
  -  **TCP SYN Flood**
  -  **UDP Flood**
  -  **ICMP Flood**
- Provides live network traffic monitoring via `iftop`
- Uses a custom Docker network for realistic container communication
  

---

##  How to Use It

1. Clone this repository:
   ```bash
   git clone https://github.com/BernyTauers/DDOS-simulator-with-Docker.git
   cd DDOS-simulator-with-Docker
   ```

2. Create a network
   ```bash
   docker network create --subnet 192.168.0.0/24 --gateway 192.168.0.1 ddos_network
   ```
3. Launch the enviorment
   ```bash
   docker-compose up --build -d
   ```
4. Monitor Traffic
```bash
docker exec -it nginx_server bash
apt update && apt install -y iftop
iftop -i eth0
```
