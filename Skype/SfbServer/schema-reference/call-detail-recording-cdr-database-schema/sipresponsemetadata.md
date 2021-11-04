---
title: Таблица SIPResponseMetaData
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: Таблица SIPResponseMetaDataTable содержит список кодов ответа SIP, а также классификацию и определение каждого из этих кодов. Эти коды генерируются в ответ на события, затрагивающие устройства SIP и сеансы связи SIP; например, код ответа 403 создается, когда устройство SIP выполняет запрос, но сервер отказывается принять его на обработку.
ms.openlocfilehash: b0da53bded9f748643514a8235991d1124762ff9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761967"
---
# <a name="sipresponsemetadata-table"></a>Таблица SIPResponseMetaData
 
Таблица SIPResponseMetaDataTable содержит список кодов ответа SIP, а также классификацию и определение каждого из этих кодов. Эти коды генерируются в ответ на события, затрагивающие устройства SIP и сеансы связи SIP; например, код ответа 403 создается, когда устройство SIP выполняет запрос, но сервер отказывается принять его на обработку.
  
Эта таблица была представлена Skype для бизнеса Server 2015 г.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primary  <br/> |Числовое значение, которое определяет код ответа SIP.  <br/> |
|**Class** <br/> |int  <br/> || Общая классификация кода ответа. Возможные классификации: <br/>  1 . Информационные ответы <br/>  2 . Успешные ответы <br/>  3 . Ответы на перенаправление <br/>  4 . Ответы на сбой клиента <br/>  5 . Ответы на сбой сервера <br/>  6 . Глобальный ответ на сбой <br/> |
|**Описание** <br/> |nvarchar (256)  <br/> ||Описание кода ответа SIP. Например, для кода ответа 181 доступно следующее описание:  <br/> Вызов перенаправляется  <br/> |
   

