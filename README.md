# EdgeEye: Real-time Drowsiness Detection using TinyML & ESP32-CAM

EdgeEye is an end-to-end TinyML project designed to detect driver drowsiness in real time. By using an ESP32-CAM and a custom-trained object detection model built with Edge Impulse, the system identifies eye states (Open/Closed) directly on the edge. This ensures low latency, offline operation, and better data privacy.

---

## 📸 Project Showreel

### Real-world Testing

The system can detect eye states even under challenging lighting conditions, including dark vehicle interiors.

![Real-time detection of closed eyes in a dark environment](/Detecttion in dark environment.png)
**Figure 1:** Real-time detection of closed eyes in a dark environment.

---

## 🚀 Key Features

- **On-Device Inference**  
  Runs an 8-bit quantized neural network locally on the ESP32-CAM.

- **Optimized for Low Power**  
  Efficient execution on resource-constrained hardware using the EON™ Compiler.

- **High Accuracy**  
  Custom dataset trained to reliably distinguish between open and closed eyes.

- **Visual Alert System**  
  Can be extended with buzzers or LEDs for instant driver alerts.

---

## 📊 Model Performance

The model was trained on a custom dataset of eye images. Validation results show strong performance across all classes.

### Validation Metrics

- **Non-background Precision:** 100%  
- **F1 Score:** ~0.84 (INT8 quantized)  
- **Accuracy:** 99.9% (weighted)

**Figure 2:** Confusion matrix and classification report for Open, Closed, and Background classes.

### Training Progress

The training process shows stable convergence with minimal loss, indicating good generalization to new users and environments.

**Figure 3:** Training and validation loss/accuracy curves.

---

## 💻 Hardware & Deployment

EdgeEye runs on the **ESP32-CAM** module. Due to limited memory (520 KB SRAM), the model is optimized using INT8 quantization.

### Deployment Specs

- **Inference Time:** ~2674 ms  
- **Peak RAM Usage:** 363.2 KB  
- **Flash Usage:** 111.4 KB  

**Figure 4:** On-device performance metrics from Edge Impulse deployment.

---

## 🛠️ Installation & Setup

### Prerequisites

- Arduino IDE  
- ESP32 Board Support for Arduino  
- Edge Impulse CLI (optional)

### Steps

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your-username/EdgeEye-TinyML-Drowsiness-Detection.git
````

2. **Include the Library**

   * Go to **Sketch > Include Library > Add .ZIP Library...**
   * Select the `.zip` file exported from Edge Impulse.

3. **Upload the Code**

   * Open the provided `.ino` sketch from the `firmware/` folder.
   * Select **AI Thinker ESP32-CAM** as the board.
   * Connect the ESP32-CAM using an FTDI programmer and click **Upload**.

4. **Monitor Output**

   * Open the Serial Monitor at **115200 baud** to view detection logs.

---

## 📁 Repository Structure

```
/firmware   → Arduino source code and exported TinyML library  
/dataset    → Sample training images (Open/Closed eyes)  
/models     → Quantized .tflite models and metadata  
/docs       → Performance charts and real-world testing images  
```

---

## 📝 License

This project is licensed under the **MIT License**.
See the `LICENSE` file for details.

---

Created with ❤️ by **Saiful Islam**

```
```
