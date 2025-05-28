# Intro

自動從 VT 撈釣魚網站 LINK ，丟到 URLScan 上面分析，並傳到 slack 上面

# 第一個 node

`on a schedule`
- 基本不用條，要調也可以，就根據自己想要多久觸發一次，這相當於 crontab

# 第二個 node

`action in an app -> VirusTotal`
- Credential for VirusTotal: 放自己的 VirusTotal API Token
- URL: https://www.virustotal.com/api/v3/intelligence/search (用以做 Threat Intelligence)
- [x] Send Query Parameters
  - Specify Query Parameters: Using Fields Below
  - Query Parameters
    - Name: query
    - Value: (這個就是 vt 搜尋，可以去上面找，這邊複製 vt 上針對釣魚網站的搜尋方式) `entity:url and engines:phishing and p:3+ and fs:2d+`  

點選測試看看有無問題，看看有無拿到資料

# 第三個 node

選 `code`
- mode: Run once for all items
- language: python
- python code below:
