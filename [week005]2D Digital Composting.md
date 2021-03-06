[week5]2D Digital Composting.md
=============
Chroma key
-------------
## summary
크로마키를 할 때 초록색을 많이 사용하는 이유는 사람과 가장 먼색이기 때문이다. 크로마키를 하는 이유는 알파를 좀 더 쉽게 추출하기 위해서이다. 크로마키 작업이 로토스코핑보다 먼저 나왔다. 필름을 쓸 때부터 나왔던 기법이다. 예전에는 필름과 필름을 겹쳐서 촬영 못함. 우리가 매트가 들어가는 부분을 빛에 노출되지 않게 하기 위해, 상을 맺히지 않게 하기 위해 렌즈 필름 부분에 빛을 들어가지 않도록 촬영을 했다. 

-------------
## 크로마키의 역사
1. **다중노출**
필름 하나로 매트를 걸어주어 정말 머리가 떨어진 것처럼 연출. '흑마법이 아니냐는' 등 그 당시 뜨거운 반응이었음.

2. **블랙스크린**
내용들을 블랙스크린으로 촬영하고 촬영된 필름을 감광을 계속 높히면 내용물만 남는다. 

3. **블루와 옐로우 스크린**

4. **디즈니 vapor lamp**
디즈니에서 개발함. 기술을 독점적으로 사용하여(공유하지 않아) VFX산업의 발전 속도를 더디게 함. 인화하는 과정에서 특정빛의 스펙트럼을 삭제하여 합성기술로 이용함

5. **블루스크린**
디즈니에 있다 나온 사람이 개발함. 비싸다. 

6. **그린스크린**
* 블루스크린보다 빛을 덜 요구하고 전기에서 더 밝다는 장점이 있다. 


=============
## Chroma Key Lighting
크로마키 방에 쏟아지는 조명들 중 천장에 달린 두개는 피사체를 향한 것이 아니라 벽을 향한 것이다. 사람의 그림자가 벽에 지기 때문에 그것을 방지하고자 벽을 향해 쏜다. 

## soft key, hard key + keymix
우리의 목적은 알파매트를 추출하는 것이다. 키어는 하나만 사용 가능한 것이 아니다. 여러개 써도 된다. 

## DESPILL
우리가 키를 따면 그린매트가 픽셀에 묻는다. 안 묻을 수가 없다. 이것을 억제하는 법은

키잉으로 알파 추출. 로토 쓸 수 있고 

고양이 할 때 다시 보기..뭘 할 수 있다

## **KEYER**
기본적으로 아웃을 알파로 내보낸다.

**DEFERENCE**
두 프레임간 차이를 알고 싶을 때 사용하는 노드이다. 사전에 프레임홀드로 키를 잡아주고 연결해주면 사용할 수 있다. 

**KEYLIGHT**
알파채널을 더 따내고 싶을 때 SCREEN MATTE를 사용하면 된다. 주로 Clip black 과 Clip white를 사용 

**copy**
a알파를 b알파로 복사한다. 키작업을 할 떄 원본 플레이트가 콘트라스트 등이 바뀌어도 알파만 잘 뽑히면 된다. 그리고 원본과 연결하면 되니까 다들 주의하자~~ 주의하자~~ 

**Primatte**
operation 순서대로 작업한다고 생각하면 된다. 
알파채널 강하게 들어가있으면 스필로 빼주기 

**Ultimatte**
우리가 사용할거면 프리랑 얼티 둘다 forground에 적용하면 된다 



=============
## GRADE NODE

input data를 조절하는 필터 노드이다. 우리는 Whitepoint, Lift, Gain, Multiply와 Gamma를 조절할 수 있고 Offset을 줄일 수 있다.  

![원본](https://postfiles.pstatic.net/MjAyMTEwMTRfNjQg/MDAxNjM0MTUzMzkzNzg4.EFx9InGrtZ7f56WZzFFZQa5r6w1gTplkkdaEu2c9AUAg.aFSut_eLx8qT0Mt5IirQHj9QlzNo3G_LT-j0-Dt5vngg.JPEG.hjkl3805/%EA%B8%88%EC%86%8D.jpg?type=w773)

원본

![누크적용](https://postfiles.pstatic.net/MjAyMTEwMTRfMjY4/MDAxNjM0MTUzMzkzODcx.8tBUBek0TlWInizW-tnua4tFcwMvck6wwXVoWUGZ6tUg.RlrDX_DMDpjNtb0vig1K6WgxYb2BnQQtbL8pojGjQcYg.PNG.hjkl3805/5test.png?type=w773)
![누크적용](https://postfiles.pstatic.net/MjAyMTEwMTRfMTY3/MDAxNjM0MTUzNDI1ODU1.785g8LFoIfi1sOJJL-bbIsvycFqjJGmKy6-Wr5-b4UQg.OfZ9gamQ6_41e0GVZWH6RQ5tJ-ZtaC7CPabq6eZV_nAg.PNG.hjkl3805/K-5792.png?type=w773)

grade적용값

좀더 밝은 느낌으로 바꿔보았다. 
