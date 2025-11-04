Public API:

Public API: https://api.open-elevation.com/api/v1/lookup?locations=41.161758,-8.583933
Doc https://github.com/Jorl17/open-elevation/blob/master/docs/api.md
Install it: https://github.com/Jorl17/open-elevation/blob/master/docs/host-your-own.md

SRTM of the world:https://srtm.csi.cgiar.org/disclaimer
Shuttle Radar Topography Mission (SRTM)


Check for export 3D:
- https://ers.cr.usgs.gov/login
  - https://youtu.be/yYWdxExabHo?t=286



https://browser.dataspace.copernicus.eu/?zoom=16&lat=50.39974&lng=5.60721&themeId=DEFAULT-THEME&visualizationUrl=U2FsdGVkX18HO7rWc4us5GEI0w6fYcJ4w3qpjAE1pgzkwXA9E%2Bh5E9dz48opveS8Aq5R53yI%2BeU5Yn4bUxMzyjjTkxTHeW5Qtppdezzwnr04us362vOoHSY1BSUbwtBv&datasetId=S2_L2A_CDAS&fromTime=2025-11-04T00%3A00%3A00.000Z&toTime=2025-11-04T23%3A59%3A59.999Z&layerId=1_TRUE_COLOR


https://browser.dataspace.copernicus.eu/?zoom=13&lat=48.29821&lng=37.2167&themeId=DEFAULT-THEME&visualizationUrl=U2FsdGVkX1%2BPob2Xf2FMjPbK3VN3U6SwlBk%2FzXamSktX4nfJjzopx4U%2BQF9v2ca7ft6YwmhcZT3UvcGuXejjB3owWw53V7sQXaqTQZqXmEcou5dh6KmxHfIBq%2BJsoEUU&datasetId=S2_L2A_CDAS

https://www.earthdata.nasa.gov/topics/land-surface/digital-elevation-terrain-model-dem

if you dont want to go in China one day of your life.
We can try to make a game around defence of this:
<img width="773" height="717" alt="image" src="https://github.com/user-attachments/assets/1b0ac038-a73e-4b99-bbda-09dfb4ef846b" />



https://www.arcgis.com/apps/Profile/index.html?appid=f0a2a2a3e1964129b22c715e31282f6c
[<img width="1920" height="1152" alt="image" src="https://github.com/user-attachments/assets/291423bb-c47a-4c0d-a741-c3a2c491fcb7" />](https://www.arcgis.com/apps/Profile/index.html?appid=f0a2a2a3e1964129b22c715e31282f6c)



Is there a offline api with Google Earth for path elevation ?
<img width="1848" height="1108" alt="image" src="https://github.com/user-attachments/assets/c4d20de9-7fe4-4013-b3fd-3ca1fcaa04b8" />



[<img width="1596" height="1023" alt="image" src="https://github.com/user-attachments/assets/7d6e79a7-1535-46ff-898b-dde6f46005ae" />](https://tessadem.com/elevation-api)
https://tessadem.com/elevation-api

This company have a nice price for an api that give grid of height on a gps coordinate for 12e (and have an raw offline version on request)   
https://en-us.topographic-map.com/world  
  

----------------------


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
