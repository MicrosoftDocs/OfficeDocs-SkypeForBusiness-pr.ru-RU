---
title: Таблица TraceRoute
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: Таблица TraceRoute содержит сведения о маршрутизации звонков. Эта таблица была представлена в Microsoft Lync Server 2013.
ms.openlocfilehash: 7ecad93cca80a9b7cea73f64158b3c0008a1d6e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831329"
---
# <a name="traceroute-table"></a>Таблица TraceRoute
 
Таблица TraceRoute содержит сведения о маршрутизации звонков. Эта таблица была представлена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Первичный, внешний  <br/> |Дата и время начала звонка.  <br/> |
|**SessionSeq** <br/> |int  <br/> |Первичный, внешний  <br/> |Уникальный идентификатор, используемых для однозначной идентификации звонков, которые могут начаться одновременно.  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Основной, внешний  <br/> |Представляет тип видеоканала, используемого для звонка. Допускаются следующие значения:  <br/> 0 — звук  <br/> 1 — видео  <br/> 2 — панорамное видео  <br/> 3 — общий доступ к приложениям и рабочему столу  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primary  <br/> |Конечная точка, выполнившая звонок.  <br/> |
|**Hop** <br/> |int  <br/> ||Переход между сетями.  <br/> |
|**IPAddressKey** <br/> |int  <br/> |Внешняя  <br/> |Уникальный идентификатор IP-адреса. Сведения об IP-адресах хранятся в [таблице IPAddress.](ipaddress.md)  <br/> |
|**RTT** <br/> |int  <br/> ||Время цикла. Это время, которое требуется на то, чтобы пакет с голосовыми данными достиг назначения и отправил обратно уведомление о том, что он был получен.  <br/> |
   

