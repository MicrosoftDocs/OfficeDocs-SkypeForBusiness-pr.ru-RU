---
title: tblActivePeers
ms.reviewer: ''
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
ms.openlocfilehash: e921d6faa4f7bcf3e3c6f6dc9859f4bd0db16bc5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884169"
---
# <a name="tblactivepeers"></a>tblActivePeers
 
Таблица tblActivePeers содержит текущие peer-to-peer соединения между службами чата.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**.|
|:-----|:-----|:-----|
|aplServerID  <br/> |int, не null  <br/> |Идентификатор сервера, добавившего запись.  <br/> |
|aplPeerID  <br/> |int, не null  <br/> |ИД узла, который подключен сервер учета.  <br/> |
   
**Ключи**

|**Столбец**|**Описание**.|
|:-----|:-----|
|\<aplServerID aplPeerID\>  <br/> |Первичный ключ.  <br/> |
|aplServerID  <br/> |Внешний ключ с поиском в таблице tblServerIdentity.serverID.  <br/> |
|aplPeerID  <br/> |Внешний ключ с поиском в таблице tblServerIdentity.serverID.  <br/> |
   

