# vscode\_html\_languageservice

## Utils

```Javascript
export function dirname(path: string): string
```
path에서 `'/'` 이나 `'\\'`의 인덱스를 검색 후 폴더의 **상위 폴더 경로**를 반환함  
(~path.lastIndexOf('/') || ~path.lastIndexOf('\\'): ~ = 결과 비트 NOT(반전)연산자)  
[~ 연산자 도움 링크 참조](https://www.joezimjs.com/javascript/javascript-tilde-real-no-mystery/)  


```Javascript
export function basename(path: string): string
```
dirname과 같은 방식으로 현재 폴더 이름 반환


```Javascript
export function extname(path: string): string
```
파일의 경로를 주면 위의 `basename`을 이용해 파일의 확장자 반환  
(`~path.lastIndexOf('.')` 함수로 확장자 위치 확인 =>  
존재시 `path.substring(~~path.lastIndexOf('.'))`, 존재하지 않을 경우 `''` 반환)


```Javascript
export function findMatchingTagPosition( document: TextDocument, position: Position,htmlDocument: HTMLDocument): Position | null
```
주어진 위치의 오프셋을 가져와 노드를 찾고,  
**열리는 태그**의 안에 오프셋이 있을 경우 *닫는 태그의 위치*를 계산  
if문: (node.start + '<'.length <= offset <= node.start + '<'.length + node.tag.length)  
node.start + '<'.length : 열리는 태그 안 (`<[v]offset>`)  
node.start + '<'.length + node.tag.length : 열리는 태그 뒤 (`<offset[v]>`)  

닫는 태그 위치: `offset - '<'.length - node.start + node.endTagStart + '</'.length;`  

**닫히는 태그**의 안에 오프셋이 있을 경우 위를 변형하여 *열리는 태그의 위치*를 계산
