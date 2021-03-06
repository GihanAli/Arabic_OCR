# Arabic_OCR
![alt text](https://github.com/maidaly/Arabic_OCR/blob/main/demo.png)
<br>
This repo contains Arabic OCR App. The APP can be used to extract the Arabic text from the images. This was built based on the [EasyOCR](https://github.com/JaidedAI/EasyOCR) library. EsayOCR built  detection/recognition model to detect and recognize the characters and words. For detection part they used the pretrained model for [CRAFT](https://arxiv.org/abs/1904.01941) algorithm. For recognition they built a [CRNN](https://arxiv.org/abs/1507.05717) model. For our case, we used the two pretrained model for Arabic language. To create the wep app, we used the [Streamlit](https://www.streamlit.io/) library.

## Installation
There are many option to run or install the app we will show three of them:
### 1. Run via Colab
you can run colab notebook and go through the ngrok link to run the app.<br>
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1JMyzh_fnhTtZnN_hfzMmm3Pr3AON89SK?usp=sharing),<br>
### 2. Install via conda
In this step we assume that conda is preinstalled on the machine. If conda is not installed you can follow the steps on the that [link](https://docs.conda.io/projects/conda/en/latest/user-guide/install/)<br>
1. At first we need to clone the repo to the local machine.
```bash
git clone https://github.com/maidaly/Arabic_OCR.git
```
2. Create a new conda enviroment to run the app inside it.
```bash
conda create --name arabic_ocr
```
```
conda activate arabic_ocr
```
3. Install the required python packages
```bash
pip install -r requirements.txt
```
4. Run the app
```bash
streamlit run app.py
```
The command need to run from the folder that contains the repo files. It will generate two links you can go throgh [http://localhost:8501](http://localhost:8501) to run the app on the local host.
### 3. Run via docker container
In this step we assume that Docker is running on your machine.
1. Clone the repo silmilar to conda installtion.
2. Convert directory to the repo location.
2. Build a docker image.
```bash
docker image build -t arabic_ocr:app 
```
4. Run the image
```bash
docker run -p 8501:8501 arabic_ocr:app 
```
After running the image we can go to [http://localhost:8501](http://localhost:8501) to run the app.

## Note
- The first time running the app it may take time (some moments) to download the pretrained models that used. The time depends on the network speed. Then the pretrained models will be saved to used later.
- The app is running faster with the machine that contains Nvidia gpus. If the gpu is not availble the app will run but with slow performance. 
