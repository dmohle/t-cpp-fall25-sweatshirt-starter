# t-cpp-fall25-sweatshirt-starter
Template for CIT-66 “Do I Need a Sweatshirt?” project — C++ client/server programming using libcurl and JSON.

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

## 📂 Folder Structure
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

## 📂 Folder Structure
sweatShirt/
├── CMakeLists.txt ← build configuration for CLion
├── doIneedAsweatShirt.cpp ← main source code
├── /include ← header files
│ ├── /curl ← networking library headers
│ └── /nlohmann ← JSON parser header
├── /lib
│ └── libcurl.a ← static library (libcurl)
└── /certs
└── cacert.pem ← certificate bundle for HTTPS


---

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
The program extracts temperature, temperatureUnit, and shortForecast to build a simple weather summary.

🧑‍💻 Real-World Relevance

This program mirrors how many modern apps work:

Weather apps

Stock tickers

AI chatbots

News aggregators

All are clients that fetch data from remote servers using APIs.

🧩 Next Steps (Optional Challenge)

Try editing the gridpoint in main():

const string url = "https://api.weather.gov/gridpoints/HNX/53,100/forecast";

You can find gridpoints for other U.S. cities here:
👉 https://www.weather.gov/documentation/services-web-api

Then rebuild and see the forecast for your hometown!

🧱 Project Credits
Instructor: Dennis Mohle, Fresno City College
Libraries:
libcurl
 — for HTTPS client connections
nlohmann/json
 — for JSON parsing
Data Source: National Weather Service API

🏁 License
Educational use only.
© 2025 Fresno City College — CIT-66 Programming in C++.
---
