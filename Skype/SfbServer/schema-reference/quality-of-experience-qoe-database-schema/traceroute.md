---
title: Таблица TraceRoute
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: Таблица TraceRoute содержит сведения о маршрутизации звонков. Эта таблица была представлена в Microsoft Lync Server 2013.
ms.openlocfilehash: 8a4ca952bb2b6ced61f4b1aae6745a5e1b68d417
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60840921"
---
# <a name="traceroute-table"></a>Таблица TraceRoute
 
Таблица TraceRoute содержит сведения о маршрутизации звонков. Эта таблица была представлена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Первичный, внешний  <br/> |Дата и время начала звонка.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Первичный, внешний  <br/> |Уникальный идентификатор, используемых для однозначной идентификации звонков, которые могут начаться одновременно.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Основной, внешний  <br/> |Представляет тип видеоканала, используемого для звонка. Допускаются следующие значения:  <br/> 0 - Аудио  <br/> 1 - Видео  <br/> 2 . Панорамное видео  <br/> 3 . Совместное использование приложений и настольных компьютеров  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |Конечная точка, выполнившая звонок.  <br/> |
|**Hop** <br/> |int  <br/> ||Переход между сетями.  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Foreign  <br/> |Уникальный идентификатор IP-адреса. Сведения об IP-адресе хранятся в [таблице IPAddress.](ipaddress.md)  <br/> |
|**RTT** <br/> |int  <br/> ||Время цикла. Это время, которое требуется на то, чтобы пакет с голосовыми данными достиг назначения и отправил обратно уведомление о том, что он был получен.  <br/> |
   

