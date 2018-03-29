---
title: Таблица tblActivePeers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: Таблица tblActivePeers содержит текущие peer-to-peer соединения между службами чата.
ms.openlocfilehash: 5dc585a8db67c1bbdcc1c3933018b1296fd75484
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblactivepeers"></a>Таблица tblActivePeers
 
Таблица tblActivePeers содержит текущие peer-to-peer соединения между службами чата.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, не null  <br/> |Идентификатор сервера, добавившего запись.  <br/> |
|aplPeerID  <br/> |int, не null  <br/> |ИД узла, который подключен сервер учета.  <br/> |
   
**Ключи**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<aplServerID aplPeerID\>  <br/> |Первичный ключ.  <br/> |
|aplServerID  <br/> |Внешний ключ с поиском в таблице tblServerIdentity.serverID.  <br/> |
|aplPeerID  <br/> |Внешний ключ с поиском в таблице tblServerIdentity.serverID.  <br/> |
   

