# SDL 사용방법

## Microsoft Visual Studio Community 2022 기준
1. SDL Release 다운로드 (https://github.com/libsdl-org/SDL/releases)  
   SDL2-devel-2.26.5-VC.zip  
   (VScode 사용시 SDL2-devel-2.26.5-mingw.zip)  
   적당한 위치에 압축 해제 (프로젝트 폴더와 같을 필요 없음)
2. Visual Studio에서 C++ 빈 프로젝트 생성
3. 소스 파일에 cpp 파일 생성
4. 프로젝트 속성
  - VC++ 디렉터리  
    . 포함 디렉터리 : ~\SDL2-devel-2.26.5-VC\SDL2-2.26.5\include  
    . 라이브러리 디렉터리 : ~\SDL2-devel-2.26.5-VC\SDL2-2.26.5\lib\x64  
  - 링커  
    . 입력 > 추가 종속성 : SDL2.lib;SDL2main.lib;  
      (또는 code 상단에 아래 두줄 입력)  
      ```C
      #pragma comment(lib, "SDL2.lib")  
      #pragma comment(lib, "SDL2main.lib")  
      ```
    . 프로그램 실행시 콘솔 창 안나오게 하려면,  
      설정 > 시스템 > 하위 시스템 : 창(/SUBSYSTEM:WINDOWS)  
     
5. 출력 파일 위치에 SDL2.dll 파일 넣기


테스트 코드  
https://lazyfoo.net/tutorials/SDL/01_hello_SDL/index2.php


참고 사이트 SDL tutorials  
http://www.sdltutorials.com/sdl-tutorial-basics
https://lazyfoo.net/tutorials/SDL/index.php
https://www.willusher.io/pages/sdl2/

https://wikidocs.net/book/6636

https://www.youtube.com/watch?v=EAMHQfCGymg
https://www.youtube.com/@codergopher8270



## Linux에서 Visual Studio Code 사용시 (Raspberry Pi)
1. SDL Source 다운로드  
  `git clone https://github.com/libsdl-org/SDL.git -b SDL2`  
  (참고: Branch main ➔ SDL2)

2. SDL Build  
  https://wiki.libsdl.org/SDL2/Installation  
  https://github.com/libsdl-org/SDL/blob/main/docs/README-linux.md


