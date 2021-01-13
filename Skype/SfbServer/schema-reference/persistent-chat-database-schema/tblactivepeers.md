---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: Таблица tblActivePeers содержит текущие одноранговые соединения между службами чата.
ms.openlocfilehash: befba4086a78281fbfbec1e270b7c8e3f8174752
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812939"
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
   

