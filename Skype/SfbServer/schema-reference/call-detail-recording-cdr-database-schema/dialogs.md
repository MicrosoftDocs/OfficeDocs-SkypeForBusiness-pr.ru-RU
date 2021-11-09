---
title: Таблица диалогов Skype для бизнеса Server 2015 г.
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Таблица диалоговых диалогов — это вспомогательная таблица, которая хранит сведения о диалоговых и одноранговых сеансах.
ms.openlocfilehash: c59f3a2d84f4ebed243cba3dbe22f465551cbfaf
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60850682"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Таблица диалогов Skype для бизнеса Server 2015 г.
 
Таблица диалоговых диалогов — это вспомогательная таблица, которая хранит сведения о диалоговых и одноранговых сеансах.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Время запроса сеанса; используется совместно с SessionIDSeq для уникальной идентификации сеанса.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Идентификатор сеанса. Используется совместно с SessionIDTime для уникальной идентификации сеанса.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Checksum of the ExternalID. Это поле используется для увеличения скорости поиска баз данных.  <br/> |
|**ExternalId** <br/> |varbinary (775)  <br/> | <br/> |Код диалогового файла SIP, хранимый как двоичный. Формат двоичного:  <br/> диалоговое окно; от тега;до тега  <br/> Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

