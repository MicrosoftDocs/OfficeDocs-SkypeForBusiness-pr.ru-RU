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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: ТблпринЦипалмемберс включает участников участника.
ms.openlocfilehash: c56ab16f96322cb295c4eff6fc63e01ba887dd22
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813947"
---
# <a name="tblprincipalmembers"></a>tblPrincipalMembers
 
ТблпринЦипалмемберс включает участников участника.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|принид  <br/> |int, NOT NULL  <br/> |Идентификатор участника.  <br/> |
|мемберадпас  <br/> |nvarchar (384), NOT NULL  <br/> |Отличительное имя участника. Участник может не быть участником (в таблице ТблпринЦипал).  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Принид, Мемберадпас\>  <br/> |Первичный ключ.  <br/> |
|принид  <br/> |Внешний ключ с подстановкой в ТблпринЦипал. Принид.  <br/> |
   

