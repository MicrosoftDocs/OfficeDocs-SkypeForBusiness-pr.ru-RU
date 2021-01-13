---
title: Таблица Dialogs в Skype для бизнеса Server 2015
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Таблица Dialogs — это вспомогательная таблица, в которую хранится информация о DialogID для одноранговых сеансов.
ms.openlocfilehash: a4f0bb8c63e165985ef09af8f9aafa071529bf1f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816049"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Таблица Dialogs в Skype для бизнеса Server 2015
 
Таблица Dialogs — это вспомогательная таблица, в которую хранится информация о DialogID для одноранговых сеансов.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Время запроса сеанса; используется в сочетании с SessionIDSeq для уникальной идентификации сеанса.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Идентификатор сеанса. Используется в сочетании с SessionIDTime для уникальной идентификации сеанса.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Контрольная контрольнаямбла ExternalID. Это поле используется для повышения скорости поиска в базе данных.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |Код диалога SIP, хранимый в двоичном файле. Двоичный формат:  <br/> dialog;from-tag;to-tag  <br/> Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

