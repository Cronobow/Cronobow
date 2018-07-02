---
layout: post
title: "ASW Summit Taipei 2018 議題回顧"
date: 2018-07-02 19:20:32 +0800
comments: true
tags: 
- conference
---
本篇是今年參加 ASW Summit Taipei 2018 的簡易分場議題回顧。

<!-- more --> 

### GDPR x AWS 導覽

> 無論機構的位置，只要機構有 `收集` `儲存` `處理` EU 成員的個資，就需要符合 GPDR。

- What is GPDR

{% include image.html path="2018/aws-smmit-2018/IMG_0243.JPG" alt="aws-image" %}

- 如何分辨內容與個資

只要資料能識別獨立的 EU 客人，都屬於個資，例如註冊時紀錄的 IP，可以和註冊資料比對後識別個人，此註冊時的 IP 紀錄就屬於個資。

### 個資保護機制的重點項目

這部分應該是這場議題的大重點：

- 賦予使與者資料可攜的權利

{% include image.html path="2018/aws-smmit-2018/IMG_0244.JPG" alt="aws-image" %}

這部分，在台灣許多企業幾乎無法做到，甚至自己有哪些個資在企業手上都無法得知。

- 資料的可遺忘權（刪除）
{% include image.html path="2018/aws-smmit-2018/IMG_0245.JPG" alt="aws-image" %}

這是台灣個資法上路時的重點項目之一，但實務上幾乎無法監管。

- 初始設計就該有以上機制
{% include image.html path="2018/aws-smmit-2018/IMG_0246.JPG" alt="aws-image" %}

這我想是許多企業來不及符合 GDPR 的原因

- 資料外洩時的通報機制
{% include image.html path="2018/aws-smmit-2018/IMG_0247.JPG" alt="aws-image" %}

台灣好像沒有發生過什麼個資外洩的事件（怎麼可能，是沒人承認過...都是 they 的錯）

### 責任分攤

這裏把個資的處理成分成兩部分，控制者(Controllers)
和處理者(Processors)。

無論控制者(公司)，處理者(AWS)都需要負責
如果是 B2B 的產業，自身機構對其他公司的個資(等於自己是其他公司的處理者)，也需要負責。

簡單一句話，有碰到的都要負責(符合 GDPR)

### TOMS. Technical Operational and Maintenance System.

Controllers 和 Processors 該做的事：

{% include image.html path="2018/aws-smmit-2018/IMG_0248.JPG" alt="aws-image" %}

1. 收集回來的個資，需要加密
2. 所有的個資需要備份
3. 需有有復原的技術
4. 定期評估 TOMs 的有效性

### AWS 針對保護與加密的可用工具 

{% include image.html path="2018/aws-smmit-2018/IMG_0249.JPG" alt="aws-image" %}

1. 設計階段的資料保護
  - 傳輸時的加密 https/TLS
2. 儲存時的加密 
  - AWS KMS 金鑰管理
  - CloudHSM
3. 處理動作的記錄
  - AWS CloudTrail 帳戶使用紀錄
  - AWS Config 掃描加密設定檔
  - AWS GuartDuty 警告

{% include image.html path="2018/aws-smmit-2018/IMG_0250.JPG" alt="aws-image" %}
{% include image.html path="2018/aws-smmit-2018/IMG_0251.JPG" alt="aws-image" %}
{% include image.html path="2018/aws-smmit-2018/IMG_0252.JPG" alt="aws-image" %}

最後官方工商服務：AWS 已完全符合 GDPR 標準

---

## 以 Amazon EC2 Spot 執行個體有效控制專案成本

{% include image.html path="2018/aws-smmit-2018/IMG_0253.JPG" alt="aws-image" %}

### 機器的種類（依計費方式）

1. On-Demoan
  - 用多少算多少
2. Reserved
  - 長期租用（適合底層服務）
3. Spot
  - 突發性需求

### Spot 用便宜的價格銷售閒置資源

{% include image.html path="2018/aws-smmit-2018/IMG_0255.JPG" alt="aws-image" %}

### Request Type

- Request （抽掉就沒了）
- Request and Maintanin （抽走就補）
 
### 新增功能

1. New Price Model
  - 不需設定浮動價格的最大值
  - 平均價格低
  - 不會超過 On-Demand 價格
2. 不需要學習新的API
  - 和 EC2 一樣的指令
  - 同樣的 API 可用多個服務

### Pause & Resume

- Stop/Start （類似 EC2 的 Stop/Start）
  {% include image.html path="2018/aws-smmit-2018/IMG_0257.JPG" alt="aws-image" %}
- Hibernate/Resume (類似休眠)
  Memory/RAM 都還會在
  {% include image.html path="2018/aws-smmit-2018/IMG_0260.JPG" alt="aws-image" %}

---

##  使用 AWS Step Functions 靈活調度 AWS Lambda

- AWS Lambda: 不用管理底層資源就能完成任務

- 每個功能(function)的執行都專注於解決一件事情

- 透過工作流程組成複雜的事情

- AWS Step Function

  - State Machine
  - JSON 化的工作流程描述
  - 每個流程進行時，會有完整紀錄

- Step Function 的狀態

{% include image.html path="2018/aws-smmit-2018/IMG_0261.JPG" alt="aws-image" %}

---

## 產業轉型：如何利用 AWS 構建 SaaS 服務平台，新思維拓展新商機

### SaaS 優勢

- 可將內部服務資源轉為外部應用

1. 對使用者友善度高
2. 價格：可採用訂閱制，有使用再付款
3. 版本控制佳
4. 管理方便

### 傳統服務轉型 SaaS 

{% include image.html path="2018/aws-smmit-2018/IMG_0268.JPG" alt="aws-image" %}

### 做 Saas 要考慮的點

{% include image.html path="2018/aws-smmit-2018/IMG_0270.JPG" alt="aws-image" %}

### 轉型重點

{% include image.html path="2018/aws-smmit-2018/IMG_0272.JPG" alt="aws-image" %}

1. 公司思維與文化轉變
2. 各部門相互支援

### 工具簡介

{% include image.html path="2018/aws-smmit-2018/IMG_0274.JPG" alt="aws-image" %}

{% include image.html path="2018/aws-smmit-2018/IMG_0275.JPG" alt="aws-image" %}

{% include image.html path="2018/aws-smmit-2018/IMG_0277.JPG" alt="aws-image" %}


### Takeaways

{% include image.html path="2018/aws-smmit-2018/IMG_0276.JPG" alt="aws-image" %}

> 圖隊的緊密結合是 SaaS 服務的重點
