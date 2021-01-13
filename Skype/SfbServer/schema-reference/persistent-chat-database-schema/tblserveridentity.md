---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity содержит активные серверы чата в пуле серверов сохраняемого чата.
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831499"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity содержит активные серверы чата в пуле серверов сохраняемого чата.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|serverID  <br/> |целое, не равно null  <br/> |Идентификатор сервера. Соответствует ИД экземпляра из центрального банка управления.  <br/> |
|serverAddress  <br/> |nvarchar (256), не равно null  <br/> |Адрес сервера с использованием адреса платформы Windows Communication Foundation.  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |Время последнего обновления этой строки сервером канала для подтверждения функционирования.  <br/> |
   
**Раздел**

|**Столбец**|**Описание**|
|:-----|:-----|
|serverID  <br/> |Первичный ключ.  <br/> |
   

