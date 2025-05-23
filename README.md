# ⏱️ Epoch Time Display Website

This GitHub Pages site displays the **current epoch time (Unix timestamp)** and its **human-readable equivalent** in real-time. It is specifically designed to be **camera and OCR-friendly**, enabling timestamp extraction from video frames during dataset collection.

🔗 **Live demo**: [https://olayasturias.github.io/epoch-time-page](https://olayasturias.github.io/epoch-time-page)

---

## ✨ Features

- **Epoch Time with Milliseconds**: Continuously updated using `requestAnimationFrame` (~60 Hz).
- **Human-readable Time**: Toggle between UTC and local time.
- **Dark Mode Toggle**: Improves readability across lighting conditions.
- **OCR-Optimized Display**:
  - High-contrast yellow-on-black text
  - Large, monospaced digits using [OCR-B](https://en.wikipedia.org/wiki/OCR-B)
  - Designed for visual parsing from video frames

---

## 📷 Use Case: Time-Synchronizing Devices via Screen Recording

This website is especially useful when collecting datasets with **independent devices that don’t share a common clock** (e.g., multiple cameras, sensors, or embedded systems).

### ✅ Workflow:

1. Open this site fullscreen on a monitor or tablet.
2. Begin recording all devices (cameras, sensors, etc.).
3. Capture the screen showing this timestamp as part of the recording.
4. Later, extract the timestamp from video frames using OCR (e.g., [Tesseract OCR](https://github.com/tesseract-ocr/tesseract)).
5. Align device data based on the visible timestamp.

This allows **coarse synchronization** between unsynchronized systems with a precision of approximately **10–30 ms**.

---

## ⚠️ Accuracy & Limitations

| Factor | Limitation |
|--------|------------|
| **Update frequency** | ~60 Hz (one update per screen refresh) |
| **Time resolution** | 3 decimal places → ~1 ms display precision |
| **Camera sync precision** | Limited by frame rate and shutter (~16–33 ms typical) |
| **OCR noise** | Minor OCR errors possible if lighting or resolution is poor |
| **Drift** | No real-time clock sync — best used at recording start, or with regular visual resyncs |

If precise time sync is critical, consider alternatives such as **NTP**, **PTP (IEEE 1588)**, **GPS**, or **hardware trigger lines**.

---

## 🛠️ Technologies Used

- HTML5, CSS3, JavaScript
- `requestAnimationFrame` for high-frequency updates
- OCR-B font (via [FontLibrary](https://fontlibrary.org/en/font/ocr-b))


---

## 📄 License

This project is open source and available under the MIT License.
