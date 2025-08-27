# 國立高雄科技大學論文 LaTeX 精簡模板<br>(NKUST Thesis LaTeX Simple Template)

本專案為**國立高雄科技大學論文 LaTeX 精簡模板**，是擷取 Yuhao-Kuo 等人製作的[國立高雄科技大學研究所論文 LaTeX 模板](https://github.com/yuhao-kuo/NKUST-thesis-template)及 Hsins 等人的[國立台灣大學研究所論文 LaTeX 模板](https://github.com/Hsins/NTU-Thesis-LaTeX-Template) 進行改作的模板，格式參照[國立高雄科技大學教務處學位論文撰寫體例參考(中華民國111年3月修訂版)](https://acad.nkust.edu.tw/var/file/4/1004/img/212/F-2-35.docx)。

## 現況

本專案仍在開發中

## 使用

### 使用流程

1. 直接下載或 Git clone 本專案到本地電腦
2. LaTeX 開發環境設定
3. 編譯指令設定
4. 修改 setup/config.tex 中的必要資訊與選項
5. 開始撰寫您的論文內容

### LaTeX 開發環境設定

#### Windows

本專案在 Windows 11 中使用 MikTex + Strrawberry Perl + VSC(LaTeX Workshop) 能夠正常編譯，其他環境尚需測試。

#### Mac

#### Linux

### 編譯指令設定

- 由於 LaTeX 本身限制，加入 BibLaTeX 文獻管理後，編譯指令會較為繁瑣，因此需要另做設定

#### 直接使用命令列進行編譯

   ```
   cd [專案資料夾路徑]

   xelatex main
   biber main
   xelatex main
   xelatex main
   ```

#### Vscode + LaTeX Workshop (推薦)

#### Make

### 檔案結構說明

### config.tex 的調整

## 本專案仍可改進之處

1. 參考文獻格式使用 APA 但未加上方框標號

## 鳴謝

感謝 [Yuhao-Kuo 等人](https://github.com/yuhao-kuo/NKUST-thesis-template/graphs/contributors)及 [Hsins 等人](https://github.com/Hsins/NTU-Thesis-LaTeX-Template/graphs/contributors)們的貢獻！

## 免責聲明

使用前請務必檢視版型是否符合現行規範，若引用此專案造成一切損失，本專案不承擔任何責任。

如有任何問題及錯誤，歡迎發 Issue 告知。
