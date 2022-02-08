---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: Таблица tblPrincipalMembers содержит сведения о членстве субъектов.
ms.openlocfilehash: 77377a98e7dcf336eb05deb68c170de0c58a1223
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62389057"
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
   

