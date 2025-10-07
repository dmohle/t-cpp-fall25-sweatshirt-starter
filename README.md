# t-cpp-fall25-sweatshirt-starter
Template for CIT-66 “Do I Need a Sweatshirt?” project — C++ client/server programming using libcurl and JSON.

📥 [Download Starter Project (ZIP)](./sweatShirt_Starter_Fall25.zip)


# 🧥 CIT-66 — *Do I Need a Sweatshirt?*  
### Fresno City College • Fall 2025  
**Instructor:** Professor Dennis Mohle  

---

## 📘 Overview
This project demonstrates how a **C++ client program** connects to a remote **web server** using HTTPS and parses JSON data returned by a REST API.

Your program connects to the **National Weather Service (NWS) API** to retrieve a forecast for Fresno, California — then displays:
- 🌡️ Temperature  
- 🌤️ Conditions (e.g., Sunny, Cloudy)  
- 🧥 A friendly “Do I need a sweatshirt?” recommendation  

### 💡 Concepts Covered
- HTTP / HTTPS networking  
- Secure Sockets (TLS / SSL)  
- REST APIs  
- JSON data parsing  
- Client–Server architecture in action  

---

## 📂 Project Root Folder: /sweatShirt
##
## /sweatShirt
## --CMakeLists.txt              // Build configuration for CLion/CMake
## --doIneedAsweatShirt.cpp      // Main source file
## --/include                    // Header-only libraries
## ----/curl                     // libcurl headers
## ------curl.h
## ------easy.h
## ------curlver.h
## ----/nlohmann                  // JSON library (header-only)
## ----json.hpp
## --lib/                        // Prebuilt static libraries
## ----libcurl.a                 // libcurl (static)
## --certs/                      // TLS certificate bundle for HTTPS
## ----cacert.pem
## --/cmake-build-debug             // Auto-generated build output (binary lives here)


---

## 📘 Overview
This project demonstrates how a **C++ client program** connects to a remote **web server** using HTTPS and parses JSON data returned by a REST API.

Your program connects to the **National Weather Service (NWS) API** to retrieve a forecast for Fresno, California — then displays:
- 🌡️ Temperature  
- 🌤️ Conditions (e.g., Sunny, Cloudy)  
- 🧥 A friendly “Do I need a sweatshirt?” recommendation  

### 💡 Concepts Covered
- HTTP / HTTPS networking  
- Secure Sockets (TLS / SSL)  
- REST APIs  
- JSON data parsing  
- Client–Server architecture in action  

## ⚙️ How to Open and Run in CLion

### 1️⃣ Unzip or Clone the Project
Unzip the project into a simple directory like:

C:\cppProjects\sweatShirt

If this project was assigned via **GitHub Classroom**, it will already be in your GitHub repository — just open that folder in CLion.

---

### 2️⃣ Open in CLion
In CLion:
- Go to **File → Open**
- Select the **sweatShirt** folder  
- Wait for CMake to configure automatically.

---

### 3️⃣ Build and Run
Click the green ▶️ **Run** button.  
You should see output similar to:

Using CA cert: "C:\cppProjects\sweatShirt\certs\cacert.pem"

--- Fresno Forecast (This Afternoon) ---
Temperature: 87°F
Conditions: Sunny
Recommendation: NO — it’s warm enough today.


---

## 🧰 Troubleshooting

| Problem | Likely Cause | Fix |
|----------|--------------|-----|
| `curl error: Problem with the SSL CA cert` | `cacert.pem` file not found | Make sure `/certs/cacert.pem` exists and is not empty. |
| Red folder names (curl or nlohmann) | CLion didn’t reload paths | Right-click `CMakeLists.txt` → **Reload CMake Project** |
| Weird characters like `ΓÇÖ` or `┬░` | Console isn’t using UTF-8 | Already fixed in this version with `SetConsoleOutputCP(CP_UTF8);` |

---

## 🧠 Learning Notes

### 🌍 Client–Server Model
- **Client:** Your C++ program (the request sender)  
- **Server:** The National Weather Service API (the data provider)  

The client sends an HTTPS request, and the server replies with structured JSON data.

### 🔒 Secure Communication
- Uses **HTTPS (port 443)** for encryption.
- The certificate bundle `cacert.pem` verifies the server’s authenticity.

### 🧩 JSON Data
The NWS API returns a JSON structure like:
```json
{
  "properties": {
    "periods": [
      {
        "name": "This Afternoon",
        "temperature": 87,
        "temperatureUnit": "F",
        "shortForecast": "Sunny"
      }
    ]
  }
}

