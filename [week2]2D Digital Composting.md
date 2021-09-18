2D Digital Compositing
=============
Week2 What is Color? What is Alpha? Omega?...
-------------
## summary
* 디지털이란? : (Digit + al) : 숫자라는 의미인 'digit'에 al가 추가된 단어
* composition : 사진 찍을 떄 같은 일련의 모든 행위들이 compositing
* 로토스코핑
마스킹 따내는 것이 로토스코핑의 한 종류이다. 마스킹을 딸 때 로토스코핑을 사용하는 이유는 우리가 현장을 촬영할 당시에는 모든 것을 개별적으로 촬영하기 어렵기 때문이다. 촬영 후 마스킹이 필요한 부분이 있다면 그 부분을 마스킹 단다. 오브젝트를 분리한 후 알파채널을 이용한다.
* 트래킹 
2D 트래킹: 오브젝트 X, Y 영상 내의 트래킹을 따라가는 것. ex: 오브제를 손 위에 올려 놓거나 문양을 축하기
3D 트래킹: 카메라의 움직임을 재현한다. ex: 걸어가면서 말할 때 카메라의 흔들림을 재현한다. 

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

VECTOR2: (X,Y)

VECTOR3: (X,Y,Z)

VECTOR4: (X,Y,Z,W) = W는 회전값

(int)eger 

float(f) 0.1, 0.25, 2.14

string : 2D, Digital,

EIZO(현존하는 가장 비싼 모니터. 색 표현 잘하는 회사): 흰색이 얼마나 균일하게 출력되나가 좋은 모니터의 기준이다.

넷플릭스 ACEScg

DCI-P3: 얘도 모니터에서 쓰는.. 

* 우리가 흔히 하는 오해 

컬러스페이스가 커지면 이뻐진다? > 삐.. 그냥 표현할 수 있는 색의 영역이 넓어지는 것 뿐이다.



## 추가공부
### GI(Global Illumination)
![흐엌](https://image2.slideserve.com/4119789/about-global-illumination-l.jpg)
*https://www.slideserve.com/chyna/generating-a-global-illumination-map-on-gpu

예술가들은 색으로 이야기를 표현한다는 이야기를 듣고 애니메이션 회사 '픽사'의 컬러 표현에 관하여 찾아보다 해당 개념을 발견하였다. 
* GI(Global Illumination)란
CG에서의 빛 표현 방식 중 하나인데 광원에서의 직접광, 그리고 다른 재질이나 물체, 벽 등에 반사되는 간접광까지 모두 계산해주는 알고리즘을 말한다. (diffuse + ambient + specular )

GI는 특히 3D애니메이션에서 더 실감나는 느낌을 주기 때문에 중요하다. 
![럴럴](https://www.pluralsight.com/content/dam/pluralsight/blog/dt/wp-uploads/2013/12/Light_Bouncing.jpg)
*https://www.pluralsight.com/blog/film-games/understanding-global-illumination

예를 들어 당신은 이미지를 봤을 때 오른 쪽 벽의 그린 컬러가 구의 오른쪽 측면에 비쳐진다는 사실을 알 수 있다. 이 효과를 간접광이라고 할 수 있다. 그 이유는 초록빛이 직접적으로 떨어진 것이 아니기 때문이다. white light가 초록색 벽에 부딪히고, 부딪힌 그 빛이 구에 떨어진 것이라고 볼 수 있다. GI는 이러한 독특하고 필요한 성질 덕분에 중요한 역할을 한다. 
![광자](https://www.pluralsight.com/content/dam/pluralsight/blog/dt/wp-uploads/2013/12/Global_Illumination.jpg)
이러한 효과를 발휘하기 위해 GI는 mental ray에서 광자 사용을 필요로 한다. 과학적 측면에서 광자는 빛 에너지를 필요로 하는 입자이다. 당
