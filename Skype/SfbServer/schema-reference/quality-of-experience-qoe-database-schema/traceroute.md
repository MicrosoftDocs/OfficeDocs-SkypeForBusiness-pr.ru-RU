---
title: Таблица TraceRoute
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: Таблица TraceRoute содержит сведения о маршрутизации звонков. Эта таблица была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 741eaabbe94ee1849bd5a7d5e516714861658d7e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884903"
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
   

