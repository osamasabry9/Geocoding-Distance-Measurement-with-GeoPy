# 🌍 Geocoding & Distance Measurement with GeoPy 

This project demonstrates practical applications of **geocoding, reverse geocoding, and distance calculation** using real city data from the **United Arab Emirates**, powered by `GeoPy`, `Pandas`, and `Folium`.

🗂️ Main Notebook: [`Geocoding_&_Distance_Measurement_with_GeoPy.ipynb`](./Geocoding_&_Distance_Measurement_with_GeoPy.ipynb)

---

## 🚀 Features

- ✅ Batch **geocoding** of multiple locations (using OpenStreetMap/Nominatim)
- ✅ **Reverse geocoding** from latitude/longitude to full address
- ✅ **Distance calculation** between two cities using geodesic measurement
- ✅ **Interactive map visualization** with `folium`
- ✅ Real data: UAE cities with latitude, longitude, population, etc.

---

## 📁 Dataset

The file `ae_addresses.csv` contains structured data on UAE cities:
- `city`, `lat`, `lng`
- `admin_name`, `country`, `population`

> Example:

| City        | Latitude | Longitude | Emirate     |
|-------------|----------|-----------|-------------|
| Dubai       | 25.2631  | 55.2972   | Dubayy      |
| Abu Dhabi   | 24.4667  | 54.3667   | Abū Z̧aby   |
| Sharjah     | 25.3575  | 55.3908   | Ash Shāriqah |

---

## 🔧 Installation (Google Colab or Local)

```bash
pip install geopy folium pandas
````

---

## 🧪 Example Code Snippets

### 🔹 Geocode a location

```python
from geopy.geocoders import Nominatim
geolocator = Nominatim(user_agent="uae_locator")
location = geolocator.geocode("Ajman University, UAE")
print(location.latitude, location.longitude)
```

### 🔹 Reverse geocode

```python
point = (25.1972, 55.2744)  # Burj Khalifa
address = geolocator.reverse(point)
print(address.address)
```

### 🔹 Distance between two cities

```python
from geopy.distance import geodesic
dubai = (25.2631, 55.2972)
abu_dhabi = (24.4667, 54.3667)
distance_km = geodesic(dubai, abu_dhabi).km
print(f"{distance_km:.2f} km")
```

### 🔹 Folium interactive map

```python
import folium
m = folium.Map(location=[25.2, 55.3], zoom_start=7)
folium.Marker([25.2631, 55.2972], tooltip="Dubai").add_to(m)
m.save("uae_map.html")
```

---

## 📦 Folder Structure

```
Geocoding-Distance-Measurement-with-GeoPy/
│
├── ae_addresses.csv                             # Dataset of UAE cities
├── Geocoding_&_Distance_Measurement_with_GeoPy.ipynb  # Main notebook
├── uae_map.html                                 # Output map (optional)
├── dubai_cities.csv                             # Example filtered output
└── README.md
```

---

## 📌 Learning Objectives

* Understand and apply geocoding concepts in real-world datasets
* Perform reverse lookups and interpret location metadata
* Measure accurate distances using geodesic formula
* Use `folium` to build interactive maps

---

## 📄 License

All data used is public domain via OpenStreetMap (ODbL).
This repository is for educational and non-commercial purposes.

---
