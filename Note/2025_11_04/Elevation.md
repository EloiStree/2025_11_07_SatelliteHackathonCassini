# GPT

Got it 👍 — you’re looking for an **API that returns the elevation (height above sea level)** for a given GPS location (latitude and longitude).

Here are the best options — all of them are actively maintained and provide reliable results:

---

### 🗺️ 1. **Google Maps Elevation API**

**✅ Most accurate, global coverage**

* **Endpoint example:**

  ```
  https://maps.googleapis.com/maps/api/elevation/json?locations=40.714728,-73.998672&key=YOUR_API_KEY
  ```
* **Response:**

  ```json
  {
    "results": [
      {
        "elevation": 8.123456,
        "location": { "lat": 40.714728, "lng": -73.998672 },
        "resolution": 4.771975994110107
      }
    ],
    "status": "OK"
  }
  ```
* **Docs:** [Google Elevation API](https://developers.google.com/maps/documentation/elevation)

---

### 🌍 2. **Open-Elevation API (Free & Open Source)**

**✅ Free, no key needed | ⚠️ Slower and less reliable at scale**

* **Endpoint example:**

  ```
  https://api.open-elevation.com/api/v1/lookup?locations=40.714728,-73.998672
  ```
* **Response:**

  ```json
  {
    "results": [
      { "latitude": 40.714728, "longitude": -73.998672, "elevation": 10 }
    ]
  }
  ```
* **Docs:** [open-elevation.com](https://open-elevation.com)

---

### 🛰️ 3. **OpenTopoData API**

**✅ Multiple elevation datasets (SRTM, Mapzen, EU DEM, etc.)**

* **Endpoint example:**

  ```
  https://api.opentopodata.org/v1/srtm90m?locations=40.714728,-73.998672
  ```
* **Response:**

  ```json
  {
    "results": [
      { "elevation": 9, "location": { "lat": 40.714728, "lng": -73.998672 } }
    ],
    "status": "OK"
  }
  ```
* **Docs:** [opentopodata.org](https://www.opentopodata.org/)

---

### ⚙️ Example (in Python)

```python
import requests

lat, lon = 40.714728, -73.998672
url = f"https://api.opentopodata.org/v1/srtm90m?locations={lat},{lon}"

res = requests.get(url)
data = res.json()
elevation = data['results'][0]['elevation']
print("Elevation:", elevation, "meters")
```

---

Would you like me to recommend **the best option** for your specific use case (e.g., mobile app, large-scale batch queries, offline use, etc.)?
