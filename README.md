EdgeEye: Real-time Drowsiness Detection using TinyML & ESP32-CAM

EdgeEye is an end-to-end TinyML project designed to detect driver drowsiness in real-time. By utilizing an ESP32-CAM and a custom-trained object detection model via Edge Impulse, this system identifies eye states (Open/Closed) directly on the edge, ensuring low latency and data privacy.

📸 Project Showreel

Real-world Testing

The system is capable of detecting eye states even in challenging lighting conditions, such as dark vehicle interiors.

Figure 1: Real-time detection of closed eyes in a dark environment.

🚀 Key Features

On-Device Inference: Performs 8-bit quantized neural network inference locally on the ESP32-CAM.

Optimized for Low Power: Efficiently runs on resource-constrained hardware using the EON™ Compiler.

High Accuracy: Specialized dataset trained to distinguish between open and closed eyes with high precision.

Visual Alert System: Can be integrated with buzzers or LEDs for immediate driver notification.

📊 Model Performance

The model was trained using a custom dataset of eye images. Based on the validation results, the model achieves excellent performance in distinguishing classes.

Validation Metrics

Non-background Precision: 100%

F1 Score: ~0.84 (int8 quantized)

Accuracy: 99.9% (weighted)

Figure 2: Confusion matrix and classification report showing performance across Open, Closed, and Background classes.

Training Progress

The model shows stable convergence with minimal loss, ensuring robust generalization to new faces and environments.

Figure 3: Training and Validation loss/accuracy curves.

💻 Hardware & Deployment

The project leverages the ESP32-CAM module. Due to its limited RAM (520KB SRAM), the model has been optimized using INT8 Quantization.

Deployment Specs

Inference Time: ~2674 ms

Peak RAM Usage: 363.2 KB

Flash Usage: 111.4 KB

Figure 4: On-device performance metrics from Edge Impulse deployment.

🛠️ Installation & Setup

Prerequisites

Arduino IDE

ESP32 Board Support for Arduino

Edge Impulse CLI (Optional)

Steps

Clone the Repository:

git clone [https://github.com/your-username/EdgeEye-TinyML-Drowsiness-Detection.git](https://github.com/your-username/EdgeEye-TinyML-Drowsiness-Detection.git)


Include the Library:

Go to Sketch > Include Library > Add .ZIP Library... and select the .zip file from your Edge Impulse export.

Upload the Code:

Open the provided .ino sketch in the firmware/ folder.

Select AI Thinker ESP32-CAM as your board.

Connect your ESP32-CAM via an FTDI programmer and click Upload.

Monitor:

Open the Serial Monitor at 115200 baud rate to see detection logs.

📁 Repository Structure

/firmware: Arduino source code and exported TinyML library.

/dataset: Sample images used for training (Open/Closed eyes).

/models: Quantized .tflite files and model metadata.

/docs: High-resolution performance charts and testing images.

📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

Created with ❤️ by Saiful Islam
