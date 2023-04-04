# samarafurniture
## Install requirements tools

1. Install Git:
```
sudo apt-get install git
```

## Project set up

1. Clone the repository:
```
git clone hhttps://github.com/grklakg/samarafurniture.git
```

2. Go to project path:
```
cd samarafurniture
```

3. Create a virtualenv and activate it:
```
python3 -m venv env
source env/bin/activate
```

4. Install project in the virtual environment.
```
pip install -e .
```

5. Run:
```
flask --app samarafurniture init-db
flask --app samarafurniture run --debug
```

Open http://127.0.0.1:5000 in a browser.