---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
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
ms.openlocfilehash: d2d28c70cbb1bc35acdeca4739a667a5e991e52f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756309"
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
   

