# 國立高雄科技大學論文 LaTeX 精簡模板<br>(NKUST Thesis LaTeX Simple Template)

本專案為**國立高雄科技大學論文 LaTeX 精簡模板**，是擷取 Yuhao-Kuo 等人製作的 [國立高雄科技大學研究所論文 LaTeX 模板](https://github.com/yuhao-kuo/NKUST-thesis-template) 及 Hsins 等人的 [國立台灣大學研究所論文 LaTeX 模板](https://github.com/Hsins/NTU-Thesis-LaTeX-Template) 進行改作的模板，格式參照 [國立高雄科技大學教務處學位論文撰寫體例參考(中華民國111年3月修訂版)](https://acad.nkust.edu.tw/var/file/4/1004/img/212/F-2-35.docx)。

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
|       oral_exam_approval.pdf # 口試審定書
|       power_of_attorney.pdf # 論文授權書
|       
\---setup # 所有專案設定
        config.tex
        pakeges.tex
        settings.tex
```

> [!IMPORTANT]  
> 若您對於 LaTeX 的語法不熟悉，建議您不要更動除「本專案 `setup/config.tex` 中論文必要資訊與選項調整」所提以外的本專案提供內容

### 本專案使用流程

1. 直接下載 zip 檔解壓縮或使用 `git clone` 本專案至您的電腦
2. LaTeX 開發環境設定
3. XeLaTeX + BibLaTeX 編譯指令設定
4. 修改本專案 `setup/config.tex` 中的論文必要資訊與選項
5. 開始撰寫您的論文內容，若有其它欲調整處，請見專案中註解

### LaTeX 開發環境設定

- 因為專案規模大小問題，不建議使用如 [Overleaf](https://www.overleaf.com/) 這樣的雲端網頁服務編譯。
- 如果您會使用 [Git](https://git-scm.com/) 進行版本控制，LaTeX 搭配 Git 使用，那是非常棒的，Very Beautiful，Very Powerful。

#### 本專案開發環境

以下列出本專案開發環境，其它環境尚需測試，但應是理論可用的。

- 作業系統：Windows 11
- LaTeX 編譯器：[MikTeX](https://miktex.org/)
- LaTeX 發行版：XeLaTeX
- LaTeX 文獻管理套件：BibLaTeX(Biber)
- 編輯器環境：
  - [Visual Studio Code](https://code.visualstudio.com/)
  - [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
  - [Strawberry Perl](https://strawberryperl.com/)：配合 MikTex 編譯所需

#### 安裝編譯器

以下列出各作業系統可用的編譯器以供參考。

- Windows
  - [MikTeX](https://miktex.org/)：本專案推薦
  - [TeXlive](https://www.tug.org/texlive/)

- Mac
  - [MacTeX](https://www.tug.org/mactex/)
  - [MikTeX](https://miktex.org/)
  - [TeXlive](https://www.tug.org/texlive/)

- Linux
  - [MikTeX](https://miktex.org/)
  - [TeXlive](https://www.tug.org/texlive/)

### XeLaTeX + BibLaTeX 編譯指令設定

本專案使用 XeLaTeX 與 BibLaTeX(Biber) 進行文獻管理，由於 LaTeX 本身限制，編譯指令會較為繁瑣，因此建議另做設定，在編譯上才會更為方便。

#### 直接使用命令列進行編譯(不建議)

   ```
   cd [專案資料夾路徑]

   xelatex main
   biber main
   xelatex main
   xelatex main
   ```

#### Vscode + LaTeX Workshop Recipe (建議)

1. 下載 Vscode 並安裝 [LaTeX Workshop Extension](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop)
2. 在 Vscode 中，利用 `ctrl + shift + p` 快捷鍵，輸入`Preference： Open User Settings(JSON)`，打開 `settings.josn`
3. 在`settings.josn`中加入以下 JSON
4. 之後便可在開啟 `main.tex` 時，切換至 LaTeX Workshop 面版進行編譯

```json
  // LaTeX
  "[latex]": {
    "editor.defaultFormatter": "James-Yu.latex-workshop"
  },

  "latex-workshop.view.pdf.viewer": "tab", // 選擇pdf瀏覽器，可選browser/tab/external
  "latex-workshop.latex.autoBuild.run": "never", // 不要自動編譯
  "latex-workshop.formatting.latex": "latexindent", // 設定 forrmatter

  // 設定 LaTeX 編譯工具指令
  "latex-workshop.latex.tools": [
    {
      "name": "xelatex",
      "command": "xelatex",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
    },
    {
      "name": "xelatex-with-shell-escape",
      "command": "xelatex",
      "args": [
        "--shell-escape",
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
    },
    {
      "name": "pdflatex",
      "command": "pdflatex",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
    },
    {
      "name": "pdflatex-with-shell-escape",
      "command": "pdflatex",
      "args": [
        "--shell-escape",
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "%DOC%"
      ]
    },
    {
      "name": "latexmk",
      "command": "latexmk",
      "args": [
        "-synctex=1",
        "-interaction=nonstopmode",
        "-file-line-error",
        "-pdf",
        "%DOC%"
      ]
    },
    {
      "name": "bibtex",
      "command": "bibtex",
      "args": ["%DOCFILE%"]
    },
    {
      "name": "biber",
      "command": "biber",
      "args": ["%DOCFILE%"]
    },
    {
      "name": "makeindex",
      "command": "makeindex",
      "args": ["%DOCFILE%"]
    }
  ],

  // 選擇 LaTeX 編譯工具的指令，以及工具的順序
  "latex-workshop.latex.recipes": [
    //　目前只使用 xelatex 和 biber
    {
      "name": "xelatex",
      "tools": ["xelatex"]
    },
    {
      "name": "xelatex -> biber -> xelatex*2",
      "tools": ["xelatex", "biber", "xelatex", "xelatex"]
    }
  ],

  // 每次編譯前，刪除之前的output檔
  "latex-workshop.latex.clean.enableed": true,
  "latex-workshop.latex.clean.fileTypes": [
    "*.aux",
    "*.bbl",
    "*.blg",
    "*.idx",
    "*.ind",
    "*.lof",
    "*.lot",
    "*.out",
    "*.toc",
    "*.acn",
    "*.acr",
    "*.alg",
    "*.glg",
    "*.glo",
    "*.gls",
    "*.ist",
    "*.fls",
    "*.log",
    "*.fdb_latexmk"
  ],
```

> [!NOTE]  
> 以上內容參考自
>
> 陳宥廷. (2021, April 10). *VS Code 下的 LaTeX 環境設定*. HackMD. <https://hackmd.io/@DextinChen/VSCode-LaTeX-setting>.
>
> Kaibaooo. (2022, August 12). *使用 VSCode 上撰寫中文 Latex 文件*. Kaibaooo’s Note. <https://kaibaoom.tw/posts/notes/vscode-latex/>.
>
> 邱繼群. (2022, September 16). *Latex*. HackMD. <https://hackmd.io/@m7Thna5ET3KEdtU32Lsk3g/r1XI4_KSK>.

#### Makefile

- 適合進階使用者自行研究

### 本專案 `setup/config.tex` 中論文必要資訊與選項調整

- 詳細請見 `setup/config.tex` 檔案中註解
- 需要調整部份主要為：論文內容選項、論文基本資訊、語言變數
- 論文內容選項：
  - 本專案已將大部分需調整的內容置於註解，僅需解開需要的即可
  - 需注意區分中英文獻選項，若需使用這個，則必須確定您的參考文獻 bib 皆需要有 `langid` 欄位，且中文文獻在此欄位必須有 `zh` 或 `chinese` 值
- 論文基本資訊：為研究生、指導教授、學校等基本資訊
- 語言變數：本專案預設使用中文，若使用英文撰寫論文，則需將中文部份註解，並將英文部份解開註解

## 本專案仍可改進之處

1. 參考文獻格式使用 APA，未如學校格式加上方框標號
2. 參考文獻中文標點符號未轉全形

## 鳴謝

感謝 [Yuhao-Kuo 等人](https://github.com/yuhao-kuo/NKUST-thesis-template/graphs/contributors)及 [Hsins 等人](https://github.com/Hsins/NTU-Thesis-LaTeX-Template/graphs/contributors)們的貢獻！

## 免責聲明

使用前請務必檢視版型是否符合貴系所現行規範，若引用此專案造成一切損失，本專案不承擔任何責任。

如有任何問題及錯誤，歡迎發 Issue 告知。
