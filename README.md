# Webhooks-Gmail
How to create webhooks on gmail
## Prerequisites
- Install python 3
```
sudo apt install python3-pip
```
- Install python library
```
sudo pip install httplib2
```

## Fetch Webhook link
- go to Google Space
- Apps and Integrations
- Manage webhooks

## Put in pyton script
```
from json import dumps

from httplib2 import Http

WEBHOOK_URL = "https://chat.googleapis.com/v1/spaces/AAAAjfuqaCU/messages?key=AIzaSyDdI0hCZtE6vySjMm-WEfRq3CPzqKqqsHI&token=fNbsi28ViLti6rixYVSwPB9taZgQpJIfV5-HRnE2CSk"

def main():
    """Google Chat incoming webhook quickstart."""
    url = WEBHOOK_URL
    app_message = {
        'text': 'Hello from a Python script!'}
    message_headers = {'Content-Type': 'application/json; charset=UTF-8'}
    http_obj = Http()
    response = http_obj.request(
        uri=url,
        method='POST',
        headers=message_headers,
        body=dumps(app_message),
    )
    print(response)


if __name__ == '__main__':
    main()

```
