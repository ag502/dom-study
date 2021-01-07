# dom-study
Document Object Model Study

#1. 노드 개요

##1-1 DOM은 노드 개체들의 계층화된 트리이다.

---

##1-2 노드 개체 유형

---
1. DOCUMENT_NODE (window.document)
2. ELEMENT_NODE (\<div>, \<p>, \<body>, ...)
3. ATTRIBUTE_NODE (class="funEdges")
4. TEXT_NODE (줄바꿈과 공백을 포함한 HTML 문서 내의 텍스트 문자)
5. DOCUMENT_FRAGMENT_NODE (document.createDocumentFragment())
6. DOCUMENT_TYPE_NODE (\<!DOCTYPE html>)
...
   

##1-3 Node 개체로부터 상속받은 하위 노드 개체

---
DOM 트리의 노드개체는 Node로 부터 속성과 메서드를 상속받는다.

###1-4 노드를 다루기 위한 속성 및 메서드

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