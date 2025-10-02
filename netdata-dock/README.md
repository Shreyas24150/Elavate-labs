# 📊 System Monitoring with Netdata (via Docker)

## 🎯 Objective
Install **Netdata** to visualize system and application performance metrics in real time.

---

## 🛠 Tools
- [Netdata](https://www.netdata.cloud/) (free, open-source monitoring tool)
- Docker

---

## ⚡ Setup Instructions

### 1. Run Netdata in Docker
```
docker run -d --name=netdata \
  -p 19999:19999 \
  --cap-add SYS_PTRACE \
  --security-opt apparmor=unconfined \
  netdata/netdata
```

### 2. Verify Container
```
docker ps
```
You should see netdata running and port 19999 mapped.

### 3. Access Dashboard
```
Open your browser → http://localhost:19999

If using WSL2/VM, replace localhost with your host machine’s IP.
```

---

## 📈 Metrics to Explore
```
CPU Usage – per-core and overall load
Memory Usage – RAM consumption
Disk I/O – reads/writes, utilization
Network Traffic – incoming/outgoing packets
Docker Containers – per-container usage
```

---

## 🚨 Alerts & Panels
```
Netdata comes with built-in alerts (high CPU, memory pressure, etc.).
Explore different chart panels in the dashboard.
```

---

## 📂 Logs

Netdata stores logs inside the container at /var/log/netdata.
Access them with:
```
docker exec -it netdata bash
cd /var/log/netdata
ls -l
cat error.log
tail -f access.log
```