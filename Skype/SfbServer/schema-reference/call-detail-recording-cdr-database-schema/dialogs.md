---
title: Таблица диалогов Skype для бизнеса Server 2015 г.
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
description: Таблица диалоговых диалогов — это вспомогательная таблица, которая хранит сведения о диалоговых и одноранговых сеансах.
ms.openlocfilehash: 368abb6131367434edbdf1fe142a376fe9a155277eec8b369482545146dbdc3b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302283"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Таблица диалогов Skype для бизнеса Server 2015 г.
 
Таблица диалоговых диалогов — это вспомогательная таблица, которая хранит сведения о диалоговых и одноранговых сеансах.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Время запроса сеанса; используется совместно с SessionIDSeq для уникальной идентификации сеанса.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Идентификатор сеанса. Используется совместно с SessionIDTime для уникальной идентификации сеанса.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Checksum of the ExternalID. Это поле используется для увеличения скорости поиска баз данных.  <br/> |
|**ExternalId** <br/> |varbinary (775)  <br/> | <br/> |Код диалогового файла SIP, хранимый как двоичный. Формат двоичного:  <br/> диалоговое окно; от тега;до тега  <br/> Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

