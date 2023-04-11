필요한 것들을 적어두는 공간

matplotlib에서 한글 표시하기

참고 사이트
http://corazzon.github.io/matplotlib_font_setting

MacOS
파일 위치
/Users/sj/miniconda3/lib/python3.7/site-packages/matplotlib/mpl-data/matplotlibrc

font name

font.family:  Apple SD Gothic Neo

마이너스 부호 표시

axes.unicode_minus: False

~~~
import matplotlib as mpl
import matplotlib.pyplot as plt
import matplotlib.font_manager as fm
import numpy as np
data = np.random.randint(-100,100,50).cumsum()

plt.plot(range(50), data, 'r')
plt.title('시간별 가격 추이')

font_list = fm.findSystemFonts(fontpaths=None, fontext='ttf')
f = [f.name for f in fm.fontManager.ttflist]
[(f.name,f.fname) for f in fm.fontManager.ttflist if 'Apple' in f.name]
~~~




git 사용방법

참고 사이트 https://rogerdudler.github.io/git-guide/index.ko.html


git init

git clone /로컬/저장소/경로

git add <파일 이름>

git commit -m "이번 확정본에 대한 설명"

git push origin master

git pull





SDL 사용방법
Microsoft Visual Studio Community 2022 기준
1. SDL 다운로드 (https://github.com/libsdl-org/SDL/releases/tag/release-2.26.5)
   SDL2-devel-2.26.5-VC.zip  (VScode 사용시 SDL2-devel-2.26.5-mingw.zip)
   적당한 위치에 압축 해제 (프로젝트 폴더와 같을 필요 없음)
2. Visual Studio에서 C++ 빈 프로젝트 생성
3. 소스 파일에 cpp 파일 생성
4. 프로젝트 속성
  - VC++ 디렉터리
    . 포함 디렉터리 : ~\SDL2-devel-2.26.5-VC\SDL2-2.26.5\include
    . 라이브러리 디렉터리 : ~\SDL2-devel-2.26.5-VC\SDL2-2.26.5\lib\x64 (필요에 따라 x86 선택)
  - 링커
    . 입력 > 추가 종속성 : SDL2.lib;SDL2main.lib;
      (또는 code 상단에 아래 두줄 입력)
        #pragma comment(lib, "SDL2.lib")
        #pragma comment(lib, "SDL2main.lib")
    . 시스템 > 하위 시스템 : 창(/SUBSYSTEM:WINDOWS)   <- 프로그램 실행시 콘솔 창 안나오게 하기 위함
5. 출력 파일 위치에 SDL2.dll 파일 넣기


테스트 코드
https://lazyfoo.net/tutorials/SDL/01_hello_SDL/index2.php





