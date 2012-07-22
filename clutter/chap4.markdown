## 파트 IV. 클러터 핵심부 참고서 ##

**목차**


[추상 클래스와 인터페이스](./chap4-1.markdown)

* [ClutterActor](./chap4-1-1.markdown) - 모든 보이는 스테이지 액터에 대한 기본 추상 클래스입니다
* [ClutterContainer](./chap4-1-2.markdown) - 컨테이너 액터를 구현하기 위한 인터페이스 입니다
* [ClutterChildArea](./chap4-1-3.markdown) - 컨테이너에 있는 액터의 래퍼입니다
* [ClutterMedia](./chap4-1-4.markdown) - 미디어 데이터의 재생을 제어하는 인터페이스 입니다
* [ClutterLayoutManager](./chap4-1-5.markdown) - 레이아웃 관리자의 기본 클래스입니다
* [ClutterLayoutMeta](./chap4-1-6.markdown) - 배치 관리자에 있는 액터의 래퍼입니다
* [ClutterActionMeta](./chap4-1-7.markdown) - 액터 수정자의 기본 클래스 입니다
* [ClutterAction](./chap4-1-8.markdown) - 이벤트 관련 로직에 대한 추상 클래스 입니다
* [ClutterConstraint](./chap4-1-9.markdown) - 위치나 크기를 제한하는 추상 클래스 입니다
* [ClutterEffect](./chap4-1-10.markdown) - 액터 효과에 대한 기본 클래스 입니다

[기본 액터](./chap4-2.markdown)

* [ClutterRectangle](./chap4-2-1.markdown) - 간단한 사각형을 표시하는 액터입니다
* [ClutterTexture](./chap4-2-2.markdown) - 그림을 표시하고 조작하는 액터입니다
* [ClutterClone](./chap4-2-3.markdown) - 원본 액터의 복제물을 표시하는 액터입니다
* [ClutterText](./chap4-2-4.markdown) - 텍스트를 표시하고 편집하는 액터입니다
* [ClutterCairoTexture](./chap4-2-5.markdown) - 카이로 통합 라이브러리로 표현하는 텍스처입니다

[컨테이너 액터](./chap4-3.markdown)

* [ClutterGroup](./chap4-3-1.markdown) - 고정 배치 컨테이너입니다
* [ClutterStage](./chap4-3-2.markdown) - 액터를 배치할 상위레벨 시각 요소입니다.
* [ClutterBox](./chap4-3-3.markdown) - 일반 배치 컨테이너입니다

[배치 관리자](./chap4-4.markdown)

* [ClutterFixedLayout](./chap4-4-1.markdown) - 고정 배치 관리자입니다
* [ClutterBinLayout](./chap4-4-2.markdown) - 단순 배치 관리자입니다
* [ClutterFlowLayout](./chap4-4-3.markdown) - 흐름 재조정 배치 관리자입니다
* [ClutterBoxLayout](./chap4-4-4.markdown) - 한줄로 자식요소를 정렬하는 배치 관리자입니다
* [ClutterTableLayout](./chap4-4-5.markdown) - 행열로 자식요소를 정렬하는 배치 관리자입니다

[동작](./chap4-5.markdown)

* [ClutterClickAction](./chap4-5-1.markdown) - 누를 수 있는 액터에 대한 동작입니다
* [ClutterDragAction](./chap4-5-2.markdown) - 액터 끌기를 가능케 하는 동작입니다
* [ClutterDropAction](./chap4-5-3.markdown) - 대상에 내려놓기 위한 동작입니다
* [ClutterGestureAction](./chap4-5-4.markdown) - 제스처를 표현하는 동작입니다
* [ClutterSwipeAction](./chap4-5-5.markdown) - 닦아내기를 표현하는 동작입니다

[제한자](./chap4-6.markdown)

* [ClutterAlignConstraint](./chap4-6-1.markdown) - 액터의 위치를 정렬하는 제한자입니다
* [ClutterBindConstraint](./chap4-6-2.markdown) - 액터의 위치와 크기를 할당해주는 제한자입니다
* [ClutterPathConstraint](./chap4-6-3.markdown) - 경로를 따라가는 제한자입니다
* [ClutterSnapConstraint](./chap4-6-4.markdown) - 두 액터를 함께 달라붙게 하는 제한자입니다

[효과](./chap4-7.markdown)

* [ClutterOffscreenEffect](./chap4-7-1.markdown) - 오프스크린 버퍼를 사용하는 효과의 기본 클래스 입니다
* [ClutterShaderEffect](./chap4-7-2.markdown) - 쉐이더 효과에 대한 기본 클래스 입니다
* [ClutterDeformEffect](./chap4-7-3.markdown) - 액터의 좌표를 변형하는 효과를 주는 기본 클래스 입니다
* [ClutterBlurEffect](./chap4-7-4.markdown) - 흐림 효과입니다
* [ClutterColorizeEffect](./chap4-7-5.markdown) - 색채 효과입니다
* [ClutterDesaturateEffect](./chap4-7-6.markdown) - 색농도 감소 효과입니다
* [ClutterPageTurnEffect](./chap4-7-7.markdown) - 페이지 넘김 효과입니다
