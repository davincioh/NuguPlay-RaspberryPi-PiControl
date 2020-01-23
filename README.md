# Play Builder로 '파이컨트롤' Play 만들기
Play는 NUGU 플랫폼의 엔진들과 통신해 서비스를 제공하는 단위로서, 사용자와 상호 작용하여 의도를 이해하고 그에 맞는 적절한 답변을 주거나 명령을 수행합니다. Play로 서비스를 제공하기 위해서는 사용자의 발화를 이해하여 의도를 파악하고 그에 맞는 답변을 제공해야 합니다.

- 의도 : 라즈베리 파이의 불을 켜고싶다. 
- 기능 : 라즈베리 파이 GPIO를 컨트롤하는 명령어를 전달한다. 그리고 사용자에게 명령이 수행되었다고 대답한다.


   - [Play Builder 가이드문서](https://developers.nugu.co.kr/docs/nugu-developers-an-overview/nugu-play-kit.html#play)


라즈베리파이 제어를 위한 명령어 구성하기
--

NUGU에서 라즈베리 파이를 제어하기 위해서는 크게    

- Play 호출이름 (Invocation Name)     "파이컨트롤"
- Play 세션 (Session)                       
- Play 시작과 종료                          "파이컨트롤 시작/그만"
- Intent와 Entity                             "Entity : LED" / "Intent : OnLED"

를 머릿속에 유념하게 구성하시면 쉽게 하실 수 있습니다.    



사용자의 의도를 학습하여 더욱 똑똑하게 인식한다.
--
Play가 제공할 기능들을 사용하기 위해 사용자는 발화를 통해 Play에게 의도를 전달해야 합니다.    
인간과 기계(Play)가 음성 대화를 통해 상호 작용할 수 있도록 하는 언어모델을 User Utterance Model이라고 합니다. 
Play는 이러한 모델을 통해 사용자의 말을 이해하고 그 속에 담긴 요청/명령을 수행할 수 있게 됩니다.

그리고, User Utterance Model은 Intent와 Entity로 구성됩니다.    
여기서 Intent는 Play의 기능을 동작시키기 위해 표현하는 사용자 의도를 의미하며, Entity는 사용자의 요청을 정확히 처리하기 위해 Intent 외에 추가로 알아야 하는 개체를 의미합니다. 


Play Builder는 사용자가 정의한 User Utterance Model을 바탕으로 NLU 엔진을 자동으로 학습시킵니다.    
이후 사용자가 예상 발화와 일치하거나 유사한 의도를 가지는 발화를 한 경우에 NLU 엔진은 해당 Intent와 Entity로 분석합니다.

라즈베리파이를 예를들어 설명드리자면 NUGU서버가 사용자의 말을 이해하기 위해서는 먼저, NUGU스피커에 발화(명령)하는 문장을 적어줘야 합니다.

 - "라즈베리파이에서 엘이디 밝게해줘", 
 - "파이에서 LED 켜줘"
 - "보드에서 불 꺼줘" 

기계가 사람의 말을 인식하기 위해서는 위의 문장과 같이 사용자가 할 수 있는 발화를 모두 적어줘야 합니다. 하지만 그렇게 되면 적어야할 문장은 수 없이 늘어나고 사람마다 말하는 스타일이 다르기 때문에 몇개의 문장을 적어야할지 막막하게 됩니다.

NUGU Developers 에서는 Intent와 Entity를 바탕으로 비슷한 단어, 문장을 이해하고 패턴과 의도를 학습합니다. 
그래서 비슷한 문장을 말하더라도 인식 될 수 있게 도와줍니다. 
사용자는 "라즈베리파이에서 불 켜" 라고만 적었지만 학습 후에는 "불 켜줘" "불 켜 줄래" 등 비슷한 유형의 단어도 인식될 가능성이 높아집니다. 
NUGU Developers의 제일 강력한 기능이지 않을 까 생각됩니다. 


실습하기 
--
 - [Play 실습 예제 (Hello World)](https://developers.nugu.co.kr/docs/create-plays-with-play-builder/hello-aria.html#hello-aria)

자 이제, LED를 켜보기 위한 Play를 작성해볼까요?
Play Builder에서 새 Play를 생성합니다.

- Play를 생성합니다.
- 기본정보를 입력합니다.
- Custom Entity Types를 설정합니다.
- Entity 라즈베리파이를 등록합니다
- Entity LED를 등록합니다.
- Custom Intents 를 설정합니다.
- Custom Intent LED를 켜는 명령어를 등록합니다.
- Custom Intent LED를 끄는 명령어를 등록합니다.
- 사용자의 발화에 따른 기능수행을 위해 Custom Action을 정의합니다.
- 불 켜는 기능을 정의합니다. (1/2)
- 불 켜는 기능을 정의합니다. (2/2)
- 불을 끄는 기능을 정의합니다. (1/2)
- 불을 끄는 기능을 정의합니다. (2/2)
- Play가 완성되었습니다. 빌드를 합니다.












