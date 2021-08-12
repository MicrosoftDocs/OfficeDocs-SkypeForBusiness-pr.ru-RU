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
ms.openlocfilehash: 6e4c891aefb41b88fdaae1e9d80a25f878042d14e06c94fe510414f6a24ac1a0
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54284499"
---
# <a name="sipresponsemetadata-table"></a>Таблица SIPResponseMetaData
 
Таблица SIPResponseMetaDataTable содержит список кодов ответа SIP, а также классификацию и определение каждого из этих кодов. Эти коды генерируются в ответ на события, затрагивающие устройства SIP и сеансы связи SIP; например, код ответа 403 создается, когда устройство SIP выполняет запрос, но сервер отказывается принять его на обработку.
  
Эта таблица была представлена Skype для бизнеса Server 2015 г.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ResponseCode** <br/> |int  <br/> |Primary  <br/> |Числовое значение, которое определяет код ответа SIP.  <br/> |
|**Class** <br/> |int  <br/> || Общая классификация кода ответа. Возможные классификации: <br/>  1 . Информационные ответы <br/>  2 . Успешные ответы <br/>  3 . Ответы на перенаправление <br/>  4 . Ответы на сбой клиента <br/>  5 . Ответы на сбой сервера <br/>  6 . Глобальный ответ на сбой <br/> |
|**Description** <br/> |nvarchar (256)  <br/> ||Описание кода ответа SIP. Например, для кода ответа 181 доступно следующее описание:  <br/> Вызов перенаправляется  <br/> |
   

