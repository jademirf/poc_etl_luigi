# Simple LUIGI test

## (optional) create a new virtual environment
```bash
python3 -m venv luigi-venv
```
## (optional) activate the newly created venv
```bash
. luigi-venv/bin/activate
```
## install
```bash
pip install -r requirements.txt
``` 
## enable acess to port 8082
```bash
sudo ufw allow 8082/tcp
``` 
## run the scheduler
```bash
sudo sh -c ". luigi-venv/bin/activate ;luigid --background --port 8082"
``` 
## get top books list
```bash
python -m luigi --module word-frequency GetTopBooks
``` 
## Download a book by id
```bash
python -m luigi --module word-frequency DownloadBooks --FileID 2
``` 
## Count words from a file by id
```bash
python -m luigi --module word-frequency CountWords --FileID 2
``` 
## Generate top words by word-frequency
```bash
python -m luigi --module word-frequency TopWords --GlobalParams-NumberBooks 15 --GlobalParams-NumberTopWords 750
``` 
