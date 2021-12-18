
2D Digital Compositing
=============
![누크](https://postfiles.pstatic.net/MjAyMTEwMDRfMTA5/MDAxNjMzMjgwNDA3NzE4.qBvq64OSCJT_qWGXaeQy6pqyUWJQm8bklnDDvZFCB2Ig.ekhL8b5E1gasUksymG2Lf-YsTq_uu6PVq0dUyCclNqwg.PNG.hjkl3805/test_comp.png?type=w773)
누크
![포토샵](https://postfiles.pstatic.net/MjAyMTEwMDRfMTAx/MDAxNjMzMjgwNDA3NjAw.jVPINkuDQUzCSzT063VZb6KX2CNLAXsAKAkEFVu1rsIg.eEjdkhY2vWWDRttVuB6rUTn1kwQQdppPx7l9Narp0Ggg.PNG.hjkl3805/%ED%88%AC%EB%94%94%ED%95%A93%EC%A3%BC%EC%B0%A8%ED%85%8C%EC%8A%A4%ED%8A%B8.png?type=w773)


=============
Week3 Gamma / Linear Workflow ...
-------------
## summary & RESEARCH
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
    * 풀컬러픽셀: RGBA /  투명함을 표현하는 건 ALPHA
[https://www.oscars.org/science-technology/sci-tech-projects/aces]
[https://artnfear.com/entry/ACES-%EC%8B%9C%EC%8A%A4%ED%85%9C%EC%9D%B4%EB%9E%80]


 * **Pre - multipl - ication** : 
 우리가 투명도를 가지고 있는 사진을 작업할 때, 우리는 "premultiplied alpha" 라는 용어를 들을지도 모른다. 이 용어는 수학 단어처럼 들리기도 하는데 이것의 의미는 무엇일까? 
 premultiplied alpha를 알기에 앞서 알파채널은 레이어의 보이는 정도를 조절할 수 있는 마스크를 말한다. 예를 들어 포토샵에서 이미지에 마스크를 씌우고 검정색으로 원하는 부위를 그리기 시작하면 그 부분의 이미지는 보이지 않는다. 
 
   * 소녀와 기린을 합성해보자.
 ![아아악](https://limnu.com/wp-content/uploads/2016/07/premult2-image00.png)
 
 ![으어억](https://limnu.com/wp-content/uploads/2016/07/premult2-image01.png)
 
 소녀에게서 마스크로 소녀만 따내고 기린 사진에서 소녀가 들어갈 부분을 파준다.(검은색은 이미지를 가려주는 역할을 한다.)
 그리고 소녀와 기린 배경을 합성(MULTIPLY)한다. TO MULIPLY(곱하는 것)는 TO MASK(마스크 씌우는 것)을 말한다.
 PRE-MULIPLIED는 즉 PRE-MASKED를 말한다. 
 
  참고자료 [https://limnu.com/premultiplied-alpha-primer-artists/]
 
포토샵은 알파를 스트레이트방식으로 처리한다. 포토샵은 자동적으로 투명도를 조절하기에 알파개념이 없다.
반면에 누크는 프리멀티프라이 개념이 적용돼있어서 누끼를 딸 때 이 개념이 사용된다.


 
 
 
 
 *
 *
 *
 
### VIDEO(Watch color-management-fundamentals-aces-workflows- in nuke)
-------------
## summary
[https://www.youtube.com/watch?v=Hlj5ep-85ys]
* color management 란?
 모두가 어디에서든 각자 스크린에서 동일한 색을 볼 수 있는 것
 
 디지털 카메라가 발견되기 전 네거티브 필름으로 간단히 *촬영* 하고 컴퓨터로 옮겼다. 이때 표준 RGB 형식을 사용했다. 그 다음 로그, LIN, 감마 인코딩(*CG*)한 미디어를 *컴퓨터*로 처리한 후 극장이나 방송국으로 보낸다. => 3개의 색공간을 합침.
 현재는 달라졌다. 여전히 네거티브 필름으로 촬영하지만 몇 가지 변한 점이 있다면 카메라의 개수가 다양하게 늘었다는 점이다. 또한 우리가 그 영상물을 보는 방식도 달라졌다(아이패드나 스마트폰을 이용). => 다양하게 기기가 발명된 만큼 우리가 보는 색의 단계들을 통일할 필요가 커졌다. 

* 다양한 컬러모델
  * CMYK : 색인자 모두 합치면 검정색이 된다. 
  * RYB : 노란색과 파란색을 합치면 초록색이 된다. 
  * HSV(색조,채도,명도)
  * HSL(색조,채도,휘도)
  * RGV : 우리가 가장 많이 쓰는 컬러모델. 모든 색을 합치면 흰색이 된다.
   * 우리가 이 모델을 사용하는 이유: 카메라와 디스플레이가 인간 색각을 참조해서 발명됐기 때문.
  * 인간이 색을 보는 방식
   * 가시 스펙트럼
    인간의 눈 안에 세 가지 감광 세포가 있는데 우리는 이 다양한 빛의 파장을 포착한다. 이 때 이 빛의 파장을 우린 가시 스펙트럼이라고 한다. 
    
   * 화이트밸런스
    인간은 색온도 변화에 익숙하다. 우리 눈은 주변 환경을 인지하기 위해서 들어오는 빛의 온도를 균형있게 유지한다. 이를 화이트밸런스라고 하고 우리는 윌가 감지하는 화이트 포인트를 정의한다. 이 화이트 포인트는 반드시 표준화해서 설정해야 한다. 입시 때 물감이 같은 흰색이라도 제조사마다 다른 색상이 나타난 것처럼 이도 마찬가지이다. CIE는 이를 통일했다. 여러상황에서도 동일한 하얀색을 볼 수 있도록 말이다. 즉 '백색광'을 말한다. RGB스페이스 를 이해할 때 이 개념을 꼭 알아야하며, CIE 표준광 D65라고 하기도 한다. 
    CIE 표준광 D65: 약 6,500k 온도에서 나타나는 표준광: (대략 북서유럽의 평균 한낮정도의 빛. 직사광선과 맑은 하늘로 흩어지는 빛 모두 포함. 주광이라고 부르기도 함. )
