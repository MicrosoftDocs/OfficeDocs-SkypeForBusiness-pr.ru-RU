---
title: tblPrincipalMembers
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
ms.localizationpriority: medium
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: Таблица tblPrincipalMembers содержит сведения о членстве субъектов.
ms.openlocfilehash: e35b64a34114a7135133175211ecec5a806332b6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58626461"
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
   

