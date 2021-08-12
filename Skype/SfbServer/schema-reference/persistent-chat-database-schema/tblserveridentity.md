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
description: tblServerIdentity содержит активные серверы чата в пуле постоянных серверов чата.
ms.openlocfilehash: 092331f275ef76372ad1bd2d2462acb9eb7848eea263d59c2276d7a4b6a83779
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303662"
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
   

