## 파트 III. 클러터 실행하기 ##

Emmanuele Bassi

 &lt;ebassilinux.intel.com&gt;

### 환경 변수 ###

클러터는 초기화 중에 자동으로 환경 변수를 확인합니다. 이 환경 변수들은 디버그 도구와 같은 의미가 있으며 기본 기능을 덮어쓰거나 알려진 하드웨어 문제를 바로 잡는데 사용합니다. 

<table border="0">
	<tr><td> CLUTTER_TEXT_DIRECTION         </td><td> 클러터의 모든 팡고 배치에 대해 글쓰기 방향을 강제합니다. 유효한 방향은 ltr(왼쪽에서 오른쪽으로)과 rtl(오른쪽에서 왼쪽으로)가 있습니다. </td></tr>
	<tr><td> CLUTTER_SHOW_FPS               </td><td> 클러터가 보여주는 초당 프레임 수를 출력합니다.                                                   </td></tr>
	<tr><td> CLUTTER_DEFAULT_FPS            </td><td> 기본 프레임 재생율을 설정합니다                                                               </td></tr>
	<tr><td> CLUTTER_DISABLE_MIPMAPPED_TEXT </td><td> 텍스트를 표현할때 밉매핑을 비활성화합니다                                                       </td></tr>
	<tr><td> CLUTTER_FUZZY_PICK             </td><td> "퍼지 피킹(fuzzy picking)"을 활성화 합니다.                                             </td></tr>
	<tr><td> CLUTTER_DEBUG                  </td><td> 클러터 디버깅 모드를 활성화합니다.                                                          </td></tr>
	<tr><td> COGL_DEBUG                     </td><td> Cogl 디버깅 모드를 활성화합니다.                                                         </td></tr>
</table>

GLX 백엔드에 다음과 같은 변수도 있습니다.

<table botder="0">
	<tr><td>CLUTTER_VBLANK</td><td>사용할 sync-to-vblank 모드를 선택합니다. 유효한 값은 none,dri,glx가 있습니다</td></tr>
</table>

### 명령줄 인자 ###
환경 변수와 유사하게 클러터는 초기화 과정에서 해석하는 명령줄 스위치를 설정합니다.

<table border="0">
	<tr><td> --clutter-show-fps                 </td><td> CLUTTER_SHOW_FPS와 동일합니다. 초당 프레임 수로 표현 속도를 출력합니다.                </td></tr>
	<tr><td> --clutter-default-fps=FPS          </td><td> CLUTTER_DEFAULT_FPS와 동일합니다. 기본 프레임 재생율을 설정합니다.                  </td></tr>
	<tr><td> --clutter-text-direction=DIRECTION </td><td> CLUTTER_TEXT_DIRECTION과 동일합니다. 글쓰기 방향을 설정합니다.                   </td></tr>
	<tr><td> --clutter-disable-mipmapped-text   </td><td> CLUTTER_DISABLE_MIPMAPPED_TEXT와 동일합니다. 텍스트를 표현할 때 밉매핑을 비활성화합니다. </td></tr>
	<tr><td> --clutter-use-fuzzy-picking        </td><td> CLUTTER_FUZZY_PICK과 동일합니다. "퍼지 피킹(fuzzy picking)"을 활성화합니다.      </td></tr>
	<tr><td> --clutter-debug=FLAGS              </td><td> CLUTTER_DEBUG와 동일합니다. 클러터 디버깅 플래그를 FLAGS에 설정합니다.                </td></tr>
	<tr><td> --clutter-no-debug=FLAGS           </td><td> 클러터 디버깅 플래그 중에 FLAGS에 설정한 것을 뺍니다.                               </td></tr>
	<tr><td> --cogl-debug=FLAGS                 </td><td> COGL_DEBUG와 동일합니다. Cogl 디버깅 플래그를 FLAGS에 설정합니다.                  </td></tr>
	<tr><td> --cogl-no-debug=FLAGS              </td><td> Cogl 디버깅 플래그 중에 FLAGS에 설정한 것을 뺍니다.                              </td></tr>
</table>

X11 백엔드에 다음 명령줄 옵션도 있습니다.

<table border="0">
	<tr><td> --display=DISPLAY </td><td> 사용할 X11 디스플레이를 설정합니다. </td></tr>
	<tr><td> --screen=SCREEN   </td><td> 사용할 X11 화면 번호를 설정합니다  </td></tr>
	<tr><td> --synch           </td><td> X11이 동기화를 호출하도록 합니다   </td></tr>
</table>

GLX 백엔드에 다음 명령줄 옵션도 있습니다.

<table border="0">
	<tr><td>--vblank=METHOD</td><td>CLUTTER_VBLANK와 동일합니다. 사용할 sync-to-vblank 방식을 설정합니다.</td></tr>
</table>

### 클러터의 디버그 플래그 ###
디버깅 플래그는 CLUTTER\_DEBUG 환경변수와 --clutter-debug 스위치에서 사용할 수 있습니다. 여러 플래그는 콜론(:)으로 구분할 수 있습니다.

<table border="0">
	<tr><td> actor     </td><td> 일반 액터 관련 기록입니다다.                      </td></tr>
	<tr><td> animation </td><td> ClutterAnimation 기록입니다.               </td></tr>
	<tr><td> backend   </td><td> 백엔드 기능과 GL 컨텍스트 생성과 관련된 백엔드 관련 기록입니다. </td></tr>
	<tr><td> bahaviour </td><td> ClutterBehaviour 기록입니다.               </td></tr>
	<tr><td> event     </td><td> 이벤트 제어 기록입니다.                         </td></tr>
	<tr><td> layout    </td><td> ClutterLayoutManager 기록입니다.           </td></tr>
	<tr><td> misc      </td><td> 기타 요소 기록입니다.                          </td></tr>
	<tr><td> scheduler </td><td> 타임라인과 주 시계와 관련한 기록입니다.                </td></tr>
	<tr><td> script    </td><td> ClutterScript와 관련한 기록입니다.             </td></tr>
</table>

디버깅 플래그 전부를 표현하기 위해 특별한 "all" 플래그를 설정할 수 있습니다.
