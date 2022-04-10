import requests 
import io
import bz2
import json

url ="https://www.slotwin138.vip/slots}


response = requests.get(
    url.format(time="202002070300"),
    headers={'x-apikey': '<your VT API key>'})

if response.status_code != 200:
  raise Exception(response.content)
else:
  with io.BytesIO(response.content) as f:
    file_feed = [json.loads(line) for line in bz2.decompress(f.read()).splitlines()]
# further processing
