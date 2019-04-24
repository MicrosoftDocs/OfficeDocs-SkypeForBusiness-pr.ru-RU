---
title: tblConfig
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig содержит несколько серверов сохраняемого чата неподдерживаемой конфигурации в одну строку.
ms.openlocfilehash: 9d28c0506b905975e2a72eeb83605fe4e32e7cfd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213069"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig содержит несколько серверов сохраняемого чата неподдерживаемой конфигурации в одну строку.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), отлично от null  <br/> |Содержит «pool».  <br/> |
|configContent  <br/> |nvarchar (максимум)  <br/> |Содержимое конфигурации.  <br/> |
|configPoolID  <br/> |Идентификатор GUID, не может быть null  <br/> |Уникальный идентификатор экземпляра базы данных.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|configLabel  <br/> |Первичный ключ.  <br/> |
   

