# 🛵 Smart Delivery

A web app that plans fast delivery routes and verifies parcels using maths and algorithms.
Built with Python and Streamlit as a 1st year engineering project at
BGS College of Engineering and Technology.

**Live app:** https://smart-delivery-gyhzumgpa97wnvfqrmihzn.streamlit.app/

## Features

- **Live Traffic Routing:** shows up to 3 different road routes on a map, with an ETA and distance for each. The fastest route is highlighted.
- **Multi-drop Planning:** picks the best order for several delivery stops using the Travelling Salesman Problem (nearest-neighbour + 2-opt).
- **Rider Simulation:** a slider moves the delivery bike along the chosen route.
- **Damage-proof QR Scanner:** matches parcels even when the QR code is damaged, using error correction and edit distance.
- **Damage Lab:** corrupt characters on purpose and see whether the scanner still finds the right parcel.

## Maths used

| Feature | Maths |
|---|---|
| Distance between places | Haversine formula |
| Rush-hour traffic | Gaussian curves (peaks at 9 AM and 6 PM) |
| Travel time | Speed drops linearly with congestion, t = d / v |
| Multi-drop order | TSP with nearest-neighbour and 2-opt |
| QR matching | Levenshtein distance (dynamic programming), Reed-Solomon codes |

## Tech stack

Python, Streamlit, Folium, OpenStreetMap, OSRM, OpenCV, NumPy, qrcode, Pillow

## Run it on your computer

```
pip install -r requirements.txt
streamlit run app.py
```

## Team

PUNEETH S, MANU G N, RAGHUNANDAN, PANCHAM GOWDA V R, PRABHAKAR

## Note

Free OSRM has no live traffic data, so congestion is modelled with a mathematical rush-hour model.
A real traffic API key (TomTom or Google) can be added for real data.
