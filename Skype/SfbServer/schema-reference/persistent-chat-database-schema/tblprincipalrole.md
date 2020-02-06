---
title: tblPrincipalRole
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
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: ТблпринЦипалроле включает явные роли, назначенные узлам.
ms.openlocfilehash: 1cc606ec3825bb664d4123154e97fabb15678cfd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813367"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
ТблпринЦипалроле включает явные роли, назначенные узлам.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|принроленодеид  <br/> |int, NOT NULL  <br/> |Идентификатор узла, к которому относится роль.  <br/> |
|принролепринид  <br/> |int, NOT NULL  <br/> |Идентификатор участника.  <br/> |
|принролетипеид  <br/> |int, NOT NULL  <br/> |Идентификатор типа роли (из Тблролетипе).  <br/> |
|принролеупдатедби  <br/> |int, NOT NULL  <br/> |Идентификатор участника, который последним обновил эту запись.  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Принроленодеид, Принролепринид, Принролетипеид\>  <br/> |Первичный ключ.  <br/> |
|принроленодеид  <br/> |Внешний ключ с подстановкой в таблице Тблноде. Нодеид.  <br/> |
|принролепринид  <br/> |Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.  <br/> |
|принролетипеид  <br/> |Внешний ключ с подстановкой в таблице Тблролетипе. Ртипеид.  <br/> |
   

