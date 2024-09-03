Remote-Keylogger

Project Goal:
Create a remote keylogger in python, disguise as photo, remote transmit, create a fun saftey key to stop program.


Code


Imports


Begin with imports from python libraries that will make the code possible:

tkinter: for creating a GUI popup on screen
pynput.keyboard: for capturing keystrokes
logging: for creating logfiles
os: for itneracting with the host OS (Windows)
getpass/uuid/socket: get host information
threading: executing procceses in unique threads
subprocess: running system commands

<img width="376" alt="Screenshot 2024-09-03 at 6 00 14 PM" src="https://github.com/user-attachments/assets/5ee34eb9-489d-4e41-b00b-e8432654d3de">


Setup


This section of code configures the SMTP email service to use, along with the temporary file to write all of the logs to. The temporary file created is disguised to blend in with Windows files as "license_win64_details.txt". Using Gmail's SMTP service, I will be able to send emails to remotely extract the information.<img width="820" alt="Screenshot 2024-09-03 at 6 00 37 PM" src="https://github.com/user-attachments/assets/1e10d70e-2d06-4adc-b6ae-fe7183f85e38">

Host Info, Wifi Profiles

These functions will run once at the beginning of execution, and will collect host information about the machine its running on including: hostname, IP, username, saved wifi profiles, MAC address, and username.<img width="822" alt="Screenshot 2024-09-03 at 6 02 35 PM" src="https://github.com/user-attachments/assets/2bd140c4-a01b-439b-aa19-8eb1a60a10f0">

Main Loop

Here are the main functions and main loop of the code. The program will begin listening for keystrokes and writing them to a temp file that will automatically send the data incrementally when the filesize reaches 500 bytes (and on program termination). The program works by creating threads for listening and execution, infinitely logging all keystrokes, writing them to a file, and emailing the file. By default there is a safety key which terminates the program, the right control button. Hitting the exit key will stop the program, delete the temp files, and flash a popup as a fun easter egg.





<img width="749" alt="Screenshot 2024-09-03 at 6 03 30 PM" src="https://github.com/user-attachments/assets/ce6c9571-94bc-454e-90c1-f45f98d5153c">




<img width="821" alt="Screenshot 2024-09-03 at 6 03 57 PM" src="https://github.com/user-attachments/assets/1be86814-bdfe-4e56-9b67-060aec046fca">

Executable compile


The python program can be compiled into a standalone executable through the commandline using PyInstaller. If we save the python file as a ".pyw" extension, the program will run in a mode "without console", meaning that it will run without popping up command prompts or new windows. This will help to stay undetected.



<img width="501" alt="Screenshot 2024-09-03 at 6 05 04 PM" src="https://github.com/user-attachments/assets/542a66b4-69dd-491d-9bb0-957ad9618056">

WinRAR packaging

Using WinRAR we can package the files to be an SFX archive. The program will now be embedded into a photo, and when the photo is opened it will execute the keylogger under the radar. We can disguise the icon and the opening of the file, but cannot get the file type to change from "Application".









<img width="821" alt="Screenshot 2024-09-03 at 6 09 04 PM" src="https://github.com/user-attachments/assets/244df146-29c9-410f-bb67-e46a6aca9a12">







<img width="728" alt="Screenshot 2024-09-03 at 6 09 22 PM" src="https://github.com/user-attachments/assets/4069c173-0350-485f-971a-f9c17d017a40">

Demo

After opening the photo, the executable will run and begin sending emails of the host information and keystrokes. This will loop until the user presses the right ctrl key and terminates the program.



<img width="837" alt="Screenshot 2024-09-03 at 6 17 05 PM" src="https://github.com/user-attachments/assets/cba2967e-f314-4b35-b812-3f4e4ef8f44d">
<img width="776" alt="Screenshot 2024-09-03 at 6 17 26 PM" src="https://github.com/user-attachments/assets/5f7520a0-5bbc-4bdf-be29-d0c82bc124c3">
<img width="828" alt="Screenshot 2024-09-03 at 6 17 51 PM" src="https://github.com/user-attachments/assets/9c3f6f10-2bd1-40de-9c6e-97513500c0a1">















