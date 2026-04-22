# 🚦 Traffic Light Object Detection & Counting

Sistem deteksi dan penghitungan kendaraan (mobil & motor) pada video traffic light menggunakan **YOLOv9** dengan pendekatan **zone-based counting**.

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![YOLOv9](https://img.shields.io/badge/YOLOv9-8.0-red.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

---

## 👥 Team
**Group-01**
- Marcellus Geraldio F.
- Rizki Firdaus Purnama
- Marvin Luckyanto
- Zery Gallanta Sasongko
- Aziz Faadhil

---

## ✨ Features
- ✅ Real-time object detection using YOLOv9
- ✅ Zone-based counting (Left, Center, Right)
- ✅ Object tracking to prevent double-counting
- ✅ Color-coded visualization: 🔵 Car | 🟢 Motorcycle
- ✅ Interactive zone coordinate configuration
- ✅ Multi-method edge detection (Canny, Sobel, Laplacian, Prewitt, Roberts)
- ✅ Auto frame sampling for preprocessing efficiency

---

## 🛠️ Tech Stack
| Component | Library/Tool |
|-----------|-------------|
| Framework | PyTorch, Ultralytics YOLOv9 |
| Computer Vision | OpenCV, scikit-image, Pillow |
| Data & Utils | NumPy, Matplotlib, PyYAML, tqdm |
| Dataset | Roboflow (YOLO format) |
| Platform | Google Colab (T4 GPU) |

---

## 📥 Installation

### 1. Clone Repository
```bash
git clone https://github.com/username/traffic-light-detection.git
cd traffic-light-detection
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Setup Model
YOLOv9 weights will auto-download on first run. For manual setup:
```bash
# Download yolov9c.pt to models/ directory
```

---

## 🚀 Usage

### Google Colab (Recommended)
1. Open `main.ipynb` in Colab
2. Run all cells sequentially
3. Upload input video to `data/` or mount Google Drive
4. Adjust zone coordinates via interactive tool or `data/zones_config.json`
5. Execute detection cell

### Local Execution
```bash
# Run full pipeline
python src/main.py --input data/video.mp4 --output output/result.mp4

# Custom zone config
python src/counting.py --config data/zones_config.json
```

---

##  Project Structure
```
traffic-light-detection/
├── README.md
├── requirements.txt
├── LICENSE
├── main.ipynb
├── src/
│   ├── preprocessing.py
│   ├── detection.py
│   └── counting.py
├── data/
│   ├── dataset.yaml
│   ├── zones_config.json
│   └── video.mp4
├── models/
│   ── yolov9c.pt
├── output/
│   └── result.mp4
── assets/
    ├── sample_input.mp4
    └── demo.gif
```

---

## 📊 Dataset & Zones
- **Source:** Roboflow
- **Format:** YOLO
- **Classes:** `0`-mobil, `1`-motor
- **Zone Layout:**
  - **Zona 1:** Left sidewalk/road edge
  - **Zona 2:** Center median/island
  - **Zona 3:** Right lane
- Coordinates are stored in `data/zones_config.json` and adjustable per camera angle.

---

## 📈 Output
- Video overlay with:
  - Bounding boxes + class labels
  - Persistent tracking IDs
  - Real-time counter per zone
  - FPS indicator
- Format: MP4 (H.264)
- Color coding: 🔵 Car | 🟢 Motorcycle | 🔴 Other

---

## 📄 License
Distributed under the MIT License. See `LICENSE` for details.
