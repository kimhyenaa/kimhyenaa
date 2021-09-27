
2D Digital Compositing
=============
Week2 Gamma / Linear Workflow ...
-------------
## summary
* **Linear Workflow?** : 실제 세상의 빛은 linear로 작용한다. 우리는 광원들의 빛을 곧이곧대로 받아들인다. 즉 실제 세상에서 빛을 볼 때는 input과  output이 동일한 상태이다. 이를 **linear** 라고 한다. 현재 linear workflow는 강력한 성능과 유연성 덕분에 대부분의 스튜디오에서 채택한 산업 표준이 되었다. 

우리가 볼 수 있는 모든 빛을 디지털(모니터)로 구현하기는 어렵다. 

모니터에서는 전압이 input이고, 전압이 빛의 정도로 환산해서 이미지(outpu)t로 표현한다.

하지만 이전에도 말했다시피 컴퓨터가 우리가 보는 대로 빛의 양을 똑같이 구현할 방법이 없기 때문에 최대한 유사하게 표시하도록 개발하였는데 이를 **color space** 라고 한다. 

* **color space** : 모니터에서 압도적인 점유율을 차지하고 있는 컬러스페이스는 sRGB 이다. 
  * 선형 RGB : 카메라 센서에서 얻은 원시 데이터. R, G, B 값은 빛의 양에 정비례. 
  * SRGB: 선형 RGB값에 **감마보정(gamma correction)**이라는 비선형 함수 적용한 컬러스페이스.
 
[참고자료] https://kr.mathworks.com/help/images/understanding-color-spaces-and-color-space-conversion.html
 
 * **ACES** : (Academy Clor Encoding System). 색상을 관리하기 위한 업계의 차세대 표준 기술이다.
  * Q: 어차피 시청자들의 기계사양에 따라 색상이 다 표현되는 것도 아닌데 굳이 ACES로 작업해야 하나요?
   * A: 넵. 화질을 높은 것에서 낮게 줄이는 것은 가능하지만, 낮은 화질에서 높은 화질로 만들 수 없는 거랑 똑같습니다. 회사마다 컬러콕이 다 다른데 그걸 포괄할 수 있는게 ACES 입니다.
   * 풀컬러픽셀: RGBA
   * 투명함을 표현하는 건 ALPHA

 * **Pre - multipl - ication ** : 

 
 
 
 
 
 
### color
색이란 감정이다. 
* 색상, 채도, 명도로 구분된다.

색조란 색상환 내에서 위치.
예술가들에게 색은 전부다. 색의 의미를 내포하여 이야기에 포함 시킨다.
색을 쓰기 위해 색에 대한 과학적인 지식을 아는 것은 중요하다. 색은 빛으로 이루어져 있고, 색은 다양한 파장을 가지고 있으며 우리 안구 망막에 도착하면 신경신호로 변환되어 뇌에서 처리 된다. 

### Bit depth of a color
![k-5581](https://d36nqgmw98q4v5.cloudfront.net/image-handler/ts/20161226021437/ri/750/src/images/Article_Images/ImageForArticle_1151(1).jpg)
  https://www.azooptics.com/Article.aspx?ArticleID=1151
 
1 bits: 2의 1승 / 2 bits: 2의 2승  / 3 bits: 2의 3승
### 알파
RGB에 추가적으로 새로 채널을 만든 것을 말한다. 풀컬러 픽셀은 RGB A라고 한다.
### 컬러스페이스
![K-5584](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/a46df6db-814e-4412-b24e-4cbe376bdddf/K-5584.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210918%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210918T110000Z&X-Amz-Expires=86400&X-Amz-Signature=327c14ee972b2bf792cfe0adcbae10ed5d02bcd21e00c2f33b530e8506a3ece0&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22K-5584.png%22)

Scalar (X):1이냐 0 같은 하나의 수치만으로 완전히 표시되는 값. ex: 1부터 100. 0,1,2,3,,n..

