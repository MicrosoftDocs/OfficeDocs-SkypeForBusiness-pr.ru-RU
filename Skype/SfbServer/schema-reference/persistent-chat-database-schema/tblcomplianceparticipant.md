---
title: tblComplianceParticipant
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: ТблкомплианцепартиЦипант включает текущих участников на канал и на сервер.
ms.openlocfilehash: bf6913d8bcc11db1589169c4479cec4a0238825d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295463"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
ТблкомплианцепартиЦипант включает текущих участников на канал и на сервер.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Чаннелури  <br/> |nvarchar (255), NOT NULL  <br/> |Универсальный код ресурса (URI) канала.  <br/> |
|Идентификатора пользователя  <br/> |int, NOT NULL  <br/> |Идентификатор участника (соответствующий таблице ТблпринЦипал. Принид).  <br/> |
|Жоинедат  <br/> |bigint, NOT NULL  <br/> |Метка времени присоединения к событию.  <br/> |
|Партедат  <br/> |bigint  <br/> |NULL, если участник все еще присоединен. Метка времени события выхода канала, если значение не равно null.  <br/> Эти записи в конечном итоге удаляются, когда все переводчики обрабатывают событие.  <br/> |
|Усерури  <br/> |nvarchar (255), NOT NULL  <br/> |URI пользователя.  <br/> |
|Серверид  <br/> |целое  <br/> |Идентификация сервера (как в таблице Тблсерверидентити. Серверид).  <br/> |
|Идентификатор  <br/> |bigint  <br/> |Сеанс сервера. Это случайное число, которое генерируется каждый раз, когда запускается служба чата. Она используется для различения сеансов в целях идентификации потерянных участников.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Чаннелури, userId, Жоинедат\>  <br/> |Первичный ключ.  <br/> |
   

