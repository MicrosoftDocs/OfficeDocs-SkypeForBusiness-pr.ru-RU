---
title: tblConfig
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig содержит неподдерживаемую конфигурацию сохраняемой конфигурации chat Server в одной строке.
---

# <a name="tblconfig"></a>tblConfig
 
tblConfig содержит неподдерживаемую конфигурацию сохраняемой конфигурации chat Server в одной строке.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), не равно null  <br/> |Содержит "pool."  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |Содержимое конфигурации.  <br/> |
|configPoolID  <br/> |GUID, не равно null  <br/> |Уникальный идентификатор экземпляра базы данных.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|configLabel  <br/> |Первичный ключ.  <br/> |
   

