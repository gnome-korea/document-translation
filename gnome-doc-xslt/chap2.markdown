## 스타일 시트 사용하기 ##

스타일시트를 사용하려면 xsltproc 프로그램에 익숙해야 합니다. 첫 인자는 db2html.xsl 스타일 시트의 위치를 나타냅니다. 두번째 인자는 HTML을 생성하기 위한 최상위 docbook파일을 나타냅니다

### DocBook파일에서 HTML 생성하기 ###

    $ xsltproc /usr/share/xml/gnome/xslt/docbook/html/db2html.xsl <docbook file>

xsltproc과 libxslt라이브러리에 대한 더 자세한 내용은 [http://xmlsoft.org](http://xmlsoft.org)를 참조하시기 바랍니다.

**XInclude 처리**

여러분의 문서에 다른 파일을 포함하기 위해 [Xinclude](http://www.w3.org/TR/xinclude/)를 사용하려 한다면, db2html.xsl 스타일 시트와 함께 이 DocBook파일을 처리하기 전에 완전한 DocBook을 생성하기 위해 *--xinclude* 인자를 사용해야 합니다.