---
title: Таблица диалогов в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
description: Таблица диалогов представляет собой вспомогательную таблицу, в которой хранятся сведения об идентификаторах Dialogid для сеансов peer-to-peer.
ms.openlocfilehash: 379956a2c77c60a53e702913d81b25b41dc2fc23
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901131"
---
# <a name="dialogs-table-in-skype-for-business-server-2015"></a>Таблица диалогов в Скайп для Business Server 2015
 
Таблица диалогов представляет собой вспомогательную таблицу, в которой хранятся сведения об идентификаторах Dialogid для сеансов peer-to-peer.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Время запроса сеанса; используется совместно с SessionIDSeq для уникальной идентификации сеанса.  <br/> |
|**SessionIdSeq** <br/> |целое  <br/> |Primary  <br/> |Номер идентификатора для идентификации сеанса. Используется в сочетании с SessionIDTime для уникальной идентификации сеанса.  <br/> |
|**ExternalChecksum** <br/> |целое  <br/> | <br/> |Контрольная сумма ExternalID. Это поле используется для повышения скорости поиска по базе данных.  <br/> |
|**ExternalId** <br/> |varbinary(775)  <br/> | <br/> |SIP-идентификатор диалогового окна, сохраненной в качестве двоичного файла. Имеет формат двоичного файла:  <br/> диалоговое окно, из тега; для тега  <br/> Эти данные можно преобразовать в текстовый формат с помощью следующего синтаксиса:  <br/>  `cast(cast(ExternalId as varbinary(max)) as varchar(max))` <br/> |
   

