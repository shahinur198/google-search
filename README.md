# google-search

https://developers.google.com/custom-search/v1/overview?csw=1

https://linuxhint.com/google_search_api_python/
https://cse.google.com/cse/setup/basic?cx=012379542552631971030%3Auogymum7a7v

install
```
pip3 install google-api-python-client
```
```
from googleapiclient.discovery import build
my_api_key = "AIzaSyA0rv05E5raWtH3Q0Em4mZheqVuy6ztEfo"
my_cse_id = "012379542552631971030:uogymum7a7v"

def google_search(search_term, api_key, cse_id, **kwargs):
    service = build("customsearch", "v1", developerKey=api_key)
    res = service.cse().list(q=search_term, cx=cse_id, **kwargs).execute()
    return res

result = google_search("Coffee", my_api_key, my_cse_id)
# print(len(result))
for link in result:
	
	if link == "items":
		items=result[link]
		for item in items:
			print("Title: ",item['title'])
			print("Snippet: ",item['snippet'])
			print("")

# <script async src="https://cse.google.com/cse.js?cx=012379542552631971030:wiwci6xcgok"></script>
# <div class="gcse-search"></div>

# <script async src="https://cse.google.com/cse.js?cx=012379542552631971030:uogymum7a7v"></script>
# <div class="gcse-search"></div>
```
# Speech to Text
https://www.geeksforgeeks.org/convert-text-speech-python/

https://pypi.org/project/mpyg321/

install
```
 pip3 install gTTS
 sudo apt-get install mpg321
 pip3 install mpyg321

```
```
# pip3 install gTTS
#  sudo apt-get install mpg321
#  pip3 install mpyg321

# Import the required module for text  
# to speech conversion 
from gtts import gTTS 
  
# This module is imported so that we can  
# play the converted audio 
import os 
  
# The text that you want to convert to audio 
mytext = 'Welcome to geeksforgeeks!'
  
# Language in which you want to convert 
language = 'en'
  
# Passing the text and language to the engine,  
# here we have marked slow=False. Which tells  
# the module that the converted audio should  
# have a high speed 
myobj = gTTS(text=mytext, lang=language, slow=False) 
  
# Saving the converted audio in a mp3 file named 
# welcome  
myobj.save("welcome.mp3") 
  
# Playing the converted file 
os.system("mpg321 welcome.mp3") 

```
