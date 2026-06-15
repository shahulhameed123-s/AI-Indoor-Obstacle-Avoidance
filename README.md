# AI Perception + Control Loop for Indoor Obstacle Avoidance

## 📌 Project Overview

This project implements an **AI-based Perception and Control Loop** for indoor navigation using computer vision. The system processes an indoor video, detects obstacles using the **YOLOv8 object detection model**, and generates navigation commands to safely avoid collisions.

The project is designed to run entirely on **Google Colab** without requiring a robotics simulator such as Gazebo or AirSim.

---

## 🎯 Objectives

- Detect indoor obstacles using Artificial Intelligence.
- Process video frames in real time.
- Generate control decisions based on obstacle position.
- Simulate autonomous navigation for robots or drones.
- Visualize navigation commands on the output video.

---

## 🛠️ Technologies Used

- Python 3
- Google Colab
- OpenCV
- YOLOv8 (Ultralytics)
- NumPy
- Pandas

---

## 📂 Project Structure

```
AI-Indoor-Obstacle-Avoidance/
│
├── input.mp4
├── output.mp4
├── control_log.csv
├── notebook.ipynb
├── requirements.txt
└── README.md
```

---

## ⚙️ Working Principle

### Step 1: Video Input

The system accepts an indoor navigation video (`input.mp4`) as input.

### Step 2: AI Perception

YOLOv8 detects objects such as:

- Person
- Chair
- Table
- Sofa
- Door
- Backpack
- Other indoor obstacles

Bounding boxes are drawn around detected objects.

### Step 3: Obstacle Analysis

The detected obstacle's:

- Position
- Size
- Center location

are calculated to estimate whether it blocks the robot's path.

### Step 4: Control Decision

Based on obstacle location:

| Condition | Action |
|-----------|----------|
| No obstacle ahead | FORWARD |
| Obstacle on left | MOVE RIGHT |
| Obstacle on right | MOVE LEFT |
| Large obstacle in center | STOP |

### Step 5: Output Generation

The processed video is saved as:

```
output.mp4
```

and navigation commands can also be exported as:

```
control_log.csv
```

---

## 🚀 Installation

Install required packages:

```bash
pip install ultralytics opencv-python-headless numpy pandas
```

or

```bash
pip install -r requirements.txt
```

---

## ▶️ Running in Google Colab

1. Open Google Colab.
2. Install dependencies.
3. Upload `input.mp4`.
4. Run all notebook cells.
5. Download:
   - `output.mp4`
   - `control_log.csv`

---

## 📊 Example Navigation Decisions

| Obstacle Position | Robot Command |
|-------------------|--------------|
| Clear path | FORWARD |
| Left side | MOVE RIGHT |
| Right side | MOVE LEFT |
| Center (large) | STOP |

---

## 📸 Output

The generated output video contains:

- Detected obstacles
- Bounding boxes
- AI navigation decisions
- Simulated robot control commands

Example:

```
MOVE LEFT
```

```
MOVE RIGHT
```

```
FORWARD
```

```
STOP
```

displayed directly on the video frames.

---

## 🔮 Future Improvements

- Depth estimation for accurate distance measurement.
- Integration with Gazebo or AirSim simulation.
- ROS2 support for real robots.
- Reinforcement learning for path planning.
- Autonomous drone navigation.
- SLAM-based indoor mapping.

---

## 👨‍💻 Author

**Shahul Hameed**

AI Perception + Control Loop for Indoor Obstacle Avoidance using Computer Vision and YOLOv8.

---

## 📜 License

This project is developed for educational and research purposes.