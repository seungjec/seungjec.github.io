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


#%%

class A():
    def __init__(self, pos):
        self.pos = pos
        self.b = 0

    def func0(self):
        self.pos += 1
        print("A: ", self.pos)

    def func(self):
        self.b = B(self.pos)
        # self.b.func()

class B():
    def __init__(self, pos):
        self.pos = pos

    def func(self):
        self.pos += 1
        print("B: ", self.pos)

class C():
    def __init__(self):
        self.a = A0)
        # self.a.func()

    def run(self, idx):
        self.a.func0()

        if idx == 3:
            self.a.func()

        if self.a.b != 0:
            self.a.b.func()

        if idx == 7:
            del self.a.b

if __name__ == "__main__":

    c = C()
    for idx in range(10):
        c.run(idx)




