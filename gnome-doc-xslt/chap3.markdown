## 인자 지정하기 ##

HTML을 생성하기 위해 사용자 임의로 스타일시트에서 사용할 수 있는 수많은 인자들이 있습니다. 완전한 목록은 다음 섹션에서 제공하지만, 일반적으로 사용하는 일부 인자에 대해 이 섹션에서 소개하도록 하겠습니다.

스타일시트에 인자를 지정하려면 xsltproc 프로그램의 `--stringpagam` 옵션을 사용합니다.

*db.chunk.chunk_top*

최상위 요소( _\<article\>_  또는 _\<book\>_ )를 index.xhtml 파일로 모아두려면 이 인자를 **1**로 설정합니다

*db.chunk.max_depth* 

`db.chunk.chunks`인자에 지정한 모아둔 요소의 최대 깊이를 지정합니다.

*db.chunk.extension* 

여러분이 모아놓은 출력 파일에 대해 원하는 _확장자_ 를 지정합니다.

**스타일시트 지정 예제** 

	$ xsltproc \ 
	--stringparam db.chunk.chunk_top 1 \ 
	--stringparam db.chunk.max_Depth 1 \ 
	--stringparam db.chunk.extension '.html' \ 
	/usr/share/xml/gnome/xslt/docbook/html/db2html.xsl \ 
	<docbook 파일 경로> 


*스타일시트 지정 예제* 에서는 최상위 요소에 내용을 모아둘 것이며, 모아두는 내용의 최대 깊이는 1이고, 제목 페이지로 모아둘 것입니다.

***

**1**

모아둔 것은 요소에 대해 각각 나누어 생성한 출력 파일을 참조합니다. 예를 들어 _<sec1>_ 요소가 하나의 문서에 (하위 섹션 없이) 세 개가 존재한다고 할 때 각각의 요소에 대해 세 개의 파일을 생성할 것입니다. 파일의 이름은 요소의 _id_ 속성과 같을 것입니다.
