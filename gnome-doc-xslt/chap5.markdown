## 스타일시트 번역 ##
그놈 문서 스타일시트에서는 DocBook 문서의 표현물 출력의 지역화 지원을 제공합니다. 스타일시트의 지역화 가능한 문자열은 번역을 위해 확인되고 PO 파일과 `inittool` 로 가져옵니다. 그 다음에 이들이 번역되고 나서 `inittool`은 출력 내용을 지역화하는데 사용하는 스타일시트가 사용할 l10n.xml XML 파일로 합칩니다.

DocBook 스타일시트에 대한 완전한 국제화 지원 제공은 사소한 것이 아니며, 지역화를 제공하는 것은 문서의 형식이 어떻게 갖춰지는지 이해하는 번역자가 필요하며, 그 이외에도 DocBook이 어떻게 동작하는지도 알아야 합니다. DocBook은 고급 마크업 언어이며 문서를 수많은 구조화를 제공하는 프로그램의 처리를 필요로 합니다. DocBook 프로그램은 수많은 교차 참조 처리, 내용의 목차 생성, 머릿말 형식, 그리고 지역화가 필요한 다른 형식화 작업들을 수행합니다. 이 작업들을 지역화 하는 것은 단일 문장을 번역하는 것보다 더 많은 일들이 따라옵니다. 그래서 잘 갖춰진 자체 형식화 코드를 지역화 할 수 있습니다.


**우리를 돕는 것이 여러분을 돕는 길입니다**

    문서를 형식화 하는 것은 전세계적으로 제각기 다릅니다. 
    각각의 로캘은 오랜 형식화 관습과 방법의 역사를 지니고 있습니다.
    이 스타일시트의 관리자는 모든 로캘에서의 문서 형식화의 뉘앙스를 알지 못합니다.
    여러분의 로캘에 대해 우리가 더 나은 결과를 줄 수 있는 유일한 방법은 
    얼마나 많은 문제가 있는지 여러분이 이야기를 해주었을 때 입니다.


모든 지역화가 PO 파일에서 문자열을 번역하는 것으로 끝나겠지만, 단순한 문장이나 어구가 아닌 번역 가능한 문장이 있는 여러가지 경우가 있습니다. 게다가 번역자들은 XML 단편화 요소를 사용하여 데이터를 제공해야 합니다. 이 구조화된 단편화 요소들은 문맥을 기반으로 대체 형식화를 제공하거나 형식 문자열을 제공하는  서수 양식을 작업할 때 사용합니다.

### 단순 문자열 ###
번역한 문자열은 _l10n.gettext_라는 템플릿에서 가져옵니다. 이 템플릿은 `inittool` 이 PO 파일로부터 만든 XML 파일에서 문자열을 가져옵니다. 예를 들어 _causion_요소의 머리부분으로 사용하는 *경고* 라는 문자열을 가정해봅니다. 스타일시트에서는 문서의 언어에 대한 문자열의 번역한 값을 가져오기 위해 _l10n.gettext_를 호출할 것입니다. l10n.xml 파일은 다음과 같은 목록을 가지게 됩니다.

    <msgset xmlns=""http://www.gnome.org/~shaunm/gnome-doc-utils/l10n">
        <msgid>Caution</msgid>
        <msg>Caution</msg>
        <msg xml:lang="ar">إنتباه</msg>
        <msg xml:lang="bg">Внимание</msg>
        <msg xml:lang="ca">Compte</msg>
        <msg xml:lang="cs">Upozornění</msg>
        <msg xml:lang="da">Forsigtig</msg>
        <msg xml:lang="de">Achtung</msg>
        <msg xml:lang="el">Προσοχή</msg>
        <msg xml:lang="en_CA">Caution</msg>
        <msg xml:lang="en_GB">Caution</msg>
        <msg xml:lang="es">Precaución</msg>
        <msg xml:lang="et">Ettevaatust</msg>
        <msg xml:lang="fi">Varoitus</msg>
        <msg xml:lang="fr">Attention</msg>
        <msg xml:lang="gu">સાવધાન</msg>
        <msg xml:lang="hi">चेतावनी</msg>
        <msg xml:lang="hu">Figyelem</msg>
        <msg xml:lang="id">Perhatian</msg>
        <msg xml:lang="it">Attenzione</msg>
        <msg xml:lang="ja">注意</msg>
        <msg xml:lang="ko">주의</msg>
        <msg xml:lang="lt">Įspėjimas</msg>
        <msg xml:lang="nb">Advarsel</msg>
        <msg xml:lang="ne">सावधानी</msg>
        <msg xml:lang="nl">Let op</msg>
        <msg xml:lang="no">Advarsel</msg>
        <msg xml:lang="pa">ਸਾਵਧਾਨ</msg>
        <msg xml:lang="pt"Cuidado</msg>>
        <msg xml:lang="pt_BR">Cuidado</msg>
        <msg xml:lang="ro">Atenţie</msg>
        <msg xml:lang="sk">Výstraha</msg>
        <msg xml:lang="sq">Kujdes</msg>
        <msg xml:lang="sr">Пажња</msg>
        <msg xml:lang="sr@Latn">Pažnja</msg>
        <msg xml:lang="sv">Varning</msg>
        <msg xml:lang="tr">Uyarı</msg>
        <msg xml:lang="uk">Застереження</msg>
        <msg xml:lang="vi">Cảnh báo</msg>
        <msg xml:lang="wa">Adviertance</msg>
        <msg xml:lang="zh_CN">小心</msg>
        <msg xml:lang="zh_TW">注意</msg>
    </msgset>

그러나 번역자들은 단지 PO 파일로만 작업합니다. 이러한 문자열들을 위해 PO파일을 사용하는 것은 다른 단순한 문자열 번역과 다르지 않습니다. 위 문자열에 대한 _sr_로캘에 있는 PO 목록은 아래와 같은 모습을 지니게 될 것입니다.

    #: ../xslt/gettext/l10n.xml.in.h:1347
    msgid "Caution"
    msgstr "Пажња"

### 서수 표현 ###
대부분의 경우 정적 문자열은 내용을 알맞게 지역화 하기에는 부족합니다. 이런 경우에 스타일시트에서는 구조화된 XML 단편 요소에서 이들 문자열을 대체하는 방식으로 대체 문자열을 허용합니다. 대체 문자열은 두가지 방법으로 사용하는데, 서수 양식의 제공은 언어의 서수 규칙을 따르며, 대체 양식의 제공은 지정한 역할을 기반으로 합니다. 이 섹션에서는 서수 표현을 설명합니다. 역할의 내용에 대해서는 [역할](#역할) 부분을 참조하세요

서수 양식은 다른 프로그램에서와 같이 유사하게 다룹니다. 규칙은 서수 인덱스로 숫자를 변환하는 동작을 제공하며 번역은 제각각의 인덱스에 대해 제공합니다. 불행하게도 이 정보를 XML로 인코딩 하는 표준 방법이 없어서 `inittool`의 XML 모드에 이런 기술적 방편이 없습니다. 따라서 번역자들은 XML 단편 요소에 번역 내용을 넣어야 합니다. 이 단편 요소는 l10n.xml 파일과 합쳐지며 스타일시트는 적당한 형태로 내용을 뽑아냅니다.

**l10n.xml** 파일의 예제 내용입니다.

	<msgset xmlns=""http://www.gnome.org/~shaunm/gnome-doc-utils/l10n">
		<msgid>Author</msgid>
	    <msg>
			<msgstr form='0'>Author</msgstr>
			<msgstr form='1'>Authors</msgstr>
		</msg>
		<msg xml:lang="sr">
			<msgstr form='0'>Аутор</msgstr>
			<msgstr form='1'>Аутори</msgstr>
			<msgstr form='2'>Аутори</msgstr>
		</msg>
	</msgset>

세르비아어는 제공한 번역 내용과 같이 세 가지 서수 양식이 있습니다. 각각의 내용들은 `msgstr` 요소에 위치하며 `form` 속성은 이들을 사용하는 서수 양식을 나타냅니다.

다시 말해, 번역자들은 단지 PO 파일에서 목록만을 볼 것입니다. 위 번역 물에 대한 PO 파일의 내용은 아래와 같이 보일 것입니다.

	#. Used as a header before a list of authors.
	#: ../xslt/gettext/l10n.xml.in.h:1310
	msgid ""
	"<msgstr form='0'>Author</msgstr> "
	"<msgstr form='1'>Authors</msgstr>"
	msgstr ""
	"<msgstr form='0'>Аутор</msgstr>\n"
	"<msgstr form='1'>Аутори</msgstr>\n"
	"<msgstr form='2'>Аутори</msgstr>"


`inittool`이 종종 공백문자를 대체할 때마다, PO 파일의 내용은 이 처럼 말끔하지 못한 모습으로 보일 것입니다. 번역 메시지 문자열을 만들 때 번역자들은 선택한 경우 _msgstr_ 요소 사이에 공백문자를 추가하거나 제거할지도 모릅니다. 이 추가 텍스트 내용은 `l10n.gettext`에서 무시합니다.

참고로 번역자들은 대체 번역하는 방식으로 `form` 속성없이 `msgstr`요소를 추가할 것입니다. 위와 같은 예제에서 마지막 두개의 `msgstr` 요소는 `form`속성 없이 단일 `msgstr` 요소 대체할 수 있었습니다. `l10n.gettext` 템플릿은 서수 양식이 0일 때마다 언제든지 첫번째 요소를 비교할 것이고, 그렇지 않은 경우에는 대체 요소와 비교할 것입니다.

서수 양식은 `l10n.plural.form` 템플릿을 사용하여 선택합니다. 이 템플릿은 인자처럼 많은 항목을 가지고 있으며 사용하기 위한 서수 양식의 숫자 인텍스를 지니고 있습니다. 현재 규칙은 PO 파일의 `Plural-Form` 항목에서 자동으로 추출할 수 없어서 이 기능을 계획중에 있습니다. 이 기능이 추가 되기 전까지는, 서수 규칙을 스타일 시트에 직접 코드로 넣어야 합니다. 번역자들은 스타일시트 번역을 시작할 무렵 관리자에게 알릴 필요가 있습니다.

### 역할 ###
대부분의 경우 문법적 역할과 같은 다양한 상태에 의존하는 요소를 어떻게 표현할까요. 이런 경우 스타일시트는 번역자들이 고정 문법으로부터 `role`속성으로 제각각 표시하여 다양한 번역체를 제공할 수 있게끔 합니다. 유효한 역할의 목록은 템플릿에 의존할 것이며 제각각의 문자열에 해당하는 역자 주에 주어져야 합니다. 그러나 수많은 일반적인 경우, 그리고 레이블과 교차 참고에 대해 부분적인 경우가 있습니다.

역할을 이용한 번역은 서수 양식을 사용한 번역과 유사합니다. 번역내용은 수많은 `msgstr` 요소를 지니고 있고 제각각에 대해 `role` 속성을 지니고 있습니다. 일치하는 역할이 존재하지 않을 경우 속성이 없는 `msgstr`요소를 기본적으로 제공합니다.

예를 들어 DocBook의 `citetitle` 은 출판물의 제목을 인용하는데 사용합니다. 출판물의 유형은 `class` 속성에 지정합니다. 대부분의 영문 출판물은 내용의 제목을 기울임체로 따옴표 안에 넣습니다. 다음 일부 내용은 내용의 제목을 인용하겠지만, 다른 인용 제목은 기울임체로 만들 것입니다.

	<msgstr role='article'>“<node/>”</msgstr>
	<msgstr><i><node/></i></msg:msgstr>

세르비아어 번역 팀은 내용의 제목은 따옴표로 감싸고 다른 부분은 기울임체로 하는 관례를 따릅니다. *sr.po* 의 내용은 다음과 같습니다.

	#: ../xslt/gettext/l10n.xml.in.h:304
	msgid ""
	"<msgid>citetitle.format</msgid> "
	"<msgstr role='article'>“<node/>”</msgstr> "
	"<msgstr><i><node/></i></msgstr>"
	msgstr ""
	"<msgstr role='article'>„<node/>“</msgstr>\n"
	"<msgstr><i><node/></i></msgstr>"

`msgstr` 요소 내부의 마크업 의미는 [형식 문자열](#형식%20문자열) 에서 설명할 것입니다. 이제 간단히 알아볼 내용은 여러 문자열을 `msgstr` 요소에 넣을 수 있다는 것입니다. 본래 문자열과 세르비아어 문자열의 유일한 다른점은 세르비아어에서는 기준선에 대해 정렬한 다른 열림 따옴표 문자를 사용한다는 것입니다.

또 알아두어야 할 것은 본래 번역에는 추가 `msgid` 요소가 있습니다. 이 요소는 합친 XML에서 중복됩니다. 이것은 영문의 형식과 잠재적으로 유사한 다른 문자열과 이 문자열을 구분하기 위한 것입니다. 중복 `msgid` 요소는 서수 양식과 역할 둘 다 사용하지 않을 경우에 가끔 사용하기도 합니다. 이런 경우 유일하게 번역가능한 문자열은 어떤 속성도 붙지 않고 `msgstr` 요소에 놓이게 됩니다.

### 형식 문자열 ###
특별한 형식 문자열을 사용하면 그놈 문서 스타일시트를 더 간단하게 번역할 수 있습니다. 이들 형식 문자열은 XML이 위치 인자를 넣어 사용하는 특별한 형식 토큰 보다는 이름이 붙은 인자를 사용한다는 점은 제외하고 C 프로그램에서 사용하는 형식 문자열의 원리와 유사합니다.

예로 DocBook은 인라인 인용을 표시하는데 사용하는  `quote` 요소를 제공합니다. 언어의 표현 관례에 의존하여 인라인 인용을 어떻게 표현할까요. US 영문에서는 "큰 반전 쉼표" 인용 부호 안에 표현합니다. (그러나) 세르비아에서는 보통 ,,기준선에 정렬한" 여는 따옴표를 함께 표현합니다. 이러한 형식 문자열에 대한 세르비아어 PO 파일의 내용은 다음과 같읍니다.

	#: ../xslt/gettext/l10n.xml.in.h:936
	msgid ""
	"<msgid>quote.format</msgid> "
	"<msgstr role='inner'>‘<node/>’</msgstr> "
	"<msgstr>“<node/>”</msgstr>"
	msgstr ""
	"<msgstr role='inner'>‘<node/>’</msgstr>\n"
	"<msgstr>„<node/>”</msgstr>"

다중 `msgstr` 요소는 역할 속성과 함께 제공됩니다. 이들은 내부 따옴표와 외부 따옴표를 구분하기 위해 사용합니다. 역할 속성은 [역할](#역할)에서 설명했습니다. `msgstr` 요소는 인라인 마크업을 포함합니다. 이 마크업은 추가 내용을 넣기 위해 사용합니다. 이 경우 *\<node\/\>* 요소만을 사용합니다. 이 요소는 처리한 인용 요소의 내용으로 대체합니다.

각각의 형식 문자열은 이름이 붙은 사용할 수 있는 많은 인자를 지니고 있습니다. 이 인자들은 문자열에 따른 번역자의 주석에 문서화해야 합니다. 참고로 기본 번역은 사용할 수 있는 모든 인자의 사용이 가능하지 않을지도 모릅니다. 

게다가 형식 문자열의 마커 요소에 대해서도 번역자들은 간단한 인라인 형식 마크업을 사용할지도 모릅니다. 어떤 내용일지라도 형식을 다루기 위한 제각각의 속성과 함께 `span` 요소로 감쌀 수 있습니다. 속성은 CSS 프로퍼티의 서브셋입니다. HTML 출력을 위해 해당하는 CSS로 바로 변환합니다. 사용가능한 속성의 목록은 다음과 같습니다.

*font-family*

    이 속성은 글꼴 모음 이름을 설정합니다. 정확산 글꼴을 설정하는 것은 일반적으로 
	바람직하지 않습니다. 이에 반해, 이를 통해서 일반 글꼴 모음 이름을 제공하는데
	사용합니다: serif, san-serif, cursive, fantasy, monospace

*font-style*

	이 속성은 텍스트를 기울일 때 사용할 수 있습니다.가능한 값은 italic, oblique,
	normal 입니다.

*font-variant*

	이 속성은 작은 글씨로 텍스트를 설정하는데 사용할 수 있습니다. 
	작은 글씨는 대문자를 작게 표기하면서 동시에 소문자를 출력합니다. 
	가능한 값은 small-caps와 normal 입니다.

*font-weight*
	
	이 속성은 글씨를 굵게 표시할때 사용할 수 있습니다. CSS는 보통 글자 굵기인 400과 
	굵은 글자 굵기인 700을 포함하여 100부터 900까지 어떤 숫자든 허용합니다. 게다가
	숫자값을 포함해서 bold, bolder, lighter, normal 같이 미리 정의한 값을 사용할
	수도 있습니다. 보통 bold와 normal 만 필요합니다.

*font-stretch*

	이 속성은 글꼴을 늘이거나 누를때 사용합니다. CSS는 얼마나 글꼴을 잡아 늘일지
	정확하게 정의하도록 하는 수많은 키워드를 허용합니다.
	실제로 보통 wider, narrower, normal을 사용합니다.

*font-size*

	이 속성은 글꼴의 크기를 설정합니다. CSS는 글꼴 크기와 관련된 키워드나 퍼센트값
	뿐만 아니라 숫자길이와 키워드도 사용하여 절대적인 글꼴 크기를 허용합니다.
	일반적으로 larger, smaller, normal 만 사용합니다. 아래에 설명한 big과 small 
	전통 요소를 사용하는 것이 좋습니다. 이들은 스타일시트 이곳저곳에서 사용하는
	크기 스케일을 준수하기 위해 정의되어 있습니다.

*text-decoration*

	이 속성은 텍스트의 다양한 효과를 설정할 수 있습니다. 허용하는 값은 none,
	underline, overline, ling-through, blink입니다. blink는 사용하지 마시기 바랍니다.

덧붙여 편의를 위해 추가 인라인 요소를 제공합니다. 이들 요소로 처리한 형식화는 `span` 요소를 사용하여 처리할 수 있습니다. 이들 요소를 사용하는 것은 일반적인 형식화 작업에 대해 더 쉽습니다.

*big*

	텍스트를 더 크게 만듭니다. 이는 font-size 사용보다 우선하는데, 스타일시트에서
	사용하는 크기 스케일을 사용하기 위해 이미 정의되었기 때문입니다.

*small*

	텍스트를 더 작게 만듭니다. 이는 font-size 사용보다 우선하는데, 스타일시트에서
	사용하는 크기 스케일을 사용하기 위해 이미 정의되었기 때문입니다.

*sub*

	아래 첨자로 텍스트를 표현합니다.

*sup*

	위 첨자로 텍스트를 표현합니다.

*b*

	글씨를 굵게 만듭니다. font-weight에 bold를 설정한 것과 동일합니다.

*i*

	글씨를 기울입니다. font-style에 italic을 설정한 것과 동일합니다.

*tt*

	monospace 텍스트로 만듭니다. font-family을 monospace로 설정한 것과 동일합니다.

*u*

	텍스트에 밑줄을 긋습니다. text-decoration을 underline으로 설정한 것과 동일합니다.

### 일반 형식화 지정자 유형 ###

스타일 시트에서 번역을 위해 표시하는 형식 문자열의 수많은 일반 형식들이 있습니다. DocBook은 많은 구조적 마크업과 많은 동일한 종류의 형식화 작업들을 각기 다른 요소들에 대해 수행해야 합니다. 예를 들어 챕터, 부록, 섹션은 유사한 형식을 지니고 있지만, 종종 제각각 구분되게 다룰 필요가 있습니다. 스타일시트는 DocBook의 모든 제각각의 요소에 대해 드러날 수 없습니다. 다만 문서 표현 시점에서만은 구분을 짓도록 합니다.

이 섹션은 몇 가지 번역자 여러분들이 파악할 문자열의 많은 일반적인 유형에 대해 간략하게 안내할 것입니다. 동일한 유형의 문자열은 일반적으로 동일한 형식 인자와 동일한 역할 셋을 지니고 있을 것입니다.

