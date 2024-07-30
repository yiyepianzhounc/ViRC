# ViRC: Visual Reasoning CAPTCHA Dataset 
## Dataset Details

ViRC: Visual Reasoning CAPTCHA dataset including [VTT](https://cloud.tencent.com/product/captcha), [Geetest](https://www.geetest.com/show), [NetEase](https://dun.163.com/trial/space-inference), Xiaodun, [Shumei](https://www.ishumei.com/trial/captcha.html) and [Dingxiang](https://www.dingxiang-inc.com/business/captcha).

Download: https://drive.google.com/drive/folders/1UA4V6HQfSS74puq8EuFU9ygKV3_i62S9?usp=drive_link (need request)

Some examples are shown in below table. More can be found in the [images](./images) folder and [Examples.md](./images/Examples.md).

|  CAPTCHA  |  Size  |                           Example                            |
| :-------: | :----: | :----------------------------------------------------------: |
|    VTT    | 10,000 | <img src="D:\LearnigForCyberSecurity\pictures\vtt_000001.jpg" style="width:150pt;"><br>请点击正对着你的字母<br>(Please click on the letter that is facing you) |
|  Geetest  | 10,000 | <img src=".\images\geetest_000001.jpg" style="width:150pt;"><br>请点击与黄色物体有相同大小的红色正方体。<br>(Please click on the same size red cube with the same size as the yellow object. ) |
|  NetEase  | 10,000 | <img src=".\images\netease_000001.jpg" style="width:150pt;"><br>请点击灰色大写L<br>(Please click on the gray capital L) |
|  Xiaodun  | 10,000 | <img src=".\images\xiaodun_000001.png" style="width:150pt;"><br>请点击蓝色的圆锥体<br>(Please click the blue cone) |
|  Shumei   | 3,000  | <img src=".\images\shumei_000001.jpg" style="width:150pt;"><br>点击图中最小的绿色长方体<br>(Click the smallest green custody in the figure) |
| Dingxiang | 10,000 | <img src=".\images\dingxiang_000001.jpg" style="width:150pt;"><br>请点击平行四边形左侧的字母<br>(Please click on the alphabet on the left side of the parallel quadrite) |

The data in each type of CAPTCHA is put in this way:

* train (CAPTCHA images for training)
* val (CAPTCHA images for validating)
* test (CAPTCHA images for testing)
* detect_train.json (CAPTCHA object detect results for training)
* detect_val.json (CAPTCHA object detect results for validating)
* detect_test.json (CAPTCHA object detect results for testing)
* labels.json (CAPTCHA object name2id map)
* ques_train.json (CAPTCHA questions for training)
* ques_val.json (CAPTCHA questions for validating)
* ques_test.json (CAPTCHA questions for testing)

## Data Collection and Annotaions

To prevent large-scale malicious collection of CAPTCHAs, visual reasoning CAPTCHA service providers typically employ strict anti-crawling measures, which impose certain limitations on CAPTCHA data collection. We implemented simulated browser dynamic clicking to circumvent these anti-crawling mechanisms and collect sufficient visual reasoning CAPTCHAs using Selenium from Python. 

For the data annotation task, we invited professional annotators to label the answers for the visual reasoning CAPTCHAs. We developed corresponing online annotation website to facilitate the annotation process. This website displays one visual reasoning CAPTCHA image and its corresponding question on each page. The professional annotators click on the answer region within the CAPTCHA using a mouse, and the backend of the website records the mouse click coordinates relative to the entire image and stores them in a database. Finally, we exported the data and used scripts to determine which object in the CAPTCHA the coordinates belonged to. The object is then regarded as the answer for that particular CAPTCHA, thereby completing the annotation process. In total, we annotated over 50,000 CAPTCHAs from six most popular CAPTCHA service provider platforms.

## Contact

Feel free to email me for dataset request and questions (xherlocker1214@gmail.com)

## BibTeX

If you want to cite our Dataset, you can use our [paper]():

~~~latex
B. Xu, H. Wang, "VRC-GraphNet: A Graph Neural Network-based Reasoning Framework for Attacking Visual Reasoning Captchas". Proceeding of 19th EAI International Conference on Security and Privacy in Communication Networks (SecureComm 2023), Hong Kong, China, October 19-21, 2023. (To be published soon)
~~~

