# DVWA & Flask Server – XSS Attacks Lab

DVWA 與 Flask Server – XSS 攻擊 Lab

<h2>Outline 簡介</h2>

This project explores Cross-Site Scripting (XSS) vulnerabilities using DVWA and a custom Flask-based server. The exercises include Stored XSS, Reflected XSS, and Persistent XSS scenarios, highlighting how malicious scripts can be injected, stored, and executed in web applications.

本專案透過 DVWA 與自製 Flask 伺服器練習 跨站腳本攻擊 (XSS)，涵蓋 儲存型 XSS、反射型 XSS 與持續型 XSS，展示惡意腳本如何被注入、儲存並在網站上執行。

<h2>Objectives 目的</h2>

* Practice identifying and exploiting different types of XSS vulnerabilities (Stored, Reflected, Persistent).<br/>
  練習辨識並利用不同類型的 XSS 漏洞(儲存型、反射型、持續型)</b>
* Understand the impact of executing malicious scripts in a web application.<br/>
  理解惡意腳本在 Web 應用程式中執行所帶來的影響</b> 
* Gain hands-on experience using DVWA and a custom Flask-based server as controlled lab environments.<br/>
  在可控環境下透過 DVWA 與 Flask 伺服器進行實作訓練</b> 
* Strengthen awareness of defensive programming and input sanitization techniques.<br/>
  強化對防禦性程式設計與輸入驗證技術的認知</b>


<h2>Materials and Methods 材料與方法</h2>

[Environment]
* Linux Debian 12 VM with VirtualBox nested VMs (帶有 VirtualBox 嵌套虛擬機的 Linux Debian 12 虛擬機)</b> 
* UniSQ Student VM Portal (UniSQ 學生用 VM)</b>
* Damn Vulnerable Web Application [易受攻擊的 Web 應用程式 (DVWA)]</b>
* Custom Flask server (本地運行的自製 Flask 伺服器)</b>

[Safety note]
* DVWA is intentionally vulnerable; do not deploy on internet-facing hosts.<br/>
  DVWA 為刻意脆弱之系統，請勿對外公開部署</b>

[Tasks]
* Inject JavaScript Alert (注入 JavaScript 警告彈窗)</b>
* HTML Tag Injection (注入 HTML 標籤)</b>
* Display Session Cookie (顯示 Session Cookie)</b>
* Reflected XSS with Cookie Script (反射型 XSS 顯示 Cookie)</b>
* Reflected XSS Simple Alert (反射型 XSS 簡單彈窗)</b>
* Inject Clickable Link (注入可點擊的惡意連結)</b>
* Redirect Victim to External Site (重導向至外部網站)</b>
* Start Flask Server (啟動 Flask 伺服器)</b>
* Perform Persistent XSS (執行持續型 XSS)</b>


<h2>Practice 實踐</h2>

<p align="center">
<b>Task 1: Inject JavaScript Alert<br/>(注入 JavaScript 警告彈窗)</b><br/>
<img src="https://i.imgur.com/KzswklJ.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>
<br />
<b>Task 2: HTML Tag Injection<br/>(注入 HTML 標籤) </b><br/>
<img src="https://i.imgur.com/6qAyuCc.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* The text is displayed with bold and italic formatting (頁面會顯示粗體與斜體文字)<br/>
* The DVWA reaction means that it fails to properly sanitize inputs and encode outputs, which lets browsers interpret HTML tags directly. <br/>This creates a risk of cross-site scripting (XSS).<br/>(DVWA 的反應意味著它未能正確過濾輸入和編碼輸出，導致瀏覽器直接解釋 HTML 標籤，從而存在跨站腳本 (XSS) 風險)</b>
<br/>
<br />
<b>Task 3: Display Session Cookie<br/>(顯示 Session Cookie) </b><br/>
<img src="https://i.imgur.com/ROB9bQr.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* An alert box immediately shows the session cookie, but even if you leave the page and return again, the script will still be valid. <br/>(警告框會立即顯示會話 cookie，但即使離開該頁面並再次返回，腳本仍然有效)</b>
<br/>
<br />
<b>Task 4: Reflected XSS with Cookie Script<br/>(反射型 XSS 顯示 Cookie) </b><br/>
<img src="https://i.imgur.com/PxD35yx.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Inject the same code and try to revisit the page. <br/>(注入相同的程式碼並嘗試重新訪問該頁面)<br/>
* An alert box immediately shows the session cookie, but if you leave the page and return again, the script will no longer be valid. <br/>(警告框會立即顯示會話 cookie，但若離開該頁面並再次返回，腳本將不再有效)</b>
<br/>
<br />
<b>Task 5: Reflected XSS Simple Alert<br/>(反射型 XSS 簡單彈窗) </b><br/>
<img src="https://i.imgur.com/3nNb7ui.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/> 
<br />
<b>Task 6: Inject Clickable Link<br/>(注入可點擊的惡意連結)</b><br/>
<img src="https://i.imgur.com/y9BJW9S.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* A link is shown; clicking it triggers an alert “Click!” <br/>(頁面顯示超連結，點擊後觸發 “Click!” 的彈窗)</b>
<br/>
<br />
<b>Task 7: Redirect Victim to External Site<br/>(重導向至外部網站)</b><br/>
<img src="https://i.imgur.com/VRQCvGD.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>
<br />
<b>Task 8: Start Flask Server<br/>(啟動 Flask 伺服器)</b><br/>
<img src="https://i.imgur.com/97F78ar.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>
<br />
<b>Task 9: Perform Persistent XSS<br/>(執行持續型 XSS)</b><br/>
<img src="https://i.imgur.com/YsRjpfR.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Inject malicious script into input fields. On subsequent visits, the script executes automatically.<br/>(將惡意腳本注入輸入欄位。後續造訪時，該腳本將自動執行)</b>
<br/>

<h2>Stored XSS vs Persistent XSS (儲存型與持續型 XSS 差異)</h2>

| 類型 <br/>(Type)                      | 定義 <br/>(Definition)                                                                  | 觸發方式 <br/>(Trigger)                                                            | 影響範圍 <br/>(Impact Scope)                                                                                                    | 課程範例 <br/>(Course Example)        |
| ------------------------ | -------------------------------------------------------------------------------- | ------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------- | ---------------------------- |
| **Stored XSS <br/>(儲存型)**     | Malicious script is saved into the server database or file <br/>(惡意程式碼被存入伺服器的資料庫或檔案中) | Executed whenever stored content is retrieved <br/>(每次讀取該內容時觸發)                | Limited to the specific page or module where the payload is displayed <br/>(通常只影響顯示該輸入內容的特定頁面或功能模組)                         | DVWA – *XSS (stored)*        |
| **Persistent XSS <br/>(持續型)** | A special case of Stored XSS that emphasizes long-term effect <br/>(儲存型的特例，強調長期持續影響)  | Script executes automatically on every subsequent visit<br/>(每次後續造訪頁面時都會自動執行) | May affect multiple pages or even the whole site if injected into shared components <br/>(若注入共用區塊，例如首頁公告或模板，可能影響多個頁面甚至整個網站) | Flask Server – `a2server.py` |


<h2>Results 成果展示</h2>

Successfully demonstrated different forms of XSS attacks in both DVWA and a Flask-based web server, progressing from simple alerts to cookie theft and redirection. This project emphasized the real-world risks of insecure input handling and reinforced the importance of secure coding practices in web application development.

本專題成功展示了在 DVWA 與 Flask 伺服器中進行的多種 XSS 攻擊，從簡單彈窗到竊取 Cookie 與惡意導向，完整體驗了攻擊過程。此實作突顯了輸入處理不當的實際風險，並強化了 Web 應用程式開發中安全編碼的重要性。


<h2>Reference 參考</h2>

[UniSQ] [CSC8520 - Securing Networks](https://handbook-guide.unisq.edu.au/course/2025/CSC8520)
