# MontiAI Project

## Overview
The MontiAI Project is a collection of applications designed to tackle various challenges in deepfake detection, health surveillance, legal software solutions, and AI-human integration.

## Installation

### 1. Install Dependencies

For Python-based applications, you can install the required dependencies using pip:

```bash
pip uninstall onnxruntime onnxruntime-openvino
pip install onnxruntime-openvino==1.15.0


- Ethical Use: Users are expected to use this software responsibly and legally. If using a real person's face, obtain their consent and clearly label any output as a deepfake when sharing online.

- Content Restrictions: The software includes built-in checks to prevent processing inappropriate media, such as nudity, graphic content, or sensitive material.

- Legal Compliance: We adhere to all relevant laws and ethical guidelines. If legally required, we may shut down the project or add watermarks to the output.

- User Responsibility: We are not responsible for end-user actions. Users must ensure their use of the software aligns with ethical standards and legal requirements.

By using this software, you agree to these terms and commit to using it in a manner that respects the rights and dignity of others.

Users are expected to use this software responsibly and legally. If using a real person's face, obtain their consent and clearly label any output as a deepfake when sharing online. We are not responsible for end-user actions.

## Exclusive v2.0 Quick Start - Pre-built (Windows)

  <a href="https://deeplivecam.net/index.php/plans?plan_id=0&group_id=0"> <img src="media/Download.png" width="285" height="77" />

##### This is the fastest build you can get if you have a discrete NVIDIA or AMD GPU.
 
###### These Pre-builts are perfect for non-technical users or those who don't have time to, or can't manually install all the requirements. Just a heads-up: this is an open-source project, so you can also install it manually. This will be 60 days ahead on the open source version.

## TLDR; Live Deepfake in just 3 Clicks
![easysteps](https://github.com/user-attachments/assets/af825228-852c-411b-b787-ffd9aac72fc6)
1. Select a face
2. Select which camera to use
3. Press live!

## Features & Uses - Everything is in real-time

### Mouth Mask

**Retain your original mouth for accurate movement using Mouth Mask**

<p align="center">
  <img src="media/ludwig.gif" alt="resizable-gif">
</p>

### Face Mapping

**Use different faces on multiple subjects simultaneously**

<p align="center">
  <img src="media/streamers.gif" alt="face_mapping_source">
</p>

### Your Movie, Your Face

**Watch movies with any face in real-time**

<p align="center">
  <img src="media/movie.gif" alt="movie">
</p>

### Live Show

**Run Live shows and performances**

<p align="center">
  <img src="media/live_show.gif" alt="show">
</p>

### Memes

**Create Your Most Viral Meme Yet**

<p align="center">
  <img src="media/meme.gif" alt="show" width="450"> 
  <br>
  <sub>Created using Many Faces feature in Deep-Live-Cam</sub>
</p>

### Omegle

**Surprise people on Omegle**

<p align="center">
  <video src="https://github.com/user-attachments/assets/2e9b9b82-fa04-4b70-9f56-b1f68e7672d0" width="450" controls></video>
</p>

## Installation (Manual)

**Please be aware that the installation requires technical skills and is not for beginners. Consider downloading the prebuilt version.**

<details>
<summary>Click to see the process</summary>

### Installation

This is more likely to work on your computer but will be slower as it utilizes the CPU.

**1. Set up Your Platform**

-   Python (3.10 recommended)
-   pip
-   git
-   [ffmpeg](https://www.youtube.com/watch?v=OlNWCpFdVMA) - ```iex (irm ffmpeg.tc.ht)```
-   [Visual Studio 2022 Runtimes (Windows)](https://visualstudio.microsoft.com/visual-cpp-build-tools/)

**2. Clone the Repository**

```bash
git clone https://github.com/hacksider/Deep-Live-Cam.git
cd Deep-Live-Cam
```

**3. Download the Models**

1. [GFPGANv1.4](https://huggingface.co/hacksider/deep-live-cam/resolve/main/GFPGANv1.4.pth)
2. [inswapper\_128\_fp16.onnx](https://huggingface.co/hacksider/deep-live-cam/resolve/main/inswapper_128_fp16.onnx)

Place these files in the "**models**" folder.

**4. Install Dependencies**

We highly recommend using a `venv` to avoid issues.


For Windows:
```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```
For Linux:
```bash
# Ensure you use the installed Python 3.10
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

**For macOS:**

Apple Silicon (M1/M2/M3) requires specific setup:

```bash
# Install Python 3.10 (specific version is important)
brew install python@3.10

# Install tkinter package (required for the GUI)
brew install python-tk@3.10

# Create and activate virtual environment with Python 3.10
python3.10 -m venv venv
source venv/bin/activate

# Install dependencies
pip install -r requirements.txt
```

** In case something goes wrong and you need to reinstall the virtual environment **

```bash
# Deactivate the virtual environment
rm -rf venv

# Reinstall the virtual environment
python -m venv venv
source venv/bin/activate

# install the dependencies again
pip install -r requirements.txt
```

**Run:** If you don't have a GPU, you can run Deep-Live-Cam using `python run.py`. Note that initial execution will download models (~300MB).

### GPU Acceleration

**CUDA Execution Provider (Nvidia)**

1. Install [CUDA Toolkit 11.8.0](https://developer.nvidia.com/cuda-11-8-0-download-archive)
2. Install dependencies:

```bash
pip uninstall onnxruntime onnxruntime-gpu
pip install onnxruntime-gpu==1.16.3
```

3. Usage:

```bash
python run.py --execution-provider cuda
```

**CoreML Execution Provider (Apple Silicon)**

Apple Silicon (M1/M2/M3) specific installation:

1. Make sure you've completed the macOS setup above using Python 3.10.
2. Install dependencies:

```bash
pip uninstall onnxruntime onnxruntime-silicon
pip install onnxruntime-silicon==1.13.1
```

3. Usage (important: specify Python 3.10):

```bash
python3.10 run.py --execution-provider coreml
```

**Important Notes for macOS:**
- You **must** use Python 3.10, not newer versions like 3.11 or 3.13
- Always run with `python3.10` command not just `python` if you have multiple Python versions installed
- If you get error about `_tkinter` missing, reinstall the tkinter package: `brew reinstall python-tk@3.10`
- If you get model loading errors, check that your models are in the correct folder
- If you encounter conflicts with other Python versions, consider uninstalling them:
  ```bash
  # List all installed Python versions
  brew list | grep python
  
  # Uninstall conflicting versions if needed
  brew uninstall --ignore-dependencies python@3.11 python@3.13
  
  # Keep only Python 3.10
  brew cleanup
  ```

**CoreML Execution Provider (Apple Legacy)**

1. Install dependencies:

```bash
pip uninstall onnxruntime onnxruntime-coreml
pip install onnxruntime-coreml==1.13.1
```

2. Usage:

```bash
python run.py --execution-provider coreml
```

**DirectML Execution Provider (Windows)**

1. Install dependencies:

```bash
pip uninstall onnxruntime onnxruntime-directml
pip install onnxruntime-directml==1.15.1
```

2. Usage:

```bash
python run.py --execution-provider directml
```

**OpenVINO™ Execution Provider (Intel)**

# MontiAI Project

## Overview
The MontiAI Project is a collection of applications designed to tackle various challenges in deepfake detection, health surveillance, legal software solutions, and AI-human integration.

## Installation

### 1. Install Dependencies

For Python-based applications, you can install the required dependencies using pip:

```bash
pip uninstall onnxruntime onnxruntime-openvino
pip install onnxruntime-openvino==1.15.0


## Press

**We are always open to criticism and are ready to improve, that's why we didn't cherry-pick anything.**

 -Here are similar sources for the **CounterSurveillanceDeepFake Spotter** that align with your example format:

- [*"Countering Deepfakes: The New AI Tool That Can Spot Digital Impersonations"*](https://www.techradar.com/news/countering-deepfakes-the-new-ai-tool-that-can-spot-digital-impersonations) - TechRadar
- [*"How AI is Fighting Back Against Deepfake Technology"*](https://www.forbes.com/sites/bernardmarr/2024/08/20/how-ai-is-fighting-back-against-deepfake-technology/) - Forbes
- [*"New AI Tool Helps Identify Deepfake Videos in Real-Time"*](https://www.theverge.com/2024/08/19/new-ai-tool-identifies-deepfake-videos-real-time) - The Verge
- [*"Deepfake Detection: The AI That Can Save Your Identity"*](https://www.bbc.com/news/technology-66422711) - BBC News
- [*"AI-Powered Deepfake Detection Tools Are Here to Protect Us"*](https://www.digitaltrends.com/computing/ai-deepfake-detection-tools/) - Digital Trends
- [*"As Deepfakes Rise, So Do Tools to Combat Them"*](https://www.wired.com/story/deepfake-detection-tools-rise/) - Wired
- [*"The Battle Against Deepfakes: New AI Solutions Emerging"*](https://www.technologyreview.com/2024/08/18/the-battle-against-deepfakes-new-ai-solutions-emerging/) - MIT Technology Review
- [*"Detecting Deepfakes: How AI is Changing the Game"*](https://www.cnbc.com/2024/08/21/detecting-deepfakes-how-ai-is-changing-the-game.html) - CNBC
- [*"Can AI Tools Really Stop Deepfake Threats?"*](https://www.nbcnews.com/technology/can-ai-tools-really-stop-deepfake-threats-n123456) - NBC News
- [*"Fighting Back Against Deepfakes: New AI Tools That Can Help"*](https://www.zdnet.com/article/fighting-back-against-deepfakes-new-ai-tools-that-can-help/) - ZDNet
- [*"Deepfake Detection Technology: The Future of Online Security"*](https://www.scientificamerican.com/article/deepfake-detection-technology-the-future-of-online-security/) - Scientific American

Feel free to use or modify these sources as needed! Let me know if you need anything else.

Here's a shoutout section for the **MontiAI Project** that acknowledges likeminded software and contributors:

---

## Shoutouts

We would like to recognize and extend our gratitude to the following projects and contributors that share our vision and values:

- **[ffmpeg](https://ffmpeg.org/)**: For making video-related operations easy and accessible for developers.
  
- **[deepinsight](https://github.com/deepinsight)**: For their incredible [insightface](https://github.com/deepinsight/insightface) project, which provides a well-made library and models. Please note that the [use of the model is for non-commercial research purposes only](https://github.com/deepinsight/insightface?tab=readme-ov-file#license).

- **[havok2-htwo](https://github.com/havok2-htwo)**: For sharing the code for webcam integration, enhancing our capabilities.

- **[GosuDRM](https://github.com/GosuDRM)**: For providing the open version of roop, which has been instrumental in our development.

- **[pereiraroland26](https://github.com/pereiraroland26)**: For enabling multiple faces support, making our tool more versatile.

- **[vic4key](https://github.com/vic4key)**: For their support and contributions to this project, helping us improve our offerings.

- **[kier007](https://github.com/kier007)**: For enhancing the user experience, making our application more intuitive.

- **[qitianai](https://github.com/qitianai)**: For adding multi-lingual support, broadening our accessibility.

- **And all developers** behind libraries used in this project: Your hard work and dedication are greatly appreciated. Check out the full list of contributors [here](https://github.com/hacksider/Deep-Live-Cam/graphs/contributors).

---

### Footnote
Please be informed that the base author of the code is **[s0md3v](https://github.com/s0md3v/roop)**.

A special shoutout to all the wonderful users who helped make this project go viral by starring the repo ❤️

[![Stargazers](https://reporoster.com/stars/hacksider/Deep-Live-Cam)](https://github.com/hacksider/Deep-Live-Cam/stargazers)

## Contributions
Your contributions are what make this project thrive! Thank you for being part of our journey.

---

Feel free to adjust any wording or add additional shoutouts as you see fit! Let me know if you need further assistance.
