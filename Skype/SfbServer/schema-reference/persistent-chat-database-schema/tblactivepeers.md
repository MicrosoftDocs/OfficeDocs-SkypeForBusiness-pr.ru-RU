---
title: tblActivePeers
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
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: Таблица tblActivePeers содержит текущие одноранговые соединения между службами чата.
---

# <a name="tblactivepeers"></a>tblActivePeers
 
Таблица tblActivePeers содержит текущие одноранговые соединения между службами чата.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, not null  <br/> |ИД сервера, добавившего запись.  <br/> |
|aplPeerID  <br/> |int, not null  <br/> |ИД узла, к которому подключен сервер, добавивший запись.  <br/> |
   
**Keys**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |Первичный ключ.  <br/> |
|aplServerID  <br/> |Внешний ключ с поиском в таблице tblServerIdentity.serverID.  <br/> |
|aplPeerID  <br/> |Внешний ключ с поиском в таблице tblServerIdentity.serverID.  <br/> |
   

