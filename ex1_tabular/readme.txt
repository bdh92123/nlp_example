#### 구현환경 ####
OS : ubuntu 18.0.4 (using docker)
Arch : 64 bit
IDE : Jupyter lab


#### 구현언어 ####
Python 3.7.2


#### 사용라이브러리 ####
graphviz : TRIE 사전 시각화를 위해 사용


#### 실행방법 ####
POS_tagger.zip내 tabular.py를 grammer.txt와 같은 폴더에 두고 다음 명령어로 실행
python tabular.py

실행하면 준비된 예문 및 추가 예문이 분석되어 출력됨.
또 다른 예문을 분석하고 싶으면 다음과 같이 파라메터를 주고 실행

python tabular.py "나는 먹었다."

※ 참고사항
TRIE 시각화 없이 형태소 분석만 하도록 tabular.py의 314번라인 trie.render("trie") 가 주석처리 되어있음.
만약 grammer.txt 수정 후 TRIE 시각화도 필요한 경우 해당 라인 주석 풀고 아래방법대로 graphviz 별도설치 필요.
시각화 결과는 trie.gv.pdf로 저장됨.

※ graphviz 설치방법
1. 홈페이지(https://graphviz.gitlab.io/download/) 에서 OS에 맞는 바이너리 설치
2. 설치된 폴더 하위의 bin 폴더를 PATH 환경변수에 추가
3. tabular.py있는 폴더에서 pip install -r requirements.txt

※ 소스코드 및 grammer.txt 파일인코딩은 모두 UTF-8을 따름


####  실행결과 ####
dictionary_TRIE.pdf (준비된 5개 예문에 대한 사전 시각화파일)
tabular.html (준비된 5개 예문 + 추가 예문 tabular parsing 결과)
두 파일 참고해주세요.

형태소 분석 결과 출력되는 방식은 어절당 한 행으로 형태소 분석 결과가 출력됨.
또한 다음과 같은 형태의 행은 좌우접속정보에 따라 여러가지 경우로 해석될 수 있음을 표현한 것임
[사람/보통명사+이/주격조사, 사람/보통명사+이/긍정지정사]

즉
사람/보통명사+이/주격조사
사람/보통명사+이/긍정지정사
모두 된다는 뜻.











