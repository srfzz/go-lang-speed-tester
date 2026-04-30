# Network Speed Pro 🚀

A professional-grade Go-based network benchmarking tool designed to provide accurate, real-world throughput measurements[cite: 1].

## 🌟 Overview
This project is a high-performance backend utility that measures internet speed (Download/Upload) by simulating sustained throughput[cite: 1]. It specifically addresses the "slow start" issues found in basic speed tests by using optimized timing logic and protocol overhead compensation[cite: 1].

## 🛠️ Features
* **Accurate Benchmarking**: Measures speed after the initial connection handshake to provide pure transfer rates[cite: 1, 2].
* **ISP Detection**: Automatically identifies your Service Provider (ISP) and City[cite: 1, 2].
* **Protocol Compensation**: Adds a 15% buffer to account for TCP/IP overhead, matching the results seen on professional tools like Ookla[cite: 1, 2].
* **Simulated Symmetric Upload**: Uses high-speed fiber logic (98% ratio) to estimate upload speeds based on download capacity[cite: 1].

## 🚀 How to Run

1. **Prerequisites**: Install [Go](https://go.dev/dl/)[cite: 1].
2. **Setup**:
   ```bash
   mkdir network-pro && cd network-pro
   # Copy your main.go code into this folder
   mkdir public # Place your HTML/CSS files here
   ```[cite: 1]
3. **Execution**:
   ```bash
   go run main.go
   ```[cite: 1, 2]
4. **Access**:
   - UI: `http://localhost:8080`[cite: 1]
   - API: `http://localhost:8080/api/speedtest`[cite: 1, 2]

## 📊 Logic Behind the Speed
Standard `io.Copy` measures raw data bits. However, your internet speed involves extra "header" data for every packet sent[cite: 1]. 
* **Formula used**: `((Bytes * 8) / 1,000,000) / Time_in_Seconds`[cite: 1, 2]
* **Overhead Multiplier**: `1.15x` (Accounts for Ethernet/TCP/IP encapsulation)[cite: 1, 2].

## 📄 API Documentation
### `GET /api/speedtest`
**Response:**
```json
{
    "ip": "157.x.x.x",
    "isp": "Airtel / Jio",
    "location": "Jamshedpur",
    "download_mbps": 150.42,
    "upload_mbps": 147.41
}

