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
description: tblConfig содержит неподдерживаемую конфигурацию сохраняемой конфигурации chat Server в одной строке.
ms.openlocfilehash: 0e9cc0a0c4686432032591aa0c380b303fc5251a56a6c983a1e10b009e0eb28a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278357"
---
# <a name="tblconfig"></a>tblConfig
 
tblConfig содержит неподдерживаемую конфигурацию сохраняемой конфигурации chat Server в одной строке.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|configLabel  <br/> |nvarchar (255), не равно null  <br/> |Содержит "pool."  <br/> |
|configContent  <br/> |nvarchar (max)  <br/> |Содержимое конфигурации.  <br/> |
|configPoolID  <br/> |GUID, не равно null  <br/> |Уникальный идентификатор экземпляра базы данных.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|configLabel  <br/> |Первичный ключ.  <br/> |
   

