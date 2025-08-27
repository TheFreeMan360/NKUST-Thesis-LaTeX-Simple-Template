# 國立高雄科技大學論文 LaTeX 精簡模板<br>(NKUST Thesis LaTeX Simple Template)

本專案為**國立高雄科技大學論文 LaTeX 精簡模板**，是擷取 Yuhao-Kuo 等人製作的[國立高雄科技大學研究所論文 LaTeX 模板](https://github.com/yuhao-kuo/NKUST-thesis-template)及 Hsins 等人的[國立台灣大學研究所論文 LaTeX 模板](https://github.com/Hsins/NTU-Thesis-LaTeX-Template) 進行改作的模板，格式參照[國立高雄科技大學教務處學位論文撰寫體例參考(中華民國111年3月修訂版)](https://acad.nkust.edu.tw/var/file/4/1004/img/212/F-2-35.docx)。

## 開發現況

本專案仍在開發中，但大致內容已經穩定可用，僅剩細部修改

## 使用

### 本專案目錄結構

```text
C:.
|   .gitignore
|   main.pdf
|   main.tex
|   README.md
|   
+---.git # 內容省略
+---back # 後頁內容
|       appendix01.tex # 範例用可刪除
|       appendix02.tex # 範例用可刪除
|       references.bib
|       
+---chapters # 章節內文內容
|       chapter01.tex
|       chapter02.tex
|       chapter03.tex
|       chapter04.tex
|       chapter05.tex
|       
+---figures # 圖片放置位置
|   \---seal # 高科大校徽
|           seal_golden.png # 金色版
|           seal_standard.png # 彩色版
|           
+---fonts # 字體位置
|   +---en 
|   |       Times New Roman-Bold.ttf # Times New Roman font Family from Hsins
|   |       Times New Roman-BoldItalic.ttf
|   |       Times New Roman-Italic.ttf
|   |       Times New Roman.ttf
|   |       
|   \---zhtw
|           BiauKai.ttf # 標楷體 from Hsins
|           edukai-4.0.license
|           edukai-4.0.ttf # 教育部楷體 from Yuhao-Kuo
|           edusong-big5.license
|           edusong-big5.ttf # 教育部宋體 from Yuhao-Kuo
|           
+---front # 前頁內容
|       abstract_en.tex
|       abstract_zhtw.tex
|       aknowlegement.tex
|       denotation.tex
|       oral_exam_approval.pdf
|       power_of_attorney.pdf
|       
\---setup # 所有專案設定
        config.tex
        pakeges.tex
        settings.tex
```

- 若您對於 LaTeX 的語法不熟悉，建議您不要更動除「本專案 `setup/config.tex` 中論文必要資訊與選項調整」所提以外的本專案提供內容

### 本專案使用流程

1. 直接下載 zip 檔或使用 `git clone` 本專案至您的電腦
2. LaTeX 開發環境設定
3. XeLaTeX + BibLaTeX 編譯指令設定
4. 修改本專案 `setup/config.tex` 中的論文必要資訊與選項
5. 開始撰寫您的論文內容，若有其它欲調整處，請見專案註解

### LaTeX 開發環境設定

#### 本專案開發環境

以下列出本專案開發環境，其它環境尚待測試，但應是理論可用的

- 作業系統：Windows 11
- LaTeX 編譯器：[MikTex](https://miktex.org/)
- 編輯環境：[Vscode](https://code.visualstudio.com/) + [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) + [Strawberry Perl](https://strawberryperl.com/)

#### Windows

#### Mac

#### Linux

### XeLaTeX + BibLaTeX 編譯指令設定

本專案使用 XeLaTeX 與 BibLaTeX(Biber) 進行文獻管理，由於 LaTeX 本身限制，編譯指令會較為繁瑣，因此建議另做設定，在編譯使用上才會更為方便。

#### 直接使用命令列進行編譯(不建議)

   ```
   cd [專案資料夾路徑]

   xelatex main
   biber main
   xelatex main
   xelatex main
   ```

#### Vscode + LaTeX Workshop (建議)

#### Makefile

### 本專案 `setup/config.tex` 中論文必要資訊與選項調整

## 本專案仍可改進之處

1. 參考文獻格式使用 APA，未如學校格式加上方框標號
2. 參考文獻中文標點符號未轉全形

## 鳴謝

感謝 [Yuhao-Kuo 等人](https://github.com/yuhao-kuo/NKUST-thesis-template/graphs/contributors)及 [Hsins 等人](https://github.com/Hsins/NTU-Thesis-LaTeX-Template/graphs/contributors)們的貢獻！

## 免責聲明

使用前請務必檢視版型是否符合貴系所現行規範，若引用此專案造成一切損失，本專案不承擔任何責任。

如有任何問題及錯誤，歡迎發 Issue 告知。
