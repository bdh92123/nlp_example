#### 구현환경 ####
OS : ubuntu 18.0.4 (using docker)
Arch : 64 bit
IDE : Jupyter lab


#### 구현언어 ####
Python 3.7.2


#### 사용라이브러리 ####
없음


#### 실행방법 ####
cky_parser.py를 grammar.txt 및 input.txt와 같은 폴더에 두고 다음 명령어로 실행
python cky_parser.py

실행하면 input.txt에 준비된 예문이 CKY Parsing 되어 output.txt에는 Parse Tree 목록이, used_grammar.txt에는 분석중 사용된 구문문법 인덱스 로그가 저장된다.


####  실행결과 ####
used_grammar.txt: 문장별로 분석에 사용된 구구조 문법 인덱스 로그
(Symbol, [(Left Node Index, Right Node Index),(..)]) 포맷으로 Shared-Packed Tree의 생성 과정이 저장됨. 
말단 노드의 경우 Index 번호 대신 단어가 기록.

output.txt: 문장별로 분석 완료된 Parse Tree의 목록
(Symbol, (Left Node) (Right Node)) 포맷으로 저장됨.

cky_parser.html: 소스코드, 문장별로 사용된 구구조문법 인덱스 로그, 분석완료된 Parse Tree 목록, CKY Parse Table이 모두 기록되어 있음


#### 참고사항 ####
1. used_grammar.txt및 output.txt에 출력되는 내용은 콘솔에서도 동일하게 출력된다.

2. 257라인에 trees = parser.parse(line, "used_grammar.txt", True) 중 마지막 파라메터를 True로 주면 콘솔 및 table.txt에 각 문장에 대한 CKY Parse Table이 출력된다. 

3. used_grammar.txt에서 "# packed !" 가 뒤쪽에 붙어있는 줄의 경우, 기존에 이미 Parsing 되어 Table에 노드가 추가 되었으나 해당 노드의 Sub Parse Tree가 새로 등장한 경우를 나타낸다. (즉 Packing되는 시점) 
따라서 해당 줄의 인덱스는 기존에 등장했던 인덱스 번호와 동일하다. 

4. 소스코드 및 입출력 텍스트파일 인코딩은 모두 UTF-8을 따르며, 출력파일의 개행문자는 Unix-style '\n' 를 따른다. 
따라서 출력 텍스트파일은 윈도우 환경에서 메모장이아닌, 워드패드 또는 기타 텍스트에디터(Sublime text 등)로 확인필요!

5. 소스코드에 주석으로 코드설명이 명시되어있음

