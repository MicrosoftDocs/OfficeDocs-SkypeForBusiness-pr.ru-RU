---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: Таблица tblPrincipalMembers содержит сведения о членстве субъектов.
ms.openlocfilehash: 2b2b9616c76095ec27178887e69dd482bcf6da92
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874254"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
Таблица tblPrincipalMembers содержит сведения о членстве субъектов.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**.|
|:-----|:-----|:-----|
|prinID  <br/> |int, не null  <br/> |Идентификатор субъекта.  <br/> |
|memberADPath  <br/> |nvarchar (384), отлично от null  <br/> |Различающееся имя члена. Член не нужно быть участником (в таблице tblPrincipal).  <br/> |
   
**Ключи**

|**Столбец**|**Описание**.|
|:-----|:-----|
|\<prinID memberADPath\>  <br/> |Первичный ключ.  <br/> |
|prinID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipal.prinID.  <br/> |
   

