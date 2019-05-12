---
title: Таблица TraceRoute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: Таблица TraceRoute содержит сведения о маршрутизации звонков. Эта таблица была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 77bb59f39a37aea437a902c848f4f07c662ef592
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33907047"
---
# <a name="traceroute-table"></a>Таблица TraceRoute
 
Таблица TraceRoute содержит сведения о маршрутизации звонков. Эта таблица была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Основной, внешний  <br/> |Дата и время начала вызова.  <br/> |
|**SessionSeq** <br/> |целое  <br/> |Основной, внешний  <br/> |Уникальный идентификатор для однозначной идентификации звонков, которые могут начаться на тот же день и в то же время.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Основной, внешний  <br/> |Представляет тип видео строки, используемой в вызове. Допустимые значения:  <br/> 0 — аудио  <br/> 1 — видео  <br/> 2 — панорамное видео  <br/> 3 - приложения и доступ к рабочему столу  <br/> |
|**FromCaller** <br/> |бит  <br/> |Primary  <br/> |Конечная точка, выполнившим вызов.  <br/> |
|**Перехода** <br/> |целое  <br/> ||Переход между сетями /  <br/> |
|**IPAddressKey** <br/> |целое  <br/> |Внешний  <br/> |Уникальный идентификатор для IP-адреса. IP-адресе хранится в [таблице IP-адрес](ipaddress.md).  <br/> |
|**КРУГОВОЙ ПУТЬ** <br/> |целое  <br/> ||Время цикла. Время цикла измеряет время, необходимое для пакета голосовой связи, ее назначению, а затем отправьте обратная было получено уведомление.  <br/> |
   

