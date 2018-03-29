---
title: tblConfig
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
ms.openlocfilehash: 099060f0957ae21c14b285eac1b753ad0b8c1719
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
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
   

