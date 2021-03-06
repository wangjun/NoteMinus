# 尺帛 (NoteMinus, Note-)
尺帛，言之少也。  
現有筆記軟件大多沈重遲緩，食之無味的功能不可勝數，卻不能便捷的用自己習慣的文本編輯器來編輯，一個簡單的代碼高亮卻還要大書特書。龐大遲緩之餘，竟還無法在保持文件更新進度的前提下直接利用用戶散落在硬盤每個角落的零碎筆記。其實，用輕量級標記語言來寫，就能實現絕大多數筆記軟件提供的編輯效果，就差個瀏覽窗口。於是用 Python 寫一百多行代碼，配合一些支持命令行的外部工具實現所需。尺帛做的是減法，減到衹做重要的事，而且把這些事託付給業內行家去完成，自己衹是個中樞。  
簡而言之，尺帛處理的是「精修細改」而非「大量收藏」的筆記，是「長篇大論」而非「隻言片語」的筆記，處理方式是「反中央化」而非「中央化」。  

### 特色
* 如不需要 FTP 和 WebDAV 、改換打包方式，或者說衹需要筆記的瀏覽和轉換而不理會備份，尺帛支持 Windows, MAC, Linux 。現在全功能衹做了 Windows 。
* 尺帛使用 Pandoc 將 Markdown, reST, Textile, LaTeX, org 等格式源文件轉爲 HTML 文件並預覽（ css 和 js 由用戶自決）。所以尺帛也可以看作 Jekyll, hexo 等靜態 blog 程序的簡陋型第三方預覽器。
* 尺帛可通過 FTP, WebDAV, SimpleNote, 本地打包等方式備份。所以尺帛也可看作一個支持多種格式、支持代碼高亮、支持自定義顏色樣式、自帶加密備份的 SimpleNote 客戶端。
* 尺帛可指使用戶的常用編輯器打開源文件。編輯器是引戰領域，採「用戶自決」原則，體驗較佳。所以尺帛也可以看作一個適應所有編輯器的筆記插件。
* 代碼保持精簡，遵循 KISS 原則。

### 已知問題
* 在 Windows 10 下，搜索高亮文件和選中高亮的顏色太接近。
* 無法自動感知筆記內所附多媒體文件，故多媒體文件無法自動參與備份行爲。
* 不支持用戶把不同的筆記定義爲同一名字。
* 右鍵點擊筆記中的鏈接，菜單中的 'Open in New Window' 不可用。
* 衹支持 utf-8 編碼的筆記。

### 使用
1. 下載 Note-.pyw 和 conf.py 。
2. 安裝 [Python 3](https://www.python.org/downloads/) 環境、模塊（ [PyQt4](https://www.riverbankcomputing.com/software/pyqt/download) 和 [simplenote](https://github.com/mrtazz/simplenote.py) ），裝好 [Pandoc](https://github.com/jgm/pandoc/releases/latest), [WinSCP](https://winscp.net/eng/download.php), [7zip](http://www.7-zip.org/download.html) 。
3. 根據自身情況塡寫 conf.py 。仿照 files.txt 的格式塡寫筆記列表和需要備份的多媒體文件（多媒體文件的名字應指定爲 MMB ，否則將出現在筆記列表中）。
4. 打開 Note-.pyw 。

### Log:
2015/05/02 開工。  
2015/05/06 投入使用。  
2015/05/07 開源。  
2015/05/09 增強：把顯示文件列表改爲顯示內部用名。  
2015/05/14 增強：添加文件、列表修改、列表更新等按鈕。  
2015/05/16 功能：備份到 WebDAV 和 FTP ，需 WinSCP 。  
2015/05/18 功能：備份到 Dropbox ，免帳密，使用 oauth2 access token 。  
2015/05/27 功能： Tab ，開新 tab 時自帶 view 。代碼細節修改。  
2015/05/28 功能：檢索當前文件。變更：取消獨立的列表編輯按鈕，給 tabs 增加關掉按鈕。  
2015/05/29 修正：Tab 細節，添加簡陋 icon 。變更：也取消了 Style 的獨立按鈕。  
2015/06/01 變更：多處代碼細節，均爲簡約化，不涉及功能。  
2015/06/02 功能：新增一個按鈕，同時刷新列表、在列表裏搜索並高亮結果、選中首個結果。  
2015/06/03 功能：選中下一列表搜索結果。變更：代碼結構調整。  
2015/06/04 功能：生成全部筆記和編輯當前 tab 中正在瀏覽文件的源文件。變更：把設置文件獨立出來，未使用 configparser ，因爲懶且沒必要。  
2015/06/05 功能：集體備份到 FTP/WebDAV 、本地備份。變更：去掉添加到列表按鈕。  
2015/06/09 變更：本地備份改用 7-zip 加密打包， FTP 全部備份改爲上傳加密包，代碼細節變更。  
2015/06/10 功能：添加了快捷鍵。變更：把在列表搜索和選中下一列表搜索結果的按鈕合倂了。  
2015/06/12 變更：按鈕名簡化並加 tooltips 。  
2015/07/12 增強：刷新當前筆記的按鈕。變更：快捷鍵調整。  
2015/07/14 功能：備份到 SimpleNote 。變更：快捷鍵調整。  
2015/09/12 功能：在所有文件內容中搜索。刪除： Dropbox 。變更：快捷鍵調整、獨立爲一個項目。  
2015/09/14 變更：調整筆記列表字體大小和總窗口大小。  
2015/09/19 變更：按鈕文字修改，代碼細節修改。  
2015/09/23 功能：添加多媒體文件至備份，寫法同一般筆記，但名字衹能是 'MMB' ，否則出現在筆記列表。  
2015/09/30 功能：最小化到系統托盤，雙擊或右擊圖標恢復。順手添加 rtf, docx, epub, opml 的支持。  