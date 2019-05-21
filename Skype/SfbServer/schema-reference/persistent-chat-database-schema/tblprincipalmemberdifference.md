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
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: ТблпринЦипалмембердифференце содержит изменения членства в группах (добавленные и удаленные участники), которые еще не были обработаны в последующих шагах синхронизации доменных служб Active Directory.
ms.openlocfilehash: 18d0f3f5c8700db0bb81470f5ee90851e8d277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295302"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
ТблпринЦипалмембердифференце содержит изменения членства в группах (добавленные и удаленные участники), которые еще не были обработаны в последующих шагах синхронизации доменных служб Active Directory.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Прингуид  <br/> |GUID, а не NULL  <br/> |Идентификатор GUID участника измененной группы.  <br/> |
|Мемберадпас  <br/> |nvarchar (256)  <br/> |Отличительное имя участника.  <br/> |
|Мемберремовед  <br/> |bit, NOT NULL  <br/> |Значение false, если элемент был добавлен. Значение true, если элемент удален.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Прингуид, Мемберадпас\>  <br/> |Первичный ключ.  <br/> |
   

