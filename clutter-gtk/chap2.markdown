## 클러터-gtk 위젯 ##

* [GtkClutterEmbed](#gtkclutterembed) - 클러터 장면을 넣는 위젯입니다
* [GtkClutterActor](#gtkclutteractor) - 클러터 스테이지에 위젯을 넣는 액터입니다
* [GtkClutterWindow](#gtkclutterwindow) - 클러터 스테이지에 내용을 올려놓는 GtkWindow입니다

### GtkClutterEmbed ###

GtkClutterEmbed - 클러터 장면을 넣는 위젯입니다

#### 개요 ####
<table border="0" cellspacing="2" cellpadding"2">
	<tr><td> struct     </td><td> GtkClutterEmbed;      </td><td> &nbsp;    </td></tr>
	<tr><td> struct     </td><td> GtkClutterEmbedClass; </td><td> &nbsp;    </td></tr>
	<tr><td> GtkWidget* </td><td> gtk_clutter_embed_new </td><td> (_void_); </td></tr>
	<tr><td>ClutterActor *</td><td> gtk_clutter_embed_get_stage</td><td>(_GtkClutterEmbed *embed_);
</table>

#### 객체 계층도 ####
<pre>
GObject
     +----GInitiallyUnowned
	      +----GtkWidget
		       +----GtkContainer
			        +-----GtkClutterEmbed
</pre>

#### 구현한 인터페이스 ####
GtkClutterEmbed는 AtkImplementorIface와 GtkBuildable을 구현했습니다.

#### 설명 ####
[GtkClutterEmbed](#gtkclutterembed)는 GTK+ 프로그램에 들어있는 ClutterStage를 넣는 GTK+ 위젯입니다.

[GtkClutterEmbed](#gtkclutterembed)를 사용하면 위젯을 빌드하고 보여주며 GTK+ 프로그램에 있는 Clutter를 사용하여 빌드한 장면과 상호작용을 할 수 있습니다.

#### 세부 내용 ####

##### struct GtkclutterEmbed #####
 struct GtkClutterEmbed;

기본 클러터 스테이지에 있는 GtkWidget입니다.
GtkClutterEmbed 구조체는 private 데이터만 들어있으며 제공한 API를 사용해서 접근해야 합니다.

---

##### struct GtkClutterEmbedClass #####
<pre>struct GtkClutterEmbedClass{
};
</pre>

[GtkClutterEmbed](#gtkclutterembed)의 상위클래스입니다.
GtkClutterEmbedClass는 private 데이터만 들어있습니다.

---

##### gtk\_clutter\_embed\_new () #####
`GtkWidget *     gtk_clutter_embed_new          (void);`

새 [GtkClutterEmbed](#gtkclutterembed) 위젯을 만듭니다. 이 위젯은 GTK+ 프로그램에 있는 클러터 API를 사용해서 장면을 빌드하는데 사용할 수 있습니다.

_반환값_: 새로 생성한 [GtkClutterEmbed](#gtkclutterembed)

##### gtk\_clutter\_embed\_get\_stage () #####
`ClutterActor *  gtk_clutter_embed_get_stage    (GtkClutterEmbed *embed)`

_embed_에서 ClutterStage를 가져옵니다. 반환한 스테이지는 클러터 장면에 액터를 추가하는데 사용할 수 있습니다.

_embed_: [GtkClutterEmbed](#gtkclutterembed)

_반환값_:  클러터 스테이지. 반환한 액터에 대해 할당을 해제하거나 참조를 끊을 수 없습니다. [전달 못 함]

#### 추가 참조 ####
ClutterStage

### GtkClutterActor ###
GtkClutterActor - 클러터 스테이지에 위젯을 넣는 액터입니다

#### 개요 ####
<table border="0" cellspacing="2" cellpadding="2">
	<tr><td> struct         </td><td> GtkClutterActor;                    </td><td> &nbsp;                      </td></tr>
	<tr><td> struct         </td><td> GtkClutterActorClass;               </td><td> &nbsp;                      </td></tr>
	<tr><td> ClutterActor * </td><td> gtk_clutter_actor_new               </td><td> (_void_);                   </td></tr>
	<tr><td> ClutterActor * </td><td> gtk_clutter_actor_new_with_contents </td><td> (_GtkWidget *contents_);    </td></tr>
	<tr><td> GtkWidget *    </td><td> gtk_clutter_actor_get_contents      </td><td> (_GtkClutterActor *actor_); </td></tr>
	<tr><td> GtkWidget *    </td><td> gtk_clutter_actor_get_widget        </td><td> (_GtkClutterActor *actor_); </td></tr>
</table>

#### 객체 계층도 ####
<pre>
GObject
     +----GInitiallyUnowned
	      +----ClutterActor
		       +----GtkClutterActor
</pre>

#### 구현한 인터페이스 ####
GtkClutterActor는 ClutterScriptable, ClutterAnimatable, AtkInplementorIface, ClutterContainer를 구현했습니다.

#### 속성 ####
` "contents"        GtkWidget*          : 읽기 / 쓰기 / 생성`

#### 설명 ####
[GtkClutterActor](#gtkclutteractor)는 클러터 장면그래픽에 어떤 GtkWidget이든 넣을 수도 있게 해주는 ClutterContainer입니다.

[GtkClutterActor](#gtkclutteractor)는 [GtkClutterEmbed](#gtkclutterembed)가 제공하는 ClutterStage 안에서 GtkWidget를 넣는것만을 허용합니다. 클러터 자체에서 다루는 ClutterStage에서는 [GtkClutterActor](#gtkclutteractor)를 사용할 수 없습니다.

#### 세부 내용 ####

##### struct GtkClutterActor #####

`struct GtkClutterActor;`

GtkWidget이 들어있는 ClutterActor입니다.

---

##### struct GtkClutterActorClass #####

<pre>struct GtkClutterActorClass{
};
</pre>

[GtkClutterActor](#gtkclutteractor)의 상위클래스입니다.

---

##### gtk\_clutter\_actor\_new () #####

`ClutterActor *     gtk_clutter_actor_new               (void);`

새 [GtkClutterActor](#gtkclutteractor)를 만듭니다.

이 위젯은 gtk\_clutter\_actor\_get\_widget() 을 사용하여 내부 GtkBin 컨테이너를 전달하고 GtkWidget을 컨테이너에 추가하여 클러터 장면에 GtkWidget을 넣을때 사용할 수 있습니다.

_반환값:_ 새로 생성한 [GtkClutterActor](#gtkclutteractor)

---

##### gtk\_clutter\_actor\_new\_with\_contents () #####

`ClutterActor *     gtk_clutter_actor_new_with_contents (GtkWidget *contents);`

새 [GtkClutterActor](#gtkclutteractor) 위젯을 만듭니다. 이 위젯은 클러터 장면에 Gtk 위젯을 넣을때 사용할 수 있습니다.

이 함수는 논리적으로 다음과 같습니다.
<table border="0">
<tr><td>
ClutterActor *actor = gtk_clutter_actor_new();<br/>
GtkWidget *bin = gtk_clutter_actor_get_widget (GTK_CLUTTER_ACTOR (actor));
gtk_container_add (GTK_CONTAINER(bin), contents);
</td></tr>
</table>

_contents_: ClutterActor로 감쌀 GtkWidget

_반환값_: 새로 만든 [GtkClutterACtor](#gtkclutteractor)

---

##### gtk\_clutter\_actor\_get\_contents () #####

`GtkWidget *        get_clutter_actor_get_contents      (GtkClutterActor *actor);`

_actor_의 내용을 유지하기 위해 사용하는 GtkBin의 자식 요소를 전달합니다.

이 편의함수는 논리적으로 다음과 같습니다.
<table border="0">
<tr><td>
GtkWidget *bin;<br/>
bin = gtk_clutter_actor_get_widget (GTK_CLUTTER_ACTOR (actor));<br/>
return gtk_bin_get_child (GTK_BIN (bin));
</td></tr>
</table>

_actor_: [GtkClutterActor](#gtkclutteractor)

_반환값_: GtkWidget. 내용이 없을 경우 NULL반환 [전달 못 함]

---

##### gtk\_clutter\_actor\_get\_widget () #####

`GtkWidget *        get_clutter_actor_get_widget        (GtkClutterActor *actor);`

"contents" 위젯을 유지하기 위해 사용하는 GtkBin을 전달합니다.

_actor_: [GtkClutterActor](#gtkclutteractor)

_반환값_: GtkBin [전달 못 함]

#### 속성 세부 내용 ####
##### "contents" 속성 #####

` "contents"        GtkWidget*          : 읽기 / 쓰기 / 생성`

[GtkClutterActor](#gtkclutteractor)에 넣을 GtkWidget 입니다

### GtkClutterWindow ###
GtkClutterWindow - 클러터 스테이지에 내용을 올려놓는 GtkWindow 입니다

#### 개요 ####
<table border="0" cellpadding="2" cellspacing="2">
	<tr><td> struct         </td><td> GtkClutterWindow;            </td><td> &nbsp;                        </td></tr>
	<tr><td> struct         </td><td> GtkClutterWindowClass;       </td><td> &nbsp;                        </td></tr>
	<tr><td> GtkWidget *    </td><td> gtk_clutter_window_new       </td><td> (_void_);                     </td></tr>
	<tr><td> ClutterActor * </td><td> gtk_clutter_window_get_stage </td><td> (_GtkClutterWindow *window_); </td></tr>
</table>

#### 객체 계층도 ####
<pre>
GObject
     +----GInitiallyUnowned
	      +----GtkWidget
		        +-----GtkContainer
				       +----GtkBin
					         +----GtkWindow
							       +----GtkClutterWindow
</pre>

#### 구현한 인터페이스 ####
GtkClutterWindow는 AtkInplementorIface와 GtkBuildable을 구현했습니다.

#### 설명 ####
[GtkClutterWindow](#gtkclutterwindow)는 클러터 스테이지를 넣는 GtkWindow의 하위클래스입니다.

[GtkClutterWindow](#gtkclutterwindow)는 GtkWindow 하위 요소가 [GtkclutterActor](#gtkclutteractor) 내부로 자동으로 들어간다는 점만 제외하면 GtkWindow와 완전한 유사성을 지니며, 이 때문에 내장 ClutterStage의 일부이기도 합니다.

클러터 액터는 gtk\_clutter\_window\_get\_stage()를 호출해서 동일한 스테이지에 추가할 수 있습니다.

#### 세부 내용 ####

##### struct GtkClutterWindow #####

`struct GtkClutterWindow;`

ClutterStage가 들어있는 GtkWindow입니다.
GtkClutterWindow 구조체는 private 데이터만 들어있으며 제공하는 API를 통해서 접근해야 합니다.

---

##### struct GtkClutterWindowClass #####

<pre>struct GtkClutterWindowClass{
};
</pre>

[GtkClutterWindow](#gtkclutterwindow)의 상위클래스 입니다.

GtkClutterWindowClass 구조체는 private 데이터만 들어있습니다.

---

##### gtk\_clutter\_window\_new () #####

 
`GtkWidget *      gtk_clutter_window_new        (void);`

새 [GtkClutterWindow](#gtkclutterwindow) 위젯을 만듭니다.

이 창은 GtkWidget을 놓을 숨겨진 ClutterStage를 제공합니다. 이는 다른 ClutterActor 또한 스테이지에 놓일 수 있게 할 수 있습니다.

_반환값_: 새로 만든 [GtkClutterWindow](#gtkclutterwindow)

---

##### gtk\_clutter\_window\_get\_stage () #####
`ClutterActor *   gtk_clutter_window_get_stage  (GtkClutterWindow *window);`

지정한 창이 들어있는 ClutterStage를 전달합니다.

다른 액터를 ClutterStage에 추가하고 싶다면 이 함수를 사용하십시오.

_window_: [GtkClutterWindow](#gtkclutterwindow)

_반환값_: 창의 클러터 스테이지. [전달 못 함]
