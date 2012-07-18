## 파트 I. 개요 ##

Emmanuele Bassi

 &lt;[ebassiopenedhand.com](http://ebassiopenedhand.com)&gt;

클러터는 그래픽 사용자 인터페이스를 좀 더 빠르게, 화려하게 만들기 위한 GObject 기반 라이브러리입니다.

클러터는 3차원 공간에 2차원 평면의 장면 그래픽이나 '액터'를 다룹니다.

[ClutterActor]는 각각의 평면에 대한 상위클래스 입니다. 모든 [ClutterActor]는 3차원 공간에 놓고 크기를 조절할 수 있으며 회전할 수 있습니다. 게다가 2차원 클리핑, 하위요소, 불투명도 같은 다른 속성을 설정할 수 있습니다. 상위 액터에 적용하는 변환 또한 그 어떤 하위요소에도 적용할 수 있습니다. 액터는 이벤트를 받을 수도 있습니다.

[ClutterActor]의 하위클래스에는 [ClutterStage], [ClutterTexture], [ClutterText], [ClutterRectangle], [ClutterCairoTexture], [ClutterGroup], [ClutterBox]가 있습니다. [ClutterActors]는 상위 요소에 추가하고 변환한 다음 사용자의 눈에 보이도록 합니다.

[ClutterStage]는 [ClutterActor]의 상위 수준에 있습니다. 이 것은 창이나 프레임버퍼를 나타냅니다. 클러터를 초기화 했을 때 자동으로 만들어집니다. [ClutterStage]는 [ClutterContainer]인터페이스의 구현 클래스인 [ClutterGroup]입니다.

클러터를 통해서라면 [ClutterFixedLayout] 배치 관리자를 통해 명시적인 위치 지정을 하고 크기 조정을 할 수 있으며 [ClutterBoxLayout], [ClutterFlowLayout], [ClutterTableLayout]과 같은 유동 매치 관리자를 통해 암시적 위치 지정 및 크기 조정을 할 수 있습니다. [ClutterGroup]과 [ClutterStage]와 같은 고정 배치 관리자에 있는 액터는 [ClutterConstraint] 하위클래스를 사용하여 암시적인 위치 지정과 크기 조정도 할 수 있습니다.

[ClutterTimelines]는 클러터의 애니매이션 유틸리티 기반을 제공합니다. [ClutterActor]는 다양한 [ClutterBehaviour] 구현체를 통한 명시적 애니메이션을 사용하거나, 또는 [clutter_actor_animate()]함수를 사용한 암시적 애니메이션을 사용하여 애니메이션으로 만들 수 있습니다. 애니메이션은 [ClutterState] 클래스를 통해 각 상태에 대해 이름을 붙여 정의할 수 있습니다.

클러터는 [JSON] 포맷으로 이루어진 'UI 정의' 파일을 불러오기 위해 사용하는 [ClutterScript], GPU 쉐이더를 액터에 적용하기 위한 [ClutterShader] 클래스, 모델-뷰-컨트롤러(MVC) 목록 형식의 구현을 위한 [ClutterModel] 클래스, 그리고 [ClutterAction]들, [ClutterConstraint]들, 그리고 [ClutterEffect]들 을 포함한 수많은 유틸리티를 보유하고 있습니다.

