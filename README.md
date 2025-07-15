
# 🚁 Small Object Detection in Aerial Videos using YOLOv11

**Author:**Premnath MV
**Reg No:** URK23RA4014



---

## 📌 Project Description

This project aims to detect **small objects in aerial drone videos** using the **YOLOv11** deep learning model. We used the **VisDrone** dataset, which contains images and annotations from drone footage, converted into YOLO format. The goal is to achieve better detection accuracy for small-scale objects such as pedestrians, bicycles, and vehicles.

---

## 🛠️ Tools and Technologies Used

- Python
- Ultralytics YOLOv8
- PyTorch
- OpenCV
- VisDrone Dataset
- Terminal


---

## 🔧 Setup Instructions

### 1️⃣ Clone YOLOv11 Repository

```bash
git clone https://github.com/ultralytics/ultralytics
cd ultralytics
pip install -r requirements.txt
```

### 2️⃣ 📂 Dataset Structure

This project uses the **VisDrone** dataset, converted into YOLO format. Ensure your folders are organized as shown below:

```
VisDrone-YOLO/
├── images/
│   ├── train/
│   └── val/
├── labels/
│   ├── train/
│   └── val/
└── data.yaml
```

### 3️⃣ 📄 Create data.yaml

Example `data.yaml` file:

```yaml
path: ../VisDrone-YOLO
train: images/train
val: images/val

nc: 10
names: ['pedestrian', 'person', 'bicycle', 'car', 'van', 'truck', 'tricycle', 'awning-tricycle', 'bus', 'motor']
```

### 4️⃣ 🏋️‍♂️ Train the YOLOv8 Model

```bash
yolo detect train data=data.yaml model=yolov11n.pt epochs=100 imgsz=640
```

### 5️⃣ 📊 Results After Training

After training, results are saved inside:

```
runs/detect/train/
├── weights/
│   ├── best.pt
│   └── last.pt
├── results.png
├── confusion_matrix.png
└── F1_curve.png
```

### 6️⃣ 📸 Inference Example

```bash
yolo detect predict model=runs/detect/train/weights/best.pt source=your_video_or_image_path
```

---

## 👨‍🏫 Mentorship

This project was completed under the guidance of **Dr. Vinodh Edwards**, at **Karunya Innovation and Design Studio (KIDS)**.

---

## 📚 References

- [Ultralytics YOLOv8 Docs](https://docs.ultralytics.com)
- [VisDrone Dataset](https://github.com/VisDrone/VisDrone-Dataset)
