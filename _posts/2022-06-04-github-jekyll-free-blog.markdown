---
layout: post
title:  超省錢架站法，透過 GitHub Pages + JeKyll，搭建自己免費 Blog 空間
date:   2022-06-04 01:01:35 +0800
image:  jekyll.webp
categories: Infra
tags:   Jekyll
description : A short description of the page's content
author : Mark ku
keywords : test
---
## 問題
因為身邊很多，想和我一樣，擁有一個個人的網站，但架一個網站，光是放在雲端空間，至少費用4000元 以上，但也不是每個人都像我有自己的伺服器，因此，今天我想來寫一篇超省錢的架站法。

## 架站費用
~~網站空間 4000 以上 / 年~~  
域名  680 元 / 年
## Jeklly 是什麼 
Jekyll是一個簡單的靜態網站生成器，用於生成個人，專案或組織的網站。 它由GitHub聯合創始人湯姆·普雷斯頓·沃納用Ruby編寫，並根據MIT授權條款釋出。 (Wiki)

## 事先準備
### * 註冊 Github 帳號 [連結](https://github.com/)
### * 購買一個屬於自己的域名 ( 台灣域名 振遠比較便宜，如果是國際域名，那就去 Godaddy 購買)

## 架設步驟
### 1. 首先挑選 Jeklly 模板
[免費模板](http://jekyllthemes.org/)  

### 2. fork 專案，本篇以 [Zolan 開源版型為例](https://github.com/artemsheludko/zolan)，點擊 Fork
![](https://i.imgur.com/ky411PL.png)

### 3. fork 完成，接著我們要設定 Github Pages，Settings > Pages > Source > Root > Save
![](https://i.imgur.com/AUcLezJ.png)

### 4. Github Action 這時就會開始建置部署，並部署網站
![](https://i.imgur.com/b4QB0r1.png)

### 5. 建置部署完, 就會在您的 Github Pages 頁籤中，顯示你的網站網址
![](https://i.imgur.com/GaLkQnI.png)

### 6. 輸入要客製的域名 Save
![](https://i.imgur.com/CTzYhPb.png)

### 7. 至 DNS 將域名，新增一筆 CNAME 記錄，指向 Github 指定的 Url
![](https://i.imgur.com/vjYI98c.png)

### 8. 編輯專案下的 _config.yml，將 baseurl 清空 > Commit changes
![](https://i.imgur.com/3jOMt4l.png)

### 9. 此時，Github Action 會重新建置部署，建置部署好，你就可以訪問你的 blog 
![](https://i.imgur.com/NJtReZL.png)
### 10. 如果想要 https 憑證，可以將 DNS 網域託管在 Cloud Flare，即可獲得免費憑證。 [參考先前的文章](https://blog.markkulab.net/2021/10/27/clould-flare-cdn/)

## 網站文章編輯
### 1. 切換到專案 Code >  zolan/_posts，此資料夾就是blog 的文章，點選任一選則文章。
![](https://i.imgur.com/A6dAj0i.png)
### 2. 點選編輯
![](https://i.imgur.com/9e8x5nW.png)

### 3. 試著修改標題及內容 > Commit change
![](https://i.imgur.com/ayFRoWo.png)
![](https://i.imgur.com/GBXx63t.png)

### 4. 直到Github Action 建置部署完，剛剛修改的文章內容，就更新了。
![](https://i.imgur.com/SwKXUxO.png)

### 5. 如果新增文章，只你要在 zolan/_posts/資料夾下，新增一樣的檔案，則，就會跑出一篇新的文章。

## 補充說明
### 我的習慣會在 [hackmd](https://hackmd.io/) 將想法打完，在複製到該資料夾，發佈
### 相關檔案及資料夾介紹
zolan/_posts/ => 文章放置目錄  
zolan/images => 圖片路徑  
zolan/_data/settings.yml => 可以設置標圖及內容  
zolan/_config.yml => 網站設置，可調整分頁大小  
zolan/_layouts/ => 如果懂一些 html 可以調整板型  
### 先前文章，在容器中架設JeKyll [連結](https://blog.markkulab.net/2021/04/14/Jekyll-Markdown-Blog/)

