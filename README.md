# IBM-Watson-to-convert-speech-text-text-to-speech
In this project we will use the help of IBM watson services to convert speech to text & vise versa.

## 1. Speech to Text (STT)
start by visiting the link (https://cloud.ibm.com/catalog?category=ai#services), check the option (AI/Machine learning) and then you will find Speech to Text service, choose the language and the pricing plan then click create to start:

![image](https://user-images.githubusercontent.com/85634099/125859766-16df6aa5-0bee-4c00-9098-55703e9c56e3.png)
![image](https://user-images.githubusercontent.com/85634099/125860176-c2e941d5-8b2e-4939-9330-d8fe23bf2d4a.png)


## 2. Get your Credentials
Next, click on service credentials and get your API Key and your region and save them for later use:

![image](https://user-images.githubusercontent.com/85634099/125860603-84279a8b-ce8d-4a28-95fd-d58683ebe3cf.png)

## 3. Clone IBM Watson Streaming STT Project
For this step i used Pycharm IDE and created a new project, i used its terminal to run this following code which clones the github project files into my pycharm project:
```
git clone https://github.com/IBM/watson-streaming-stt
```
![image](https://user-images.githubusercontent.com/85634099/125861325-5beea907-dcbe-4cb7-8571-c6c033ff0fa2.png)

## 4. Install Dependencies
Running this project requires specific packages written in (requirements.txt) file so use the following line of code to download then from the requirements file:
```
pip install -r requirements.txt
```

## 5. Update Region & API key 
In your cloned project, go to line number 2 in (speech.cfg) file, erase the old API and replace it with your own (the ones you got from step 2)

![image](https://user-images.githubusercontent.com/85634099/125862628-0d859e9e-8a19-4d1d-9fff-7b3aec9f87aa.png)

Next, go to line number 175 in (transcribe.py) file and erase the old region and replace it with your own (the ones you got from step 2)

![image](https://user-images.githubusercontent.com/85634099/125862845-719b750a-32c1-41a3-b852-d96b3bb2db29.png)

## 6. Speech To Text File
In the following lines of code I started by creating a text file named (STT.txt) followed by the function 'write' which writes the text content into the text file, and finally closing the file, and the text file will be found with the rest of the project files after running the code :
```
fo = open('STT.txt', 'w')
fo.write(transcript)
fo.close()
```
![image](https://user-images.githubusercontent.com/85634099/125865454-e62a38d1-8f9a-46ca-a622-3a2fe4b2866c.png)

## 7. Text To Speeh (TTS)
In the step we want to convert our text into an audio using the following code lines, I started by creating passing the text into gTTS function which will convert the text into the audio file and then save it under the name (TTS.mp3) and the mp3 file will be found with the rest of the project files after running the code :
```
output = gTTS(text=transcript, lang='en', slow=False)
output.save("TTS.mp3")
```
![image](https://user-images.githubusercontent.com/85634099/125865933-89c3db98-5097-4660-9724-79d48b418b01.png)


## 8. Run The Code
Now that everything is ready we will run the code using the following command where we use -t to specify how long we want to record (ex: 20 sec)
Note: mke sure you are in the correct directory otherwise use (cd ./watson-streaming-stt) 
```
python transcribe.py -t 20
```
## SPEECH
As i run the program i started speaking and the program started showing my speech in the terminal, and it showed a correct result as i was saying (this is my first time trying my project I hope this goes well this should turn speech to text and vice versa )

https://user-images.githubusercontent.com/85634099/125865962-8245d454-b3e0-47ed-b25a-21bc19832a8e.mp4

## MP3 FILE
After running the program it converted the output text automatically into mp3 file 

https://user-images.githubusercontent.com/85634099/125866007-4d8cfcd4-e492-43c6-a25b-78e1f07f401d.mp4

## TEXT FILE
After running the program it converted my final speech automatically into a text file 

![image](https://user-images.githubusercontent.com/85634099/125866072-35522932-c01b-4e5e-8664-677455f2c635.png)

