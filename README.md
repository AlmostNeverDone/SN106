# DVWA & Flask Server – XSS Attacks Lab

DVWA 與 Flask Server – XSS 攻擊 lab

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

*Safety note: DVWA is intentionally vulnerable; do not deploy on internet-facing hosts.
<br/>*安全提醒：DVWA 為刻意脆弱之系統，請勿對外公開部署。

[Tasks]
* Baseline Test(基線測試)</b>
* Manipulated Input for Multiple Records(輸入操控取得多筆紀錄)</b>
* Extract Database Version(讀取資料庫版本)</b>
* Extract Database User(讀取資料庫使用者)</b>
* Identify Active Database(確認當前資料庫)</b>
* Enumerate Table Names(枚舉表格名稱)</b>
* Filter User-Related Tables(過濾使用者相關表格)</b>
* Enumerate Columns(枚舉欄位)</b>
* Data Exposure Demonstration(資料洩漏示範)</b>


<h2>Practice 實踐</h2>

<p align="center">
Task 1: Baseline Test<br/>(基線測試) <br/>
<img src="https://i.imgur.com/InVX6Db.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Confirms that input directly affects the backend query.(確認輸入內容會直接參與後端查詢)</b>
<br/>
<br />
Task 2: Manipulated Input for Multiple Records<br/>(輸入操控取得多筆紀錄) <br/>
<img src="https://i.imgur.com/mEu8Dnf.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Indicates lack of input validation. (顯示後端查詢缺乏輸入驗證)</b>
<br/>
<br />
Task 3: Extract Database Version<br/>(讀取資料庫版本) <br/>
<img src="https://i.imgur.com/DlyOOx7.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Proves that system-level information can be exposed. (證實能以 UNION 技術讀取系統層級資訊)</b>
<br/>
<br />
Task 4: Extract Database User<br/>(讀取資料庫使用者) <br/>
<img src="https://i.imgur.com/q5iRFJz.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Reveals which account the application uses for DB access. (揭露應用程式連線所使用的 DB 帳號)</b>
<br/>
<br />
Task 5: Identify Active Database<br/>(確認當前資料庫) <br/>
<img src="https://i.imgur.com/dZJcibk.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Helps in structuring further enumeration. (協助後續資料庫結構探索)</b>
<br/> 
<br />
Task 6: Enumerate Table Names<br/>(枚舉表格名稱) <br/>
<img src="https://i.imgur.com/vlCWr5J.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Confirms metadata exposure. (證實中繼資料可被揭露)</b>
<br/>
<br />
Task 7: Filter User-Related Tables<br/>(過濾使用者相關表格) <br/>
<img src="https://i.imgur.com/KwvK4HX.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Pattern search identifies sensitive structures. (透過模式比對鎖定敏感表格)</b>
<br/>
<br />
Task 8: Enumerate Columns<br/>(枚舉欄位) <br/>
<img src="https://i.imgur.com/rTwtHs4.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Reveals schema design of target table. (揭露目標表格的欄位設計)</b>
<br/>
<br />
Task 9: Data Exposure Demonstration<br/>(資料洩漏示範) <br/>
<img src="https://i.imgur.com/XdTuhdB.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
* Confirms real-world risk of SQL Injection. (證實 SQLi 對敏感資料的實際危害)</b>
<br/>


<h2>Results 成果展示</h2>

Successfully demonstrated how SQL Injection can escalate from retrieving a single record to exposing complete database structures and sensitive user information in DVWA under Low Security settings. The project highlights both the technical risks of insecure coding practices and the importance of systematic defense measures such as input validation and parameterized queries.

本專題成功展示了 SQL 注入在 DVWA 低安全等級下，如何從單筆查詢逐步升級到完整資料庫結構與敏感使用者資料的洩漏。此實作凸顯了不安全編碼的技術風險，以及輸入驗證與參數化查詢等系統性防禦措施的重要性。


<h2>Reference 參考</h2>

[UniSQ] [CSC8520 - Securing Networks](https://handbook-guide.unisq.edu.au/course/2025/CSC8520)
