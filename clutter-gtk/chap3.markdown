## 기타 ##

유틸리티 함수 - GTK+에 클러터를 통합하기 위한 유틸리티 함수입니다

### 유틸리티 함수 ###

유틸리티 함수 - GTK+에 클러터를 통합하기 위한 유틸리티 함수입니다

#### 개요 ####

<table border="0" cellpadding="2" cellspacing="2">
	<tr><td> CluterInitError  </td><td> gtk_clutter_init             </td><td> (_int *argc,<br/> char ***argv_);                                                                                                                     </td></tr>
	<tr><td> clutterInitError </td><td> gtk_clutter_init_with_args   </td><td> (_int *argc,<br/>char ***argv,<br/>const char *parameter_string,<br/>GOptionEntry *entries,<br/>const char *translation_domain,<br/>GError **error_); </td></tr>
	<tr><td> GOptionGroup *   </td><td> gtk_clutter_get_option_group </td><td> (_void_);                                                                                                                                             </td></tr>
</table>

#### 설명 ####
GTK+ 프로그램에 클러터 장면을 적절하게 통합하려면 각 상태의 과정을 GTK+ 자체적으로 전달해야 합니다.

클러터-GTK는 현재 GTK+ 테마와 함께 동기화한 색의 처리 과정을 용이하게 처리하고, GdkPixbuf, GTK+ 에 저장한 항목과 아이콘 테마로부터 이미지 원본을 불러오는 API를 제공합니다.

#### 세부 내용 ####

##### gtk\_clutter\_init () #####

`ClutterInitError gtk_clutter_init           (int *argc, char ***argv);`

이 함수는 clutter\_init()와 gtk\_init() 대신 호출해야 합니다.

_argc_: 인자 카운트의 포인터 또는 NULL 입니다. [inout] [allow-none]

_argv_: 인자 벡터의 포인터 또는 NULL 입니다. [배열 길이=argc] [inout] [allow-none]

_반환값_: 성공시 CLUTTER\_INIT\_SUCCESS, 실패시 음의 정수 값을 반환합니다.


##### gtk\_clutter\_init\_with\_args () #####

`ClutterInitError gtk_clutter_init_with_args (int *args, char ***argv, const char *parameter_string, GOptionEntry *entries,`
`const char *translation_domain, GError **error);`

이 함수는 clutter\_init()와 gtk\_init\_with\_args() 대신 호출해야 합니다.

_argc_: 인자 카운트의 포인터 또는 NULL 입니다. [inout] [allow-none]

_argv_: 인자 벡터의 포인터 또는 NULL 입니다. [배열 길이=argc] [inout] [allow-none]

*parameter_string*: --help 출력의 첫번째 줄에 programname [OPTION...] 다음에 표시할 문자열입니다. [허용 안함]

_entries_: 프로그램의 옵션 내용이 있는 NULL로 끝나는 GOptionEntry의 배열입니다.

*translation_domain*: entries에 있는 옵션에 대해 gettext()로 --help 출력을 해석하는데 사용할 해석 도메인입니다.

_error_: 오류 위치를 반환하거나 NULL을 반환합니다.[allow-none]


_반환값_: 성공시 CLUTTER\_INIT\_SUCCESS, 실패시 음의 정수 값을 반환합니다.

##### gtk\_clutter\_get\_option\_group () #####

`GOptionGroup *     gtk_clutter_get_option_group    (void);`

클러터에서 인지한 명령줄 인자에 대해 GOptionGroup을 반환합니다. gtk\_clutter\_init() 이나 gtk\_clutter\_init\_with\_args()를 사용하는 대신에 여러분의 명령줄 인자를 해석하기 위해  g\_option\_context\_parse()를 사용한다면, g\_option\_context\_add\_group()으로 GOptionContext에 이 그룹을 추가해야 합니다.

gtk\_get\_option\_group()으로 만든 GTK 옵션 그룹과 clutter\_get\_option\_group\_without\_init()으로부터 가져온 클러터 옵션 그룹 다음에 GOptionContext에 이 옵션 그룹을 추가해야 합니다. 이 함수들과 함께 clutter\_get\_option\_group()을 함께 사용하면 안됩니다.

gtk-클러터의 옵션그룹이 gtk\_get\_option\_group()에 의존하는 경우 TRUE를 전달해야 합니다.

g\_option\_context\_parse()를 사용하여 반환된 GOptionGroupwith를 가지고 있는 GOptionContext에서 옵션을 해석해서 클러터와 GTK-클러터를 초기화 할 수 있습니다. 다음 코드로 설명하겠습니다

<table border="0">
<tr><td>
g_option_context_add_group (context, gtk_get_option_group(TRUE) );<br/>
g_option_context_add_group (context, cogl_get_option_group());<br/>
g_option_context_add_group (context, clutter_get_option_group_without_init());<br/>
g_option_context_add_group (context, gtk_clutter_get_option_group());<br/>
res = g_option_context_parse (context, &argc, &argv, NULL);
</td></tr>
</table>

는 기능적으로 다음과 같습니다.

<table border="0">
<tr><td>
gtk_clutter_init(&argc, &argv);
</td></tr>
</table>

반환한 GOptionGroup을 가진 GOptionContext에 대해 g\_option\_context\_parse()를 호출하고 나면 클러터와 GTK-클러터의 초기화가 보장됩니다.

_반환값_: ClutterGtk가 인식한 명령줄 인자에 대한 GOptionGroup.[transfer full]
