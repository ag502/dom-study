# dom-study

Document Object Model Study

# 1. 노드 개요

## 1-1 DOM은 노드 개체들의 계층화된 트리이다.

## 1-2 노드 개체 유형

1. DOCUMENT_NODE (window.document)
2. ELEMENT_NODE (\<div>, \<p>, \<body>, ...)
3. ATTRIBUTE_NODE (class="funEdges")
4. TEXT_NODE (줄바꿈과 공백을 포함한 HTML 문서 내의 텍스트 문자)
5. DOCUMENT_FRAGMENT_NODE (document.createDocumentFragment())
6. DOCUMENT_TYPE_NODE (\<!DOCTYPE html>)
   ...

## 1-3 Node 개체로부터 상속받은 하위 노드 개체

DOM 트리의 노드개체는 Node로 부터 속성과 메서드를 상속받는다.

### 1-4 노드를 다루기 위한 속성 및 메서드

- Node 속성
  - childNodes
  - firstChild
  - lastChild
  - nextSibling
  - nodeName
  - nodeType
  - nodeValue
  - parentNode
  - previousSibling ..
- Node 메서드
  - appendChild()
  - cloneNode()
  - compareDocumentPosition()
  - contains()
  - hasChildNodes()
  - insertBefore()
  - isEqualNode()
  - removeChild()
  - replaceChild() ..
- Document 메서드
  - document.createElement()
  - document.createTextNode() ..
- HTML \*Element 속성
  - innerHTML
  - outerHTML
  - textContent
  - innerText
  - outerText
  - firstElementChild
  - lastElementChild
  - nextElementChild
  - previousElementChild
  - children ..
- HTML element 메서드
  - insertAdjacentHTML() ..

## 1-5 노드의 유형과 이름 식별하기

모든 노드는 Node로부터 상속받은 nodeType, nodeName 속성을 가진다

## 1-6 노드 값 가져오기

nodeValue속성은 Text와 Comment 노드를 제외한 대부분 노드에서 null값을 반환. <br>
Text와 Comment노드에서 실제 텍스트 문자열을 추출하기 위해 사용. <br>
nodeValue를 이용해 텍스트 노드의 새로운 문자열을 지정할 수 있다.

## 1-7 JavaScript 메서드를 사용해서 Element 및 Text 노드를 생성하기

`createElement()` `createTextNode()` 들을 이용해 `elementNode`와 `textNode`를 생성할 수 있다.

## 1-8 JavaScript 문자열을 사용하여 DOM에 Element 및 Text 노드를 생성 및 추가하기

`innerHTML` `outerHTML` `textContent` `insertAdjacentHTML()` 를 이용해 문자열을 사용하여 DOM에 노드를 생성 할 수 있다.

- textContent vs innerText
  > textContent는 숨겨진 요소, `<script>`, `<style>` 요소를 포함한 모든 요소의 컨텐츠를 가져옴. <br>
  > innerText는 rendered된 내용만 가져옴 <br>
  > innerText는 layout정보를 알아야하기 때문에 비용이 좀 더 비쌈.

## 1-9 DOM 트리의 일부를 JavaScript 문자열로 추출하기

`innerText` `outerText` `textContent`를 사용하여 문자열을 추출할 수 있다.

## 1-10 appendChild(), insertBefore()를 사용하여 노드 개체를 DOM에 추가하기

> 이미 기존의 노드를 참조할 경우 새로운 위치로 이동(삭제할 필요 없음)

1. `appendChild()`: 선택된 노드 개체의 마지막 자식으로 노드를 삽입
2. `insertBefore()`: 지정된 노드 이전에 새로운 노드 삽입.

## 1-11 removeChild(), replaceChild()를 사용하여 노드를 제거하거나 바꾸기

- 제거, 변경
  - 단계
    1. 삭제(변경) 하고자 하는 노드 참조
    2. 삭제(변경) 하고자 하는 노드의 부모 노드 참조
    3. 부모 노드에서 삭제(변경)할 노드에 대한 참조를 함수에 전달

## 1-12 cloneNode()를 사용하여 노드를 복제하기

자식 노드들도 모두 복제하고자 하면 true를 인자로 전달

> `addEventListener()`나 `node.onclick`으로 추가된 것은 복제되지 않는다.

## 1-13 노드 컬렉션(NodeList와 HTMLCollection)에 대한 이해

트리에서 노드 그룹을 선택하거나 사전에 정의된 노드 집합에 접근하려면 해당 노드들이 NodeList나 HTMLCollection 내에 있어야 한다.

> 컬렉션은 라이브 상태 혹은 정적일 수 있다.
> 노드들은 트리내의 순서에 따라 정렬.
> 컬렉션은 요소 개수를 나타내는 length 속성을 가진다.
> 컬렉션은 진짜 배열이 아닌 유사 배열이다.

## 1-14 직계 자식 노드 전부에 대한 리스트/컬렉션 얻기

`childNodes`속성을 사용하면 직계 자식 노드에 대해 배열 형태의 리스트(NodeList)가 나온다.

## 1-15 NodeList나 HTMLCollection을 JavaScrip 배열로 변환

`NodeList`와 `HTMLCollection`은 배열이 아니므로 배열과 관련된 함수 사용 불가

> Array.from(유사 배열 객체)를 사용하여 변환

## 1-16 DOM 내의 노드 탐색

- `parentNode`, `firstChild`, `lastChild`, `nextSilbing`, `previousSibling`, `childNodes`
  > textNode, commentNode 포함 모든 노드 요소들을 반환
- `parentElement`, `firstElementChild`, `lastElementChild`, `nextElementSibling`, `previousElementSibling`, `children`
  > elementNode들만 반환

## 3-1 HTML \* Element 개체 개요

DOM에서 각 element가 고유한 JavaScript 인터페이스/생성자를 통해 만들어 진다.

## 3-3 Element 생성

`createElement()`를 이용해 동적으로 DOM에 `ElementNode`를 추가할 수 있다.

## 3-4 Element 태그 이름 얻기

`tagName`속성을 사용하여 element이름에 접근 가능 (node의 `nodeName`과 동일한 결과 반환)

## 3-5 Element의 Attribute 및 값에 대한 리스트/컬렉션 얻기

attributes 속성을 사용하면, 현재 element에 정의된 attr 노드의 컬렉션을 얻을 수 있다(NamedNodeMap(attribute node 리스트)을 반환)

## 3-6 Element의 Attribute 값 획득, 설정, 제거

- 획득
  > `getAttribute()`
- 설정
  > `setAttribute()`
- 제거
  > `removeAttribute()`

## 3-7 Element가 특정 attribute을 가지고 있는지 판단하기

`hasAttribute()`를 이용하여 포함 여부 확인 가능(값이 정의되지 않은 attr라도 참 반환)

> Boolean attribute의 경우 boolean응답을 받을 수 있다. (`cheackbok`의 체크여부 확인)

## 3-8 Class Attribute 값 리스트 얻기

`classList` 속성을 이용하면 `className` 속성에서 반환되는 공백으로 구분된 문자열 값을 사용하는 것보다 훨씬 쉽게 class Attribute에 접근가능.

## 3-9 Class Attribute에 하위 값 추가 및 제거하기

`classList.add()` `classList.remove()`를 이용하여 class attribute를 간단히 편집할 수 있다.

## 3-10 Class attribute 값 토글

`classList.toggle()`를 이용해 class attribute를 토글 시킬 수 있다. (값이 있으면 제거, 없으면 추가)

## 3-11 Class attribute 값이 특정 값을 가지고 있는지 판별하기

`classList.contains()` 메서드를 사용하면 class attribute 값 포함여부 알 수 있다.

## 3-12 data-\* attribute를 가져오고 설정하기

element 노드의 `dataset` 속성은 element에서 data-\*로 시작하는 모든 attribute를 가진 개체를 제공한다.

> dataset은 data attribute들의 camelCase 버전을 가지고 있다. </br>
> data-foo-foo -> fooFoo

## 4-1 특정 Element 노드 선택하기

`getElementById()` `querySelector()`를 통해 단일 element를 선택할 수 있다.
> `querySelector()`는 element에도 정의가 되어 있다.

## 4-2 Element 노드 리스트 선택 및 생성하기

`querySelectorAll()`, `getElementsByClassName()`, `getElementsByTagName()`, `getElementsByName`, `childNodes`는 NodeList나 HTMLCollection을 반환
  * querySelectorAll
    > static한 node list 반환
  * getElementsByName, childNodes
    > live한 node list 반환
  * getElementsByTagName, getElementsByClassName
    > live한 HTML Collection 반환

## 4-3 직계 자식 Element 노드를 모두 선택하기

element 노드에서 `children` 속성을 사용하면, element 노드의 직계자손들의 HTML Collection을 얻을 수 있다.

## 4-4 컨텍스트 기반 Element 선택

`querySelector()`, `querySelectorAll()`, `getElementsByClassName()`, `getElementsByTagName()`는 element에도 정의 되어있다.
  > element노드에서 이 메서드를 호출하면, element 노드를 검색하고자 하는 특정 컨텍스트를 선택할 수 있다.

## 4-6 선택된 Element를 검증하기 위해 matches()를 사용하기

`matches()` 메서드를 사용하면 element가 selector 문자열에 들어맞는지를 판별할 수 있다.

## 6-1 style attribute(element 인라인 CSS 속성) 개요

모든 HTML element는 해당 element에 한정된 인라인 CSS 속성을 넣는 데 사용할 수 있는 style attribute를 가진다.
  > style 속성은 문자열이 아닌 CSSStyleDeclaration 개체를 반환하며, 인라인 스타일만 반영

## 6-2 개별 인라인 CSS 속성 가져오기, 설정, 제거

  1. style 속성에서 css 속성 직접지정
  2. style 속성에서 제공하는 `getPropertyValue()` `setProperty()` `removeProperty()`를 사용

## 6-3 모든 인라인 CSS 속성 가져오기, 설정, 제거

CSSStyleDeclaration 개체의 `cssText` 속성과 `getAttribute()` 및 `setAttribute()` 메서드를ㄹ 사용하면 style attribute의 전체값을 가져오고 설정 및 제거할 수 있다.

## 6-4 `getComputedStyle()`을 사용하여 element의 계산된 스타일(계층화된 것을 포함한 실제 스타일) 가져오기

element의 계층화된 CSS(인라인 스타일시트, 외부 스타일시트, 브라우저 스타일 시트...)를 가져오려면 `window.getComputedStyle()`을 이용해야 한다.

## 6-5 `class` 및 `id` attribute를 사용하여 element의 CSS속성을 적용 및 제거하기

인라인 스타일시트나, 외부 스타일시트에 정의된 스타일 규칙은 `class` 및 `id` attribute를 사용하여 element에 추가하거나 제거할 수 있다.

## 11-1 DOM 이벤트 개요

이벤트를 설정하는 하는 것은 `인라인 attribute 이벤트 핸들러`, `속성 이벤트 핸들러`, `addEventListener()` 메서드를 사용하여 수행할 수 있다.
  > `addEventListener()`만이 견고하고 조직화된 솔루션을 제공한다.
  
## 11-2 이벤트 흐름

이벤트 흐름은 캡처 단계(DOM 트리 줄기 -> 가지), 버블링 단계(DOM 트리 가지 -> 줄기), 혹은 양쪽 모두로 발생하도록 프로그래밍 할 수 있다.