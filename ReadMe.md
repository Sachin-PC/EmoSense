Instructions to run the code:<br>
Directories Required:<br>
annotations/images<br>
annotations/labels<br>
models<br>
face_path<br>
data<br>

Load all the models required in the models folder. I used the below models:<br>
yolov8n-face.pt for face detection<br>
Face_model.h5 for face emotion classification<br>
FSRCNN_x3.pb(lighter model) model for Super Resolution<br>
EDSR_x3.pb(heavier model) for Super Resolution<br>

For Validation, I have used the YOLO format after labeling using Label-Studio. Add all the validation images into annotations/images and corresponding labels into annotations/labels.<br>
Face_path is created to store temporary face data, which is used to pass for the DeepFace method.<br><br>

Run the following commands before running the code:<br>
pip install opencv-python torch torchvision ultralytics<br>
pip install deepface opencv-python<br>

There are two extract_image_data(image_path,model) methods, you can use either of the one based on the model you are using. Here, one methods is implemented based on Yolo face detection model and the other method is implemented based on Haar Cascade detection model.<br>
Similarly, there are two classify_emotions(faces) methods. You can use either one. One method uses the DeepFace method to classify emotions while the other uses a pre pre-trained model to classify emotions. By default, I'm using the DeepFace method.