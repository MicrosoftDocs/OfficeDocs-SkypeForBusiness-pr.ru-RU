---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: Тблсерверидентити включает в себя серверы активных чатов в пуле серверов сохраняемого чата.
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295190"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
Тблсерверидентити включает в себя серверы активных чатов в пуле серверов сохраняемого чата.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Серверид  <br/> |int, NOT NULL  <br/> |Идентификатор сервера. Соответствует ИДЕНТИФИКАТОРу экземпляра из хранилища центрального управления.  <br/> |
|Сервераддресс  <br/> |nvarchar (256), NOT NULL  <br/> |Адрес сервера с использованием адреса Windows Communication Foundation.  <br/> |
|Серверластпингтиме  <br/> |datetime  <br/> |Последнее время, в течение которого сервер канала обновил эту строку, чтобы дать свидетельство о том, что оно запущено.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|Серверид  <br/> |Первичный ключ.  <br/> |
   

