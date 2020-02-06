---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: ТблпринЦипалмембердифференце содержит изменения членства в группах (добавленные и удаленные участники), которые еще не были обработаны в последующих шагах синхронизации доменных служб Active Directory.
ms.openlocfilehash: c7e965658c9e351a7a2d079921b7abe8166b48ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814077"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
ТблпринЦипалмембердифференце содержит изменения членства в группах (добавленные и удаленные участники), которые еще не были обработаны в последующих шагах синхронизации доменных служб Active Directory.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|прингуид  <br/> |GUID, а не NULL  <br/> |Идентификатор GUID участника измененной группы.  <br/> |
|мемберадпас  <br/> |nvarchar (256)  <br/> |Отличительное имя участника.  <br/> |
|мемберремовед  <br/> |bit, NOT NULL  <br/> |Значение false, если элемент был добавлен. Значение true, если элемент удален.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Прингуид, Мемберадпас\>  <br/> |Первичный ключ.  <br/> |
   

