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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
description: ТблкомплианцепартиЦипант включает текущих участников на канал и на сервер.
ms.openlocfilehash: 8f4b90cd7e8949451c2b6c1b9bc3cfabbab826e9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814647"
---
# <a name="tblcomplianceparticipant"></a>tblComplianceParticipant
 
ТблкомплианцепартиЦипант включает текущих участников на канал и на сервер.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|чаннелури  <br/> |nvarchar (255), NOT NULL  <br/> |Универсальный код ресурса (URI) канала.  <br/> |
|Идентификатора пользователя  <br/> |int, NOT NULL  <br/> |Идентификатор участника (соответствующий таблице ТблпринЦипал. Принид).  <br/> |
|жоинедат  <br/> |bigint, NOT NULL  <br/> |Метка времени присоединения к событию.  <br/> |
|партедат  <br/> |bigint  <br/> |NULL, если участник все еще присоединен. Метка времени события выхода канала, если значение не равно null.  <br/> Эти записи в конечном итоге удаляются, когда все переводчики обрабатывают событие.  <br/> |
|усерури  <br/> |nvarchar (255), NOT NULL  <br/> |URI пользователя.  <br/> |
|серверид  <br/> |целое  <br/> |Идентификация сервера (как в таблице Тблсерверидентити. Серверид).  <br/> |
|Идентификатор  <br/> |bigint  <br/> |Сеанс сервера. Это случайное число, которое генерируется каждый раз, когда запускается служба чата. Она используется для различения сеансов в целях идентификации потерянных участников.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Чаннелури, userId, Жоинедат\>  <br/> |Первичный ключ.  <br/> |
   

