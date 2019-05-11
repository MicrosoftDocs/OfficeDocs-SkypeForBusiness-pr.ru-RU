---
title: Таблица sipresponsemetadata
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: SIPResponseMetaDataTable содержит список коды ответа SIP, классификации и определения каждого из этих кодов. Эти коды создаются в ответ на события, влияния на устройствах SIP и SIP-сеансов связи; Например код ответа 403 создается при устройства SIP выполняет запрос, но сервер отклоняет на обработку этого запроса.
ms.openlocfilehash: edd1f4e60376b367f701864ff15d334c4d971e47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930290"
---
# <a name="sipresponsemetadata-table"></a>Таблица sipresponsemetadata
 
SIPResponseMetaDataTable содержит список коды ответа SIP, классификации и определения каждого из этих кодов. Эти коды создаются в ответ на события, влияния на устройствах SIP и SIP-сеансов связи; Например код ответа 403 создается при устройства SIP выполняет запрос, но сервер отклоняет на обработку этого запроса.
  
Эта таблица была введена в Скайп для Business Server 2015.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |целое  <br/> |Primary  <br/> |Числовое значение, представляющее код ответа SIP.  <br/> |
|**Класс** <br/> |целое  <br/> || Общие классификации для кода ответа. Классификации строк, относятся: <br/>  1 — информационные ответы <br/>  2 — успешные ответы <br/>  3 - ответы перенаправления <br/>  4 - ответы сбоя клиента <br/>  5 — Ответы сбоя сервера <br/>  6 - глобального сбоя ответа <br/> |
|**Описание** <br/> |nvarchar(256)  <br/> ||Описание код ответа SIP. Например код ответа 181 имеет следующее описание:  <br/> Переадресация звонка  <br/> |
   

