---
title: Таблица sipresponsemetadata
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable содержит список коды ответа SIP, классификации и определения каждого из этих кодов. Эти коды создаются в ответ на события, влияния на устройствах SIP и SIP-сеансов связи; Например код ответа 403 создается при устройства SIP выполняет запрос, но сервер отклоняет на обработку этого запроса.
ms.openlocfilehash: a90a248837dd705746fe3b342874aad10480e8a6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="sipresponsemetadata-table"></a>Таблица sipresponsemetadata
 
SIPResponseMetaDataTable содержит список коды ответа SIP, классификации и определения каждого из этих кодов. Эти коды создаются в ответ на события, влияния на устройствах SIP и SIP-сеансов связи; Например код ответа 403 создается при устройства SIP выполняет запрос, но сервер отклоняет на обработку этого запроса.
  
Эта таблица была введена в Скайп для Business Server 2015.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |целое  <br/> |Primary  <br/> |Числовое значение, представляющее код ответа SIP.  <br/> |
|**Класс** <br/> |целое  <br/> || Общие классификации для кода ответа. Классификации строк, относятся: <br/>  1 — информационные ответы <br/>  2 — успешные ответы <br/>  3 - ответы перенаправления <br/>  4 - ответы сбоя клиента <br/>  5 — Ответы сбоя сервера <br/>  6 - глобального сбоя ответа <br/> |
|**Описание** <br/> |nvarchar(256)  <br/> ||Описание код ответа SIP. Например код ответа 181 имеет следующее описание:  <br/> Переадресация звонка  <br/> |
   

