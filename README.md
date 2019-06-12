# Automatic Colorization

## Introduction

Image colorization is a task to convert a gray-scale image into a color image. Such a task is quite simple for a human since we can understand the scene, separate the image into different regions and recognize the appropriate color of each part intuitively. However, to color an image manually and make it appealing requires much time and work for a human, and only someone who has been trained can do it properly. On the other hand, the task is considerably more difficult for computers, because of the high-level comprehension required for the process. Nevertheless, with the assistant of computers, some or the whole process can become automatic, and even ordinary people can do it properly. 

Current-generation colorization system exists two broad approaches: user-guided semi-automatic colorization and data-driven automatic colorization. Semi-automatic colorization relies on user inputs for colors, so generally, they can achieve impressive results. However, these methods often require intensive user interaction, as each differently colored image region must be explicitly indicated by the user. To address these limitations, some researchers came up with data-driven automatic colorization. These methods colorize a gray-scale image in one of two ways: either by matching it to an exemplary color image in a database and non-parametrically “stealing” colors from that image, or by learning parametric mappings from gray-scale to color from large-scale image data. Although this makes colorization cheap and easy, the results often contain chromatic vanish, color bleeding, and color inconsistency. Furthermore, these methods often have a worse result with complex images with multiple objects, which are much more common-seeing in our life.

### Our work

In light of this, we would like to present a hybrid solution. We propose a deep learning approach for exemplar-based multi-objects local colorization. Our system allows control over the output colorization by simply choosing different references for different instance in the image. To achieve this goal, we will first separate each instance in the image. Then, colorize each instance through the exemplar-based colorization framework respectively, so the task becomes easier and may generate a better result. Besides, while choosing the reference image, our system will automatically choose the one with the top ranking in the database. Finally, we will combine all the color instance, and soften the edge to make the whole image looks more natural

## Result
The following images are presented as follows (left to right) :
Grayscale, Colorful image colorization, Deep exemplar and ours
![](https://i.imgur.com/x2902Ek.png)
![](https://i.imgur.com/vloDWHE.png)
![](https://i.imgur.com/tr86NkH.png)
![](https://i.imgur.com/sSXDXU6.png)
![](https://i.imgur.com/hlNbW7F.png)


In the Figure above, we show some of our experiment results. From left to right are original gray-scale image and results of some colorization system, including Colorful image colorization, Deep exemplar and our system.

To evaluate our system, we ask users to choose the best colorized image among the result of Colorful image colorization, Deep exemplarand ours.

|images|Ours|Colorful image <br>colorization|Deep exemplar|
|----|----|----|----|
|a|75.59|20.07|4.35|
|b|75.25|22.41|2.34|
|c|96.32|2.01|1.67|
|d|20.74|53.85|25.42|
|e|70.9| 21.74|7.36|

From Table 1, it's obvious that about 70 percent of users think our result is better, except for the image d. 

