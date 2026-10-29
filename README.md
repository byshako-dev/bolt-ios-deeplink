# Bolt (Taxify) iOS Deep Link

Open the Bolt app on iOS with preset destination coordinates:

```
taxify://action/bookaride?pickup=my_location&dropoff_latitude=LAT&dropoff_longitude=LNG&dropoff_title=NAME
```

## Parameters

* **pickup**: Use `my_location` to set the starting point to the user's current location.
* **dropoff_latitude**: Destination latitude (e.g. `40.409264`).
* **dropoff_longitude**: Destination longitude (e.g. `49.867092`).
* **dropoff_title**: Optional place name or address label (URL-encoded).

> **Note:** The path must be `action/bookaride`. Generic keys like `dest_lat` or `latitude` do not work on iOS.

## Code Examples

### Swift (iOS)

```swift
func openBolt(lat: Double, lng: Double, title: String) {
    let name = title.addingPercentEncoding(withAllowedCharacters: .urlQueryAllowed) ?? ""
    let urlString = "taxify://action/bookaride?pickup=my_location&dropoff_latitude=\(lat)&dropoff_longitude=\(lng)&dropoff_title=\(name)"
    
    if let url = URL(string: urlString) {
        UIApplication.shared.open(url)
    }
}
```

### JavaScript (Web)

```javascript
function openBolt(lat, lng, title = "") {
  const name = encodeURIComponent(title);
  window.location.href = `taxify://action/bookaride?pickup=my_location&dropoff_latitude=${lat}&dropoff_longitude=${lng}&dropoff_title=${name}`;
}
```

---

### 🔍 Related keywords
`bolt deeplink ios`, `taxify url scheme destination`, `open bolt with coordinates`, `bolt dropoff_latitude dropoff_longitude`, `taxify action/bookaride`, `bolt ridesharing ios deep link`
