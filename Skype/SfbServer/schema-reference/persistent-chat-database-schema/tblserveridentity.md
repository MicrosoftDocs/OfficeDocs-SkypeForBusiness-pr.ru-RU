---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity содержит активные серверы чата в пуле постоянных серверов чата.
ms.openlocfilehash: 65c9106584d6159421964da0329563cd263281ed
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768437"
---
# <a name="tblserveridentity"></a>tblServerIdentity
 
tblServerIdentity содержит активные серверы чата в пуле постоянных серверов чата.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|serverID  <br/> |целое, не равно null  <br/> |Идентификатор сервера. Соответствует ID экземпляра из магазина Central Management.  <br/> |
|serverAddress  <br/> |nvarchar (256), не равно null  <br/> |Адрес сервера с использованием адреса платформы Windows Communication Foundation.  <br/> |
|serverLastPingTime  <br/> |datetime  <br/> |Время последнего обновления этой строки сервером канала для подтверждения функционирования.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|serverID  <br/> |Первичный ключ.  <br/> |
   

