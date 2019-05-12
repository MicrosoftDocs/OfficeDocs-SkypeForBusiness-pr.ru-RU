---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity содержит активные серверы чата в пул серверов сохраняемого чата.
ms.openlocfilehash: d780c2153b2e7f9f1ed5aad20217228e44f29504
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924810"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity содержит активные серверы чата в пул серверов сохраняемого чата.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Который  <br/> |int, не null  <br/> |Идентификатор сервера. Соответствует идентификатор экземпляра из хранилища централизованного управления.  <br/> |
|serverAddress  <br/> |nvarchar (256), отлично от null  <br/> |Адрес сервера с использованием адреса Windows Communication Foundation.  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |Время последнего обновления этой строки для подтверждения функционирования сервером канала.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|Который  <br/> |Первичный ключ.  <br/> |
   

