# dom-study
Document Object Model Study

# 1. 노드 개요

## 1-1 DOM은 노드 개체들의 계층화된 트리이다.

---

## 1-2 노드 개체 유형

---
1. DOCUMENT_NODE (window.document)
2. ELEMENT_NODE (\<div>, \<p>, \<body>, ...)
3. ATTRIBUTE_NODE (class="funEdges")
4. TEXT_NODE (줄바꿈과 공백을 포함한 HTML 문서 내의 텍스트 문자)
5. DOCUMENT_FRAGMENT_NODE (document.createDocumentFragment())
6. DOCUMENT_TYPE_NODE (\<!DOCTYPE html>)
...
   

## 1-3 Node 개체로부터 상속받은 하위 노드 개체

---
DOM 트리의 노드개체는 Node로 부터 속성과 메서드를 상속받는다.

### 1-4 노드를 다루기 위한 속성 및 메서드

---
* Node 속성
    * childNodes
    * firstChild
    * lastChild
    * nextSibling
    * nodeName
    * nodeType
    * nodeValue
    * parentNode
    * previousSibling ..
* Node 메서드
    * appendChild()
    * cloneNode()
    * compareDocumentPosition()
    * contains()
    * hasChildNodes()
    * insertBefore()
    * isEqualNode()
    * removeChild()
    * replaceChild() ..
* Document 메서드
    * document.createElement()
    * document.createTextNode() ..
* HTML *Element 속성
    * innerHTML
    * outerHTML
    * textContent
    * innerText
    * outerText
    * firstElementChild
    * lastElementChild
    * nextElementChild
    * previousElementChild
    * children ..
* HTML element 메서드
    * insertAdjacentHTML() ..
  
## 1-5 노드의 유형과 이름 식별하기

---

모든 노드는 Node로부터 상속받은 nodeType, nodeName 속성을 가진다

## 1-6 노드 값 가져오기

---

nodeValue속성은 Text와 Comment 노드를 제외한 대부분 노드에서 null값을 반환. <br>
Text와 Comment노드에서 실제 텍스트 문자열을 추출하기 위해 사용. <br>
nodeValue를 이용해 텍스트 노드의 새로운 문자열을 지정할 수 있다.

## 1-7 JavaScript 메서드를 사용해서 Element 및 Text 노드를 생성하기

---

`createElement()` `createTextNode()` 들을 이용해 `elementNode`와 `textNode`를 생성할 수 있다.

## 1-8 JavaScript 문자열을 사용하여 DOM에 Element 및 Text 노드를 생성 및 추가하기

---

`innerHTML` `outerHTML` `textContent` `insertAdjacentHTML()` 를 이용해 문자열을 사용하여 DOM에 노드를 생성 할 수 있다.

* textContent vs innerText
  > textContent는 숨겨진 요소, `<script>`, `<style>` 요소를 포함한 모든 요소의 컨텐츠를 가져옴. <br>
  > innerText는 rendered된 내용만 가져옴 <br>
  > innerText는 layout정보를 알아야하기 때문에 비용이 좀 더 비쌈.
  > 

## 1-9 DOM 트리의 일부를 JavaScript 문자열로 추출하기

---

`innerText` `outerText` `textContent`를 사용하여 문자열을 추출할 수 있다.