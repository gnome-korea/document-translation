## 파트 II. 클러터 빌드하기 ##

Emmanuele Bassi

 &lt;[ebassiopenedhand.com](http://ebassiopenedhand.com)&gt;

### 클러터 의존요소 ###
<table border=0>
	<tr><td> GLib                 </td><td> 그래픽 사용자 인터페이스에 한정하지 않은 범용 유틸리티 라이브러리입니다. GLib 쓸모 있는 수많은 데이터 형식, 매크로, 형 변환, 문자열 유틸리티, 메인 루프 추상체 등이 있습니다. </td></tr>
	<tr><td> GObject              </td><td> GLib 객체 시스템은 유연하고, 확장성 있으며 C언어에 대해 (다른 언어로의) 의도적인 대응이 용이한 객체지향 프레임워크의 필수 구현체를 제공합니다.                    </td></tr>
	<tr><td> Pango                </td><td> Pango는 국제화에 역점을 두고 텍스트를 배치하고 표현하는 라이브러리입니다.                                                             </td></tr>
	<tr><td> 백엔드 윈도우 구현 시스템 라이브러리 </td><td> GLX, EGL(1.1), 코코아(OS X), WGL(윈도우즈)                                                                     </td></tr>
	<tr><td> 그래픽 표현               </td><td> Open GL( 멀티 텍스처링 지원 1.2 또는 1.3 이상 )또는 OpenGL ES (1.1 또는 2.0)                                            </td></tr>
</table>

### 플랫폼 별 명령 ###
#### 리눅스 ####

데비안이나 우분투를 사용한다면 [http://debian.o-hand.com/](http://debian.o-hand.com/)에 있는 보통 데비안에서의 방법대로 미리 컴파일한 바이너리 패키지를 설치할 수 있습니다.

클러터를 소스로부터 빌드하려면 [http://source.clutter-project.org/sources](http://source.clutter-project.org/sources)에서 최신 소스 압축 파일을 받습니다. 압축 파일로부터 소스코드를 풀고 나면 상위 디렉터리에서 다음 명령을 실행합니다.

<pre>
 $ ./configure
 $ make
 # make install
 </pre>

configure 스크립트로 전달할 수많은 추가 인자를 사용하여 빌드를 설정할 수 있습니다. 추가 인자의 전체 목록은 *./configure --help*를 실행하면 보실 수 있습니다. 다음 인자들을 클러터에서 사용합니다.

<table border="0" cellpadding="2" cellspacing="2">
	<tr><td> --enable-debug=[no/minimum/yes]                      </td><td> 클러터 디버그 수준을 조절합니다. 가능한 값은 yes(모든 GLib assert, 검사내용, 실행시간 디버그 메시지), minimum(GLib에 대해 그냥 검사내용 및 실행시간 디버그 메시지를 뿌립니다), no(모든 GLib assert, 검사내용 실행시간 디버그 메시지를 보여주지 않습니다) 입니다. 개발주기에 있어서 기본값은 yes이고 안정 릴리즈에서의 기본값은 minimum입니다. 성능과 밀접한 방향이 GLib 형식 시스템 검사 뿐이기 전에는 no값을 사용하면 안됩니다. </td></tr>
	<tr><td> --enable-cogl-debug=[no/minimum/yes]                 </td><td> COGL 디버그 수준을 조절합니다. --enable-debug와 비슷합니다.                                                                                                                                                                                                                                  </td></tr>
	<tr><td> --enable-maintainer-flags=[no/yes]                   </td><td> 엄격한 컴파일러 플래그를 사용합니다. 기본값은 no 입니다.                                                                                                                                                                                                                                           </td></tr>
	<tr><td> --enable-gtk-doc                                     </td><td> 문서를 빌드하기 위해 gtk-doc을 사용합니다. 기본값은 no 입니다                                                                                                                                                                                                                                     </td></tr>
	<tr><td> --enable-manual=[no/yes]                             </td><td> 프로그램 개발자 설명서를 빌드합니다. jw와 xmlto 바이너리가 필요합니다. 기본값은 no 입니다.                                                                                                                                                                                                                    </td></tr>
	<tr><td> --with-flavour=[glx/eglx/eglnative/win32/osx/cex100] </td><td> 클러터 백엔드를 선택합니다. 기본값은 glx입니다.                                                                                                                                                                                                                                                </td></tr>
	<tr><td> --with-imagebackend=[gdk-pixbuf/quartz/internal]     </td><td> 그림 불러오기 백엔드를 선택합니다. 리눅스와 윈도우즈에서의 기본값은 gdk-pixbuf이고, OS X에서의 기본값은 quartz입니다. 내부 그림 불러오기 백엔드는 새 플랫폼으로 이식하거나 테스트 목적으로만 사용하며 안정성이나 기능성 측면에 대하여는 보장하지 아니합니다.                                                                                                                     </td></tr>
	<tr><td> --with-gles=[1.1/2.0]                                </td><td> COGL을 지원하기 위한 GLES 버전을 선택합니다. 기본값은 1.1입니다.                                                                                                                                                                                                                                  </td></tr>
	<tr><td>--with-json=[internal/check]</td><td>ClutterScript UI 정의 파일을 해석하기 위해 JSON-Glib의 내부 복제물을 사용할지, 시스템에 설치한 라이브러리를 확인할 것인지를 선택합니다. 기본값은 internal입니다.
	<tr><td>--enable-xinput=[no/yes]</td>XInput 1 지원을 활성화할 지에 대한 여부입니다. 기본값은 no 입니다.
	<tr><td>--enable-introspection=[no/auto/yes]</td><td>GObject Introspection 데이터를 빌드 중에 생성할 것인지에 대한 여부입니다. 기본값은 auto입니다.</td></tr>
</table>

#### 윈도우즈 ####

윈도우즈에서 클러터를 빌드하는 추천 방법은 [mingw](http://www.mingw.org/) 툴체인을 사용하는 것입니다. 이 방법을 통해서라면 리눅스 설치로부터 또는 MSYS를 사용하여 윈도우즈에서 바로 크로스 컴파일을 해서 동작할 것입니다. 자세한 정보는 [위키](http://wiki.clutter-project.org/wiki/BuildingClutterOnWindows)를 참조하십시오.

#### OS X ####

시작하기전에 OSX 설치 디스크나 애플 웹사이트 내려받기를 통해 XCode를 설치해야 합니다.

참고: 이 방법은 OSX 10.6(스노우 레오파드:설범)에서만 시험 했습니다.

현재 프로그램을 개발하기 위해, 또는 클러터를 뜯어보기 위해 클러터를 설치하는 유일한 방법은, 여러분이 직접 빌드하는 것입니다. 추천하는 경로는 [MacPorts](http://www.macports.org/)를 설치하고 업데이트 한 다음에 MacPorts에서 다음 명령 실행을 통해 설치하는 것입니다.

<pre>
$ sudo port install libpixman-devel cairo-devel pango gtk-doc
</pre>

이 방법을 통해 클러터를 빌드할 필요한 의존요소를 제공 받을 것입니다.

참고하셔야 할 부분은 gtk-doc을 빌드하면 수많은 MacPorts 의존 요소를 끌어올 것이며 상당한 시간이 걸린다는 점입니다. 여러분은 `--disable-gtk-doc --disable-docs` 로 빌드를 설정하면 문서 빌드를 취소한 만큼 이 의존요소를 생략할 수 있습니다.

클러터 Quartz 백엔드는 --with-flavour=osx 명령줄 인자를 configure 스크립트에 전달해서 빌드합니다. 이 인자를 전달하지 않으면 GLX 백엔드를 빌드할 것입니다. 기본적으로 Quartz 백엔드는 텍스처에 이미지를 불러오기 위해 CoreGraphics에 의존합니다만, GDK-Pixbuf나 내부적으로 매우 실험적인 PNG, JPEG 로더에게 의존할 수도 있습니다.

GTK introspection은 OSX에서 시험해보지 않았습니다. (MacPorts 패키지에 없습니다) 그래서 --disable-introspection 인자를 통해 이것을 비활성화 하는 것을 추천합니다.

추천하는 방법대로 MacPorts의 최상위 위치에서 빌드한다면, 다음 설정 명령으로 충분할 것입니다.
<pre>
$ ./configure --with-flavour=osx --disable-introspection --prefix=/opt
</pre>
