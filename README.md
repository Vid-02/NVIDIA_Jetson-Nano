# NVIDIA_Jetson-Nano
Door Camera (Home Security)

# INTRODUCTION
Hello There! This project encompass a door camera face detection prototype that detects the faces of the people arrived at our entrance and shows
number of visits of a particular visitor along with that it also shows - for how many seconds the visitor is standing at the door.

The Images of the visitors detected by the camera are automatically saved in a folder with timestamps. New Folders are created datewise automatically.
Hence it becomes easy to keep track of number of Visitors on a daily basis.

# WORKING OF CODE(Basic Idea of the logic)
-So basically, there are 2 arrays i.e. Known_face_encodings & Knownface_meta_data. Whenever a new face is detected it is stored in known_face_encodings in 
 the form of an array and this is done by using the numpy module. 
-When another face is detected the previous data will be stored in Known_face_metadata plus it will also store the new face data in it.
-To detect the face and store it in the form of an array we have used face_recognition and numpy module. 
-The known_face_metadata is backed up in a .dat file, A known_faces.dat file is created automatically where we dump the face data using pickle.dump 
 function provided by the pickle module.
-When visitors arrive at the door we will load/read the face data stored in known_faces.dat file using pickle.load to match the previous face data with 
 current face data being stored. If the face data matches the number of visit will be incremented by 1 everytime the particular visitor visits our house.
-Everyday new folder is created with date and all the images of the visitors for the particular day are stored in that folder with timestamps. This is done
 through functions provided by opencv module and os module.
-Also to load the video on the output screen with images showing number of visits of a person and the red rectange with number of seconds at door, we have used
 opencv module.
-To exit the code you can press 'q' or Ctrl+C in the terminal

# TO RUN THE CODE
-Refer Requirements.txt file in my repository and complete the initial setup and various installations that are required.
-After completing the above step you can run the main code i.e. doorcam.py in the respective folder(Door_camera_face_detection).

# USE
This project can be used as realtime door camera for home-security purposes. We can keep track of number of visitors at our home datewise with the respective 
timestamps daily.

# FUTURE IMPLEMENTATIONS
-An automatic system generated emails in which the zip file of stored images will be emailed to the owner of the house on a daily basis.
-A user input hardware interface where the visitor can input his/her name and phone number which will be included in the same folder with there respective images.
