You might also find that for a same photo, QuMagie App in phone is showing a much poorer quality when compared with PC QuMaige webpage or QPhoto App. They all use the thubnail to display, but in PC QuMagie and QPhoto App it's using the large size thumbnail while in QuMagie app it's using middle size. It's controlled by a size parameter when app sends the http(s) request to QNAP NAS.

QNAP customzer support might suggest you to switch to view in "the original size" to solve this, but it's just a workaround. It imposes much pressure to your NAS, phone and the network, especially if the original size is very large. Also app is buggy and very slow to show the original one.

So I modified the smali code and added 3 lines to fetch the large thumbnail if the original request is to get the middle one, much like below code:
```
        if (size == "1")
        {
            size = "0";
        }
```

Feed free to download the updated app and use it. 

It would be good if you can complain this issue to QNAP too, so they understand it's a common issue and hope they will take action to fix it in the official build quickly.