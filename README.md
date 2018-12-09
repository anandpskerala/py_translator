<p align="center"><img src="https://github.com/markolofsen/py_translator//blob/master/.banners/banner_en.png?raw=1" /></p><br />
<p align="center"><b>Languages:</b><br /><b>English</b> | <a href="https://github.com/markolofsen/py_translator/blob/master/README_es.md">Spanish</a> | <a href="https://github.com/markolofsen/py_translator/blob/master/README_ru.md">Russian</a></p><br />
<br />
---<br />
<br />
# Enriched library for translating text from the Google Translate API.<br />
<br />
Version = 2.0.1<br />
Library name = py_translator<br />
Title = Google Translate API (Python 3)<br />
Keywords = Google, Cloude, API<br />
<br />
### Hot to install<br />
<br />
```sh<br />
pip3 install py_translator==2.0.1<br />
```<br />
                    <br />
<br />
## How to use<br />
<br />
1. Enable the [Cloud Translation API](https://cloud.google.com/translate/docs/quickstart?csw=1)<br />
2. Download a private key as JSON-file.<br />
3. Specify path to the file in variable "creds_path"<br />
<br />
### Sample 1<br />
```python<br />
import os<br />
from py_translator import Translator, TextUtils<br />
creds_path = os.path.join(os.path.dirname(__file__), 'creds.json')<br />
<br />
s = Translate(creds_path=creds_path).translate(text="Hello new world!", target_language='cn')<br />
print(s.text)<br />
```<br />
<br />
### Sample 2<br />
```python<br />
import os<br />
from py_translator import Translator, TextUtils<br />
creds_path = os.path.join(os.path.dirname(__file__), 'creds.json')<br />
<br />
html_str = '<p>Russian word</p>'<br />
s = Translator(creds_path=creds_path).html(text=html_str, target_language='ru')<br />
print(s.text)<br />
```<br />
<br />
### Sample 2<br />
```python<br />
from py_translator import TextUtils<br />
s = TextUtils().detect('Detect my language please...')<br />
print(s)<br />
```<br />
<br />
<br />
<br />
### Using any variables without translation? — Easy!<br />
```python<br />
import os<br />
from py_translator import Translator, TextUtils<br />
creds_path = os.path.join(os.path.dirname(__file__), 'creds.json')<br />
<br />
text = "Hi, this is [[name]], waiting for $ [[number]] from you!"<br />
s = Translator(creds_path=creds_path).translate(text="Hello new world!", target_language='ru')<br />
print(s.text)<br />
```<br />
<br />
Result: «Привет, это [[name]], жду от тебя $ [[number]]!»<br />
<br />
<br />
---<br />
<br />