# Results reducing load time
This file describes the things I did to reduce the loadtime of the static Bootstrap website.

## Begin state
When checking the loadtime of the website before the changes, it took 40 seconds for the page to fully load on regular 2G according to webpagecheck.com ![results of webpagecheck.com](https://i.imgur.com/TUyoOZ4)

![Waterfall view webpagecheck.com](https://i.imgur.com/hbZqieJ)
As you can see on the waterfall view, the first paint is around 12,5 seconds, the first interactive around 21,5 seconds and the page is fully loaded at around 41 seconds.

![Google audits results](https://i.imgur.com/vcgDHns)
Google Audits rates the website 57 out of 100, and says that the first meaningfull paint is around 5.9 seconds.

### Image compression
The first thing I did was compressing the images. Since the images are around 1/5th the size of the full width of the website, they can be resized a lot without losing any quality. Then when i resized the images, I threw them in tinyjpg.com to reduce the file size even more. I managed to reduce the biggest image (expo-vogue.jpg) from 199KB to 44KB, which is a reducement of 77%. The files together were 550KB, and after compressing the files were 187KB, resulting in 66% less KB's for images.

### Critical CSS
The second thing I did was using critical CSS. I have never used this technique before. I found an online critical CSS generator: https://jonassebastianohlsson.com/criticalpathcssgenerator/ . I could just fill in the url to the website, and add the CSS I used on that page. The total amouth of characters at first was around 145.000, but the critical CSS generator managed to reduce it to around 4000 characters, which reduces the file by 97%!

### Moving CSS files to the bottom
Since I had critical CSS, I could move the CSS files to the bottom of the page. This greatly reduced the loadingtime as well.

### Minifying HTML, CSS and JS
The third thing I did was minifying the HTML, CSS and JS. I could explain everything I did, but I'm sure you probably know what minification is, and how it works, so I won't get into detail in this one.

## Results
![Google Audits results](https://i.imgur.com/ucNP86f)
According to Google Audits, the first meaningfull paint is in 1.2 seconds, a difference of 4.7 seconds in comparison with the begin state. It also rates the website 84 out of 100 instead of 57.

![Webpagecheck results](https://i.imgur.com/Ekt3nM9)
According to Webpagecheck.com, the first view is in around 21 seconds, a difference of 19 seconds compared to the begin state.

![Webpagecheck waterfall view](https://i.imgur.com/RitKW5G)
Here you can see the waterfall view of all the requests that the web page needs to render. Comparing this one with the one above, it is almost 50% of the time.

![Videostrip begin en eind webpagecheck.com](https://i.imgur.com/YRrQPdw.png)
Here you can see the timeline of the render progress. The one with optimized files is the above. Every frame is 0.5 second. You can clearly see the difference between the two.