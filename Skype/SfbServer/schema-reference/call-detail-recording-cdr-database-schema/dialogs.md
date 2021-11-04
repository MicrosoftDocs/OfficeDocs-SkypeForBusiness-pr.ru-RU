---
title: Таблица диалогов Skype для бизнеса Server 2015 г.
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
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Таблица диалоговых диалогов — это вспомогательная таблица, которая хранит сведения о диалоговых и одноранговых сеансах.
ms.openlocfilehash: 9aaf2691e3869830e2ccc605475d856517d1fe8b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743965"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Таблица диалогов Skype для бизнеса Server 2015 г.
 
Таблица диалоговых диалогов — это вспомогательная таблица, которая хранит сведения о диалоговых и одноранговых сеансах.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Время запроса сеанса; используется совместно с SessionIDSeq для уникальной идентификации сеанса.  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Идентификатор сеанса. Используется совместно с SessionIDTime для уникальной идентификации сеанса.  <br/> |
|**ExternalChecksum** <br/> |int  <br/> | <br/> |Checksum of the ExternalID. Это поле используется для увеличения скорости поиска баз данных.  <br/> |
|**ExternalId** <br/> |varbinary (775)  <br/> | <br/> |Код диалогового файла SIP, хранимый как двоичный. Формат двоичного:  <br/> диалоговое окно; от тега;до тега  <br/> Эти данные можно преобразовать в текстовый формат, используя следующий синтаксис:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

