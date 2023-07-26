# Attendance-Management-using-face-recognition
## Attendance management during online meets using face recognition(uses HOG method)

This project is a Face Recognition Attendance Management System that allows teachers and students to interact through a graphical user interface (GUI) built using the Tkinter library. The application uses face recognition techniques to allow students to log in to their accounts, and teachers to manage attendance and schedule virtual meetings. The project is implemented in Python and uses the following libraries:

* sqlite3- for handling the database to store student face encodings and attendance records.
* cv2 (OpenCV)- for capturing webcam feed and processing images.
* face_recognition- for face detection and recognition.
* Tkinter- for building the GUI.
* PIL (Python Imaging Library)- for image processing.
* numpy- for handling array operations.
* webbrowser- for opening web links in a browser.
* datetime- for time and date-related operations.

## Features

* Student Login/Signup- Students can choose to log in or sign up using face recognition. If they are not recognized, they can sign up by providing their username and clicking an image of their face for enrollment.
* Teacher Login: Teachers can log in using face recognition. The application allows predefined teacher's face to log in e.g."Khan Sir". To add teachers we have to add the teacher's jpg image into the code and make required changes
* Teacher Functionality: Once logged in a teacher can schedule virtual meeting links for different students. They can also view the attendance records for each student which would consist of the time a particular student was present on the meet and also their attendance status based on the conditions provided in the code(These conditions can be changed from within the code).
* Join Virtual Meeting: Students can see the scheduled virtual meeting links assigned to them by the teacher and join the meeting using the provided link which would open a window monitoring their faces.
* Real-time Attendance Tracking: The application tracks the time spent by each student during the virtual meeting and records it as attendance in the database.
* Fraud detection: Students will be marked absent or would be given warnings if they commit frauds like moving away from screen or using still images/videos instead of being present themselves, this will be reflected on the attendance sheet of teacher.

## Execution

1. User will have to initially create a database- by running the 'createdb.ipynb' file.
2. The user then would have to add or delete the teachers inside the code(M2pro8.ipynb) by:
   * Adding a new jpg image and creating it's encoding
   * Add these encodings to the 'all_enc_t' list and adding the name of the teacher to 'all_img_t' list respective to the position of it's encoding in 'all_enc_t' list.
     ```python
      ks_img = face_recognition.load_image_file("khan_sir.jpg")
      ks_enc = face_recognition.face_encodings(ks_img)[0]
      all_enc_t.append(ks_enc)
      all_img_t.append("Khan Sir")
     ```
3. The user can also change the conditions of being marked absent during meet according to the user's choice.
4. Now the user can run the 'M2pro8.ipynb' file and use the application.

## Database

Database "meetdatabase.db" is automatically created on running the 'createdb.ipynb' file, if it doesn't already exist.

## Drawbacks for future improvement

* Currently the attendance will only be tracked if the meet camera is off by default or blocked as the application uses the system's webcam itself and the webcam can only be used by a single app at once
* The user has to press 'Q' to exit the attendance tracking, it doesn't happen automatically on leaving the meeting

