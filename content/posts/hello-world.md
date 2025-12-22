+++
title = "Hello World"
date = 2025-12-22
draft = false
tags = ['placeholder']
+++

This is my first post.

```python
import os
import requests
from .app_paths import paths

def transcribe(path=paths['audio_recording']):
    
    key = os.environ['LEMON_AI_KEY']

    url = "https://api.lemonfox.ai/v1/audio/transcriptions"

    headers = {
      "Authorization": f"Bearer {key}"
    }

    data = {
      "language": "english",
      "response_format": "text"
    }

    with open(path, "rb") as f:
        files = {
            "file": ("mic.wav", f, "audio/wav")
        }

        response = requests.post(url, headers=headers, data=data, files=files)

    print(response.text)


if __name__ == '__main__':
    transcribe()

```
