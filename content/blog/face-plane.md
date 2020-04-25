---
title: "Face Plane"
date: 2020-04-25T18:06:38+05:30
draft: false
---

My lazy ass was bored due to qurantine, so I saw in [video](https://www.youtube.com/watch?v=nZM9Ko806Bg) about making gift wrapping by flattening a face video. So here is my own version of it

``` python
import cv2
from tqdm import tqdm
WIDTH = 15
cap = cv2.VideoCapture("2.mp4")
outputImage = None
once = True
total = int(cap.get(cv2.CAP_PROP_FRAME_COUNT))
for _ in tqdm(range(total)):
    ret, frame = cap.read()
    frame = cv2.rotate(frame, cv2.ROTATE_90_COUNTERCLOCKWISE)
    w,h,_ = frame.shape
    if once:
        outputImage = frame[:,h//2:(h//2)+WIDTH,:]
        once = False
    else:
        outputImage = cv2.hconcat([outputImage,frame[:,h//2:(h//2)+WIDTH,:]])
cv2.imwrite("output.png",outputImage)
```

And this code gave this output
![output](/images/output.png)

Enjoy the nightmares!
