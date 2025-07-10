# Player-Re-Identification-in-Sports-Footage

🎯 Player Re-Identification Assignment – Liat AI

👤 Prepared By
Dibyajyoti Dutta
Assignment for: AI Intern Position at Liat AI


✅ Task Chosen: Option 2 – Re-Identification in a Single Feed

Objective: Given a 15-second video (`15sec_input_720p.mp4`), the goal is to detect players, assign IDs, and ensure players who leave and re-enter the frame retain the same ID.



📁 Folder Contents

Liat_AI_Player_ReID_Assignment/
│
├── output.avi                  # Final video with bounding boxes and player IDs
├── player_reid_colab.ipynb     # Colab notebook with complete working code
├── README.md                   # This file
└── best.pt                     # Provided YOLOv11 model (optional to include)


⚙️ How to Run the Notebook (on Google Colab)

1. Install Dependencies

python
!pip install ultralytics


2. Upload Files

Use:
python
from google.colab import files
files.upload()

Upload these files when prompted:
- `best.pt` (provided detection model)
- `15sec_input_720p.mp4` (input video)

3. Run the Notebook Cells

- Loads YOLOv11 model and video
- Runs detection + re-identification
- Tracks players using bounding box IoU matching
- Assigns consistent player IDs
- Saves final video as `output.avi`

4. Download Output
python
from google.colab import files
files.download("output.avi")




📽️ Model Used

-Model: YOLOv11 (`best.pt`) - pre-trained for player and ball detection
- Framework: Ultralytics + OpenCV

---

🧠 Methodology

- Used YOLOv11 to detect players (class 0)
- Tracked players using Intersection-over-Union (IoU) between bounding boxes
- If a player's IoU > threshold (0.3), assigned same ID
- New players get new IDs and color labels
- Maintained player state across frames with a simple memory list
- Used OpenCV to annotate frames with bounding boxes + IDs
- Saved annotated video as `output.avi`

---

🧰 Dependencies

- Python 3.x
- OpenCV (`cv2`)
- Ultralytics YOLO (`pip install ultralytics`)
- Google Colab (preferred for execution)

---

## 🙌 Thank You!
I really enjoyed working on this assignment. Looking forward to the opportunity!

— Dibyajyoti Dutta
