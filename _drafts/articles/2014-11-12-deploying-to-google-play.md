---
layout: article
title: "Deploying to Google Play"
modified:
categories: articles
excerpt:
tags: []
image:
  feature:
  teaser:
  thumb:
date: 2014-11-12T22:20:10+01:00
---

TODO:

* Uploading to Google Play (http://www.steverichey.com/dev/openfl-android-tips-and-tricks/)
* Grabbing screenshots

{% highlight bash %}
i = 1;
while [ 1 ];
do screencapture -t png -x ~/PATH/$i.png; 
    let i++; 
    sleep INTERVAL;
done
{% endhighlight %}

Setting `INTERVAL` to 3 seconds and `PATH` to `Desktop/` the script becomes this one-liner:

{% highlight bash %}
i = 1; while [ 1 ]; do screencapture -t png -x ~/Desktop/$i.png; let i++; sleep 3; done
{% endhighlight %}

Pretty nifty!

* Recording video

# Recording
{% highlight bash %}
echo -e "Filename for recording: \c "
read filename
echo "Recording screen..."
adb shell screenrecord --bit-rate 6000000 /sdcard/${filename}.mp4
{% endhighlight %}

# Copy from device
```
echo -e "Filename for recording: \c "
read filename
echo "Saving to ${filename}.mp4"
adb pull /sdcard/${filename}.mp4 ${filename}.mp4
echo "Done"
```


# Building a release version
## Signing
## Verifying
jarsigner -verify -verbose -certs export/android/bin/bin/GameOfGames-release.apk
