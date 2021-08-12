---
title: Таблица EdgeServers в Skype для бизнеса Server 2015 г.
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
ms.assetid: aeda8c01-c88c-4f56-b3d0-bac475fae449
description: Таблица EdgeServers — это вспомогательная таблица. Каждая запись хранит сведения об одном edge Server, который участвует в вызовах с записями в базе данных.
ms.openlocfilehash: 993cdc5801a14feea904bfaaad97004f95579ce4b87b7131e24afc1bc9212de3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54347784"
---
# <a name="edgeservers-table-in-skype-for-business-server-2015"></a>Таблица EdgeServers в Skype для бизнеса Server 2015 г.
 
Таблица EdgeServers — это вспомогательная таблица. Каждая запись хранит сведения об одном edge Server, который участвует в вызовах с записями в базе данных.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**EdgeServerId** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий этот edge Server.  <br/> |
|**EdgeServer** <br/> |nvarchar (256)  <br/> | <br/> |Имя Edge Server.  <br/> |
   

