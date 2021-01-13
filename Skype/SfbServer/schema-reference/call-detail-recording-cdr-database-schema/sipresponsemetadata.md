---
title: Таблица SIPResponseMetaData
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: Таблица SIPResponseMetaDataTable содержит список кодов ответа SIP, а также классификацию и определение каждого из этих кодов. Эти коды генерируются в ответ на события, затрагивающие устройства SIP и сеансы связи SIP; например, код ответа 403 создается, когда устройство SIP выполняет запрос, но сервер отказывается принять его на обработку.
ms.openlocfilehash: 3d6714e9c5b5c154d19381fad33821b02ec8a73e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809929"
---
# <a name="sipresponsemetadata-table"></a>Таблица SIPResponseMetaData
 
Таблица SIPResponseMetaDataTable содержит список кодов ответа SIP, а также классификацию и определение каждого из этих кодов. Эти коды генерируются в ответ на события, затрагивающие устройства SIP и сеансы связи SIP; например, код ответа 403 создается, когда устройство SIP выполняет запрос, но сервер отказывается принять его на обработку.
  
Эта таблица была представлена в Skype для бизнеса Server 2015.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primary  <br/> |Числовое значение, которое определяет код ответа SIP.  <br/> |
|**Class** <br/> |int  <br/> || Общая классификация кода ответа. Возможные классификации: <br/>  1 — информационные ответы <br/>  2 — успешные ответы <br/>  3 — ответы на перенаправление <br/>  4 — ответы на сбои клиентов <br/>  5 — ответы на сбои сервера <br/>  6 — глобальный ответ на сбой <br/> |
|**Описание** <br/> |nvarchar(256)  <br/> ||Описание кода ответа SIP. Например, для кода ответа 181 доступно следующее описание:  <br/> Вызов перенаправляется  <br/> |
   

