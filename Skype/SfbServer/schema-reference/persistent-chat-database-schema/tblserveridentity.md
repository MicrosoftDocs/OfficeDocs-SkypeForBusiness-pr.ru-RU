---
title: tblServerIdentity
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 0207871100904af348b4c1a51ed2c6f4574249d4
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398613"
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
   

