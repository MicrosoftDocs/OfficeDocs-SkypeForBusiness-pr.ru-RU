---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: Таблица tblPrincipalMembers содержит сведения о членстве субъектов.
ms.openlocfilehash: f1763244620d8ffd0ed86837b18eabc97bc72781
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60749738"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
Таблица tblPrincipalMembers содержит сведения о членстве субъектов.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |ИД субъекта.  <br/> |
|memberADPath  <br/> |nvarchar (384), not null  <br/> |Различающееся имя участника. Участник не должен быть субъектом (в таблице tblPrincipal).  <br/> |
   
**Keys**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |Первичный ключ.  <br/> |
|prinID  <br/> |Внешний ключ для поиска в таблице tblPrincipal.prinID.  <br/> |
   

