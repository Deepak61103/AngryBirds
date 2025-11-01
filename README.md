# 🖱️ Virtual Mouse Controller (Hand Tracking)

A hands-free virtual mouse that allows users to control the cursor and perform drag-and-drop actions using simple hand gestures captured via a webcam.



---

## ✨ Features

* **Cursor Control:** Mouse movement is mapped to the position of the **Index Finger**.
* **Click/Drag Action:** Performs a virtual **mouse down** (click/start drag) when the **Thumb and Index Finger** are pinched close.
* **Mouse Up Action:** Performs a virtual **mouse up** (release click/end drag) when the **Thumb and Index Finger** are separated.
* Built using OpenCV for real-time video processing.

---

## 🛠️ Requirements

### Prerequisites

* A standard webcam (built-in or external).
* Python 3.x installed.

### Installation

1.  **Install the required Python packages** using the `requirements.txt` file:
    ```bash
    pip install -r requirements.txt
    ```

---

## 🚀 How to Run

1.  Make sure your webcam is available and not in use by other applications.
2.  Run the main script:
    ```bash
    python virtual_mouse.py
    ```

---

## 🖐️ Usage and Controls

The application opens a window displaying your webcam feed with tracking visualization.

| Action | Gesture | Condition in Code |
| :--- | :--- | :--- |
| **Cursor Movement** | Move your **Index Finger** | `pyautogui.moveTo(cx * 4, cy * 4)` |
| **Click / Drag** | Pinch the **Thumb and Index Finger** together | `length < 50` $\rightarrow$ `pyautogui.mouseDown()` |
| **Release / Stop Drag** | Separate the **Thumb and Index Finger** | `length > 50` $\rightarrow$ `pyautogui.mouseUp()` |

> **Note:** The mouse is controlled within a specific green rectangular region defined in the code: `(80, 105)` to `(580, 375)`. Keep your hand in this area for tracking.

---

## 💡 Technologies Used

* **Python**
* **OpenCV**
* **CVZone** (for simplified Hand Tracking)
* **PyAutoGUI** (for OS mouse control)
