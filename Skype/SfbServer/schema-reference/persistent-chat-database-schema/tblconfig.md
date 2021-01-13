---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig содержит неподдерживаемую конфигурацию сервера сохраняемой беседы в одной строке.
ms.openlocfilehash: 614e4e6514d695777c39a9d76482f775bd1a0981
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809739"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig содержит неподдерживаемую конфигурацию сервера сохраняемой беседы в одной строке.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), не равно null  <br/> |Содержит "pool."  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |Содержимое конфигурации.  <br/> |
|configPoolID  <br/> |GUID, не равно null  <br/> |Уникальный идентификатор экземпляра базы данных.  <br/> |
   
**Раздел**

|**Столбец**|**Описание**|
|:-----|:-----|
|configLabel  <br/> |Первичный ключ.  <br/> |
   

