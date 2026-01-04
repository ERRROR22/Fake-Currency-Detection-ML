# Fake-Currency-Detection-ML
💰 Indian Currency Authenticator 💸

Jupyter Notebook project using OpenCV and NumPy for detecting fake Indian banknotes (₹2000 notes). Analyzes security features like green strip count via connected components and Gandhi portrait correlation. Includes real/fake sample images for testing.

✨ Features
🔍 Green Strip Detection: Counts connected components in HSV-filtered ROI; real notes have ~13, fakes ~8.
📊 Gandhi Correlation: Computes cross-correlation (>0.5 threshold) between transparent Gandhi regions on real vs. input.
🖼️ Preprocessing Pipeline: Grayscale, Otsu thresholding, morphological gradient, area opening for noise removal.
📈 Visual Outputs: Plots original, binary, processed images, and results.
✅ Verdict Logic: "Legitimate" if strips match and correlation passes; flags fakes otherwise.
​
🚀 Quick Start
Install dependencies: pip install opencv-python numpy matplotlib jupyter.
Load Currency.ipynb in Jupyter.
Run cells sequentially: Load images → Preprocess → Detect → Output verdict.
Test with real-note.jpg, fake.jpg, Real.jpg.

📁 Project Structure
Currency-Authenticator/
├── Currency.ipynb          # Main notebook (~1.5M chars) with code & visuals
├── real-note.jpg [image:23]  # Sample genuine ₹2000 note
├── fake.jpg    [image:24]  # Sample counterfeit
├── Real.jpg    [image:25]  # Another real sample
└── README.md             # This file! 📖
Key functions: bwareaopen(), corr2_coeff(), connectedComponentsWithStats()

🔬 How It Works
Crops Gandhi/ROI areas, converts to HSV.
Thresholds saturation (>0.3) & value (>0.9) for binary masks.
Applies morphology & counts strips: Real=13±, Fake=8±.
Correlates with real template: >0.5 → genuine.

Sample Output:
- Real: 13 strips, corr=0.5+ → "Legitimate" ✅
- Fake: 8 strips → "Green strip fake" ❌
📊 Sample Results
Note Type	Strips Count	Gandhi Corr	Verdict
Real 
​	13	>0.5	Legitimate 
​
Fake 
​	8	<0.5	Fake 
​
👨‍💻 Developed By
text
   _____ _          _    ____  _                 
  / ____| |__   ___| | _|  _ \(_) ___  ___ _ __  
 | |    | '_ \ / __| |/ / | | | |/ _ \/ _ \ '_ \ 
 | |____| | | | (__|   <| |_| | |  __/  __/ | | |
  \_____|_| |_|\___|_|\_\____/|_|\___|\___|_| |_|
                                                
     🛡️ Forgery Buster by Ritik Sharma 🛡️
     Jammu, India | CSE Undergrad | 2026
     "Spotting Fakes, One Pixel at a Time" 🔍
Custom ASCII shield for the counterfeit crusader! ⚔️

🔧 Customization
Adjust satThresh=0.3, valThresh=0.9, corr=0.5 for other denominations.
Add ₹500/100 templates in corr2().
Deploy as Streamlit app for webcam scanning.

📄 License
MIT - Fork, enhance, deploy freely!

Scan Smart, Stay Secure! 🏦🚀 
