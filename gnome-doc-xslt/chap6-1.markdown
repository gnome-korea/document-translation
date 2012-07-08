### DocBook 모음기능 ###
#### 인자 ####
[db.chunk.chunks](#dbchunkchunks)
  
    모아야 할 요소들의 공백으로 구분한 이름 목록입니다.
    
[db.chunk.chunk\_top](#dbchunkchunk%5Ftop)

    상위 모음을 모아두기 방법으로 출력할지에 대한 여부입니다.

[db.chunk.max\_depth](#dbchunkmax_depth)

	모아둔 섹션의 최대 깊이입니다.

[db.chunk.basename](#dbchunkbasename)

	확장자를 제외한 출력 파일의 기본 파일이름입니다.

[db.chunk.extension](#dbchunkextension)

	새 출력 문서의 기본 파일 확장자입니다.

[db.chunk.info\_chunk](#dbchunkinfo_chunk)

	제목 페이지에 대해 모음을 만들지에 대한 여부입니다.

[db.chunk.info\_filename](#dbchunkinfo_filename)

	제목 페이지에 대한 기본 파일이름입니다.

[db.chunk.doctype\_public](#dbchunkdoctype_public)

	출력 파일에 대한 public DOCTYPE 입니다.

[db.chunk.doctype\_system](#dbchunkdoctype_system)

	출력 파일에 대한 system DOCTYPE 입니다.

#### 모드 ####

[db.chunk.info.content\_mode](#dbchunoinfocontent_mode)

	제목 페이지의 내용을 표현합니다.

[db.chunk.content.mode](#dbchunkcontentmode)

	내용의 전체 모음을 표현합니다.

#### 템플릿 ####

[db.chunk](#dbchunk)

	출력할 새 페이지를 만듭니다.

[db.chunk.content](#dbchunkcontent)

	출력할 새 페이지의 내용을 만듭니다.

[db.chunk.children](#dbchunkchildren)

	요소의 자식에 대한 새 페이지를 만듭니다.

[db.chunk.depth-in-chunk](#dbchunkdepth-in-chunk)

	모음을 포함하는 요소의 깊이를 정합니다.

[db.chunk.depth-of-chunk](#dbchunkdepth-of-chunk)

	문서에서 모음이 들어갈 깊이를 정합니다.

[db.chunk.chunk-id](#dbchunkchunk-id)

	요소를 포함한 모음의 ID를 정합니다.

[db.chunk.chunk-id.axis](#dbchunkchunk-idaxis)

	지정한 축에 따른 첫 모음의 ID를 정합니다.

#### db.chunk.chunks ####

`db.chunk.chunks` - 모아야 할 요소들의 공백으로 구분한 이름 목록입니다.

#### db.chunk.chunk\_top ####

`db.chunk.chunk_top` - 상위 모음을 모아두기 방법으로 출력할지에 대한 여부입니다.

#### db.chunk.max\_depth ####

`db.chunk.max_depth` - 모아둔 섹션의 최대 깊이입니다.

#### db.chunk.basename ####

`db.chunk.basename` - 확장자를 제외한 출력 파일의 기본 파일이름입니다.

#### db.chunk.extension ####

`db.chunk.extension` - 새 출력 문서의 기본 파일 확장자입니다.

#### db.chunk.info\_chunk ####

`db.chunk.info_chunk` - 제목 페이지에 대해 모음을 만들지에 대한 여부입니다.

#### db.chunk.info\_filename ####

`db.chunk.info_filename` - 제목 페이지에 대한 기본 파일이름입니다.

#### db.chunk.doctype\_public ####

`db.chunk.doctype_public` - 출력 파일에 대한 public DOCTYPE 입니다.

#### db.chunk.doctype\_system ####

`db.chunk.doctype_system` - 출력 파일에 대한 system DOCTYPE 입니다.

#### db.chunk.info.content.mode ####

`db.chunk.info.content.mode` - 제목 페이지의 내용을 표현합니다.

##### 인자 #####
`depth_in_chunk` - 모음을 포함하는 요소의 깊이입니다.
`depth_of_chunk` - 문서의 모음이 들어갈 깊이입니다.

##### 설명 #####
이 모드를 포함할 때 출력 페이지에 대한 각 요소는 상위레벨 마크업을 출력해야 합니다.

#### db.chunk.content.mode ####

`db.chunk.content.mode` - 내용의 전체 모음을 표현합니다.

##### 인자 #####
`depth_in_chunk` - 모음을 포함하는 요소의 깊이입니다.
`depth_of_chunk` - 문서의 모음이 들어갈 깊이입니다.

##### 설명 #####
이 모드를 포함할 때 출력 페이지에 대한 각 요소는 상위레벨 마크업을 출력해야 합니다.

#### db.chunk ####

`db.chunk` - 출력할 새 페이지를 만듭니다.

##### 인자 #####
`node` - 출력 페이지의 원본 요소입니다.
`template` - 페이지를 만들 때 호출할 템플릿 이름입니다.
`href` - 출력 페이지에 대한 파일 이름입니다.
`depth_of_chunk` - 문서에 있는 요소 모음의 깊이입니다.

##### 설명 #####
[db.chunk](#dbchunk)템플릿은 _exsl:document_ 확장 요소를 사용하여 새 출력 문서를 만듭니다. 이 템플릿은 문서의 내용을 만들기 위해 모든 인자 값을 전달하면서 [db.chunk.content](#dbchunkcontent)를 호출합니다. 내용 생성 코드를 복제하지 않고 또 다른 요소 모음 방법을 사용할 수 있게 해줍니다.

#### db.chunk.content ####

`db.chunk.content` - 출력할 새 페이지의 내용을 만듭니다.

##### 인자 #####
`node` - 출력 페이지의 원본 요소입니다.
`template` - 페이지를 만들 떄 호출할 템플릿 이름입니다.
`depth_of_chunk` - 문서에 있는 요소 모음의 깊이입니다.

##### 설명 #####
[db.chunk.content](#dbchunkcontent) 템플릿은 출력 페이지의 실제 내용을 만듭니다. 보통 [db.chunk](#dbchunk)에 의해서만 호출합니다.

이 템플릿은 이 템플릿을 호출한 주체에 적당한 값을 가진 `depth_in_chunk`와 `depth_of_chunk` 인자를 항상 전달할 것입니다.

#### db.chunk.children ####

`db.chunk.children` - 요소의 자식에 대한 새 페이지를 만듭니다.

##### 인자 #####
`node` - 하위요소를 모을 상위요소
`depth_of_chunk` - 문서의 `node` 깊이

#### db.chunk.depth-in-chunk ####

`db.chunk.depth-in-chunk` - 모음을 포함하는 요소의 깊이를 정합니다.

##### 인자 #####
`node` - 지정한 깊이로 정할 요소

#### db.chunk.depth-of-chunk ####

`db.chunk.depth-of-chunk` - 문서에서 모음이 들어갈 깊이를 정합니다.

##### 인자 #####
`node` - 지정한 깊이로 정할 요소

#### db.chunk.chunk-id ####

`db.chunk.chunk-id` - 요소를 포함한 모음의 ID를 정합니다.

##### 인자 #####
`id` - 모음 ID를 결정할 요소의 ID
`node` - 모음 ID를 결정할 요소
`depth_of_chunk` - 모음을 포함하는 `node`의 깊이

#### db.chunk.chunk-id.axis ####

`db.chunk.chunk-id.axis` - 지정한 축에 따른 첫 모음의 ID를 정합니다.

##### 인자 #####
`node` - 기본 요소
`node` - 첫번째 모음을 찾을 축
`depth_in_chunk` - 모음을 포함하는 `node`의 깊이
`depth_of_chunk` - 문서에 있는 모음의 깊이
