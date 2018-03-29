---
title: tblServerIdentity
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity содержит активные серверы чата в пул серверов сохраняемого чата.
ms.openlocfilehash: 445021bb486d418011ea21dd32c0339e11b4d17a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
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
   

