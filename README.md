# face-and-voice-recognition

voice:

(https://drive.google.com/file/d/1TJ4pTCXHCm7tW_Gx8O451yEShMCMx7Zz/view?usp=sharing)import soundfile as sf
import python_speech_features as mfcc
import numpy as np

# Define function to compute distance between MFCC features
def compute_distance(mfcc1, mfcc2):
    return np.linalg.norm(mfcc1 - mfcc2)

# Load first voice sample (Replace with the path of the first file)
first_voice_path = input("Enter the path of the first voice file: ")
first_audio, rate_first = sf.read(first_voice_path)
num_frames_first = len(first_audio)

# Load second voice sample (Replace with the path of the second file)
second_voice_path = input("Enter the path of the second voice file: ")
second_audio, rate_second = sf.read(second_voice_path)
num_frames_second = len(second_audio)

# Ensure both audio files have the same number of frames
if num_frames_first != num_frames_second:
    # Perform actions to make the number of frames equal
    # For example, trim or pad the longer/shorter audio file
    pass

# Extract MFCC features from both audio files
mfcc_first = mfcc.mfcc(first_audio, rate_first)
mfcc_second = mfcc.mfcc(second_audio, rate_second)

# Compare MFCC features
distance = compute_distance(mfcc_first, mfcc_second)

threshold = 0.5  # Adjust threshold based on testing

if distance < threshold:
    print("Voices match: Confirmed.")
else:
    print("Voices do not match.")





face:
](https://drive.google.com/file/d/1KwvyQKYhLMnQVGjrRAucBFAAUbqBGVXd/view?usp=drivesdk)import cv2 
import cvzone 
from cvzone.FaceMeshModule import FaceMeshDetector 
from cvzone.PlotModule import LivePlot 
import datetime # for time cal
 
cap = cv2.VideoCapture(0) 
detector = FaceMeshDetector(maxFaces=1) 
 
idList = [] 
ratioList = [] 
color = (255, 0, 255) 
flag = 0 
 
while True: 
 
    success, img = cap.read() 
    img, faces = detector.findFaceMesh(img, draw=True) 
 
 
    cv2.imshow("Image", img) 
    cv2.waitKey(25)
