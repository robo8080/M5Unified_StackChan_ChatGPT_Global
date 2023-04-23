# M5Unified_StackChan_ChatGPT_Global
This is a multilingual M5Unified_StackChan_ChatGPT.

![Image1](images/image1.png)<br><br>

This is a StackChan firmware that corresponds to @mongonta555's [ StackChan M5GoBottom Version Assembly Kit.](https://raspberrypi.mongonta.com/about-products-stackchan-m5gobottom-version/ "Title")<br><br>

---

### Materials and instructions required to make a M5GoBottom version StackChan main body ###
Please refer to this.<br>

* [StackChan M5GoBottom Version Assembly Kit](https://raspberrypi.mongonta.com/about-products-stackchan-m5gobottom-version/ "Title")<br>

### Materials required to build the program ###
* [M5Stack Core2](http://www.m5stack.com/ "Title")<br>
* VSCode<br>
* PlatformIO<br>

Please refer to "platformio.ini" for the libraries used, etc.<br>

---

### Setting the GPIO number to use the servo motor ###
* Please set the GPIO number to use the servo motor around line 42 of M5Unified_StackChan_ChatGPT.ino.


### Getting the ChatGPT API key ###

The method of obtaining a ChatGPT API key is as follows. (For details, please refer to the link at the bottom of this page.)

* Access the[OpenAI website](https://openai.com/ "Title")and create an account. An email address and mobile phone number are required.
* After creating an account, issue an API key. The API key is paid, but there is a free period and credits.<br>

---

### Usage ###
* If you create the following two files at the root of the SD card, you can use it.<br>

1. wifi.txt file: The file name is "wifi.txt", and the contents are as follows.<br>
YOUR_WIFI_SSID<br>
YOUR_WIFI_PASS<br>

2. apikey.txt file: The file name is "apikey.txt", and the contents are as follows.<br>
YOUR_OPENAI_APIKEY<br>

* If the M5Stack was previously connected to Wi-Fi, it will automatically connect to Wi-Fi without the need for an SD card.<br>
In this case, access "http://XXX.XXX.XXX.XXX/apikey" in your browser and set the API key.<br>
(xxxx.xxxx.xxxx.xxxx is the IP address displayed when AI Stack Chan is started.)<br>

* You can specify the voice parameter to change the voice.<br>
Values can be specified in the range of 0 to 4.<br>
For example, specify it as follows.<br><br>
http://192.168.11.20/chat?voice=4&text=hello<br>
<br>

* You can set the role by accessing "http://xxxx.xxxx.xxxx.xxxx/role" in your browser.<br>
(xxxx.xxxx.xxxx.xxxx is the IP address displayed when AI Stack Chan is started.)<br>
If you send it without entering anything in the text area, the previously set role will be deleted.<br><br>
Role information is automatically saved to spiffs.<br>
<br>

* You can get the currently set role by accessing "http://xxxx.xxxx.xxxx.xxxx/role_get" in your browser.<br>

* You can adjust the volume of the speaker.<br><br>
Example:http://xxxx.xxxx.xxxx.xxxx/setting?volume=180<br>
The value of volume is 0 to 255.

* You can change the expression of AI Stack-chan to match the conversation content.<br>
Please enter the following two lines as they are in the role settings.<br><br>
Enclose the emotion type in parentheses, as in (Happy), and attach it to the beginning of the response.<br>
The emotion types include Neutral, Happy, Sleepy, Doubt, Sad, and Angry.<br><br>
When setting up other roles, please include these two lines at the end.<br>
If possible, try using only these two lines.<br>
Increasing the number of roles will make it more likely to fail.<br>
<br>

* Added a soliloquy mode. It speaks randomly at random intervals. It is fun when combined with the emotion expression function. Press button A to turn soliloquy mode on/off. Even in soliloquy mode, you can still talk to it from your smartphone as before.<br>
<br>

* It has a function to save the history of the last five conversations.<br>

* You need to separately prepare a speech recognition program. Pass text (UTF-8) with an HTTP command from the speech recognition program as follows (please pass the text after URL encoding):<br><br>
http://XXX.XXX.XXX.XXX/chat?text=hello<br><br>
Replace XXX.XXX.XXX.XXX with the IP address of the displayed M5Stack at startup.<br><br>
* You can also access it using a browser in the same way as above.<br><br>
![Image2](images/image2.png)<br>

* I use the iPhone's shortcut function for speech recognition. This allows for easy use of speech recognition.<br><br>
![Image3](images/image3.png)<br>

* Touching near the center of the screen of the M5Stack Core2 will stop Stack-chan's head from shaking.<br>

* Pressing button C on the M5Stack Core2 allows you to test speech synthesis.<br>

---

### Setting Language Configuration ###

Please follow these two steps:<br><br>

1. Set up ChatGPT configuration<br><br>
For example, to set the language to English, access "http://xxxx.xxxx.xxxx.xxxx/role" on your browser and set the role as shown below.<br><br>
![Image4](images/image4.png)<br><br>

2. TSet up TTS language configuration<br><br>
For example, to set the language to English, configure as follows on your browser:<br><br> http://xxxx.xxxx.xxxx.xxxx/setting?lang=en-US<br><br>en-US is the language code for English. For other language codes, please refer to the link below.<br><br>

* [Cloud Speech-to-Text Language Support](https://cloud.google.com/speech-to-text/docs/languages?hl=ja/ "Title")<br><br>

---

### Reference links for obtaining ChatGPT API key ###

* [A simple explanation of how to use ChatGPT API](https://qiita.com/mikito/items/b69f38c54b362c20e9e6/ "Title")<br>

### Reference links for ChatGPT character configuration ###

* [Reference links for ChatGPT character configuration](https://note.com/it_navi/n/nf5f702b36a75#8e42f887-fb07-4367-9f3f-ab7f119eb064/ "Title")<br>
<br><br>

