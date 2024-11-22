# 國立高雄科技大學論文 LaTeX 精簡模板<br>(NKUST Thesis LaTeX Simple Template)

本專案為**國立高雄科技大學論文 LaTeX 精簡模板**，是擷取 Yuhao-Kuo 等人製作的[國立高雄科技大學研究所論文 LaTeX 模板](https://github.com/yuhao-kuo/NKUST-thesis-template)及 Hsins 等人的[國立台灣大學研究所論文 LaTeX 模板](https://github.com/Hsins/NTU-Thesis-LaTeX-Template) 進行改作的模板，格式參照[國立高雄科技大學教務處學位論文撰寫體例參考(中華民國111年3月修訂版)](https://acad.nkust.edu.tw/var/file/4/1004/img/212/F-2-35.docx)。

## 開發環境

本專案在 Windows 11 中使用 MikTex + Strrawberry Perl + VSC(LaTeX Workshop) 能夠正常編譯，其他環境尚需測試。

## 使用

本專案使用 xelaTeX + biblaTeX 製作

### 如何開始?

1. 下載本專案
2. 修改 setup/config.tex 中的必要資訊與選項
3. 撰寫內容
4. 編譯 main.tex

   ```
   cd [專案資料夾路徑]

   xelatex main
   biber main
   xelatex main
   xelatex main
   ```

## 本專案仍可改進之處

1. 參考文獻格式使用 APA 但未加上方框標號
2. APA 未符合中文文獻格式  
3. 標題格式的邏輯可再區分為 renew 標號計數器(chapter、section)與顯示格式(Format 丟入 \thechapter、\thesection)，方便使用者自定標題格式
4. 圖表標題有章節間距
5. 語言變數邏輯可以簡化，若非前頁接需使用，可以只放 config 變數

## 鳴謝

感謝 [Yuhao-Kuo 等人](https://github.com/yuhao-kuo/NKUST-thesis-template/graphs/contributors)及 [Hsins 等人](https://github.com/Hsins/NTU-Thesis-LaTeX-Template/graphs/contributors)們的貢獻！

## 免責聲明

使用前請務必檢視版型是否符合現行規範，若引用此專案造成一切損失，本專案不承擔任何責任。

如有任何問題及錯誤，歡迎發 Issue 告知。
