---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: ТблпринЦипалмемберс включает участников участника.
ms.openlocfilehash: 12c3bf86b7416665f0f2355af0bfc9f98e3c1f1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295288"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
ТблпринЦипалмемберс включает участников участника.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Принид  <br/> |int, NOT NULL  <br/> |Идентификатор участника.  <br/> |
|Мемберадпас  <br/> |nvarchar (384), NOT NULL  <br/> |Отличительное имя участника. Участник может не быть участником (в таблице ТблпринЦипал).  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Принид, Мемберадпас\>  <br/> |Первичный ключ.  <br/> |
|Принид  <br/> |Внешний ключ с подстановкой в ТблпринЦипал. Принид.  <br/> |
   

