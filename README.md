# 🌦️ Weather Lookup API

A MuleSoft integration that retrieves live weather information from an external REST API and returns a formatted JSON response.
This project demonstrates **API orchestration**, **external HTTP calls**, **DataWeave transformations**, and **error handling** using Mule 4.

---

## 📌 Project Overview

The **Weather Lookup API** exposes a single endpoint where clients can pass a city name and receive current weather details from an external weather service (e.g., *Open-Meteo API*).

### **Key Features**

* REST API built with Mule 4
* External API call using HTTP Request Connector
* Query parameter processing
* DataWeave JSON transformation
* Try / On Error Propagate error handling

---

## 🧱 Architecture

```
Client → MuleSoft API → External Weather API → MuleSoft Transformation → Client
```

### Flow Overview

1. **HTTP Listener** receives `GET /weather?city=...`
2. **External Weather API Call** fetches live data
3. **DataWeave Transformation** formats the output
4. **Error Handler** catches failures and returns readable error responses

---

## 📁 Project Structure

```
weather-lookup-api/
 ├── src/
 │   └── main/
 │       ├── mule/
 │       │   ├── weatherapi.xml
 │       │   └── global.xml
 ├── postman/
 │   └── Weather Lookup.postman_collection.json
 ├── README.md
 └── pom.xml
```

---

## 🚀 Running the Project

### **Prerequisites**

* Anypoint Studio **7.x**
* Mule Runtime **4.x**
* Internet access

### **Steps**

1. Clone the repo:

   ```bash
   git clone https://github.com/Meigetsuu/weatherAPI.git
   ```
2. Import into **Anypoint Studio**
3. Configure HTTP Listener port if needed
4. Run the Mule application
5. Test using Postman or browser

---

## 🧪 API Usage

### **Endpoint**

```
GET /weather?city=<cityName>
```

### Example Request

```
http://localhost:8081/weather?city=Paris
```

### Example Success Response

```text
La température dans la ville de Lyon est actuellement de 11.2°C
```

---

## 🔐 Error Handling

The API handles:

* Missing `city` query parameter
* External API failure
* Bad or unsupported city names

### Example Error Response

```json
{
  {
	error: "Erreur: coordonnées invalides."
  }
}
```

---

## 🛠️ Tech Stack

* **MuleSoft Anypoint Studio**
* **Mule 4**
* **DataWeave 2.0**
* **HTTP Request Connector**
* **Open-Meteo**

---

## 📸 Screenshots

** Anypoint Studio Diagram **
![Anypoint Studio Flows](https://github.com/user-attachments/assets/bfa91aa9-a1fe-4718-9f8b-7b543e4b2fe2)

** Successfull request **
![Postamn request successfull](https://github.com/user-attachments/assets/922759af-9c9b-41f6-80f2-3b06276591d4)

** Failed request **
![postman request failure](https://github.com/user-attachments/assets/9e617e5d-87e7-456d-93dc-0889eb9664d2)

---

## 📚 Future Enhancements

* Add caching for repeated requests
* Add multi-day forecast support
* Publish and manage API on Anypoint Platform

---

## 👤 Author

**Kevin Roussel**
*MuleSoft Developer*

* LinkedIn: [Click here](https://www.linkedin.com/in/kevin-roussel-15254178/)
* GitHub: [Click here](https://github.com/Meigetsuu)
