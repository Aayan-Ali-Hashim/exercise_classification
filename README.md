# exercise_classification

# 🏋️ Video Classification with ResNet3D  

This project is about classifying exercise videos like push ups, bench press, deadlifts etc.  
I used **ResNet3D (r3d_18)** as my main model.  

---

## 📌 Why I used ResNet3D?  

At first I tried looking at 2D CNN models like ResNet18 or GoogLeNet, but those models only look at single images.  
That works fine for normal image classification, but in videos the important part is not just *what* is in one frame, but also *how it changes over time*.  

👉 Example:  
- A single frame of a push up looks like a plank.  
- Only when you see the movement across frames, you know it’s a push up.  

ResNet3D is just like ResNet, but the filters are **3D instead of 2D**.  
This means it can learn from both:  
- **Spatial features** → shapes and objects in each frame.  
- **Temporal features** → motion across frames.  

✅ Main reasons I went with ResNet3D:  
- Captures motion patterns, not just still images.  
- Pretrained weights available → faster and more accurate training.  
- ResNet backbone is stable and lighter compared to heavy 3D models.  

---

## ⚙️ Workflow  

1. Extracted frames from each video.  
2. Organized frames into train/val folders by class.  
3. Used PyTorch `VideoResNet (r3d_18)` with pretrained weights.  
4. Fine-tuned it for my dataset of exercises.  
5. Saved the trained model for future use.  

---

## 🚀 How to Run  

### 1. Clone repo  
```bash
git clone https://github.com/yourusername/video-classification.git
cd video-classification
