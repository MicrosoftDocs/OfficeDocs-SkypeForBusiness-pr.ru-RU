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
localization_priority: Normal
ms.assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
description: ТблпринЦипалроле включает явные роли, назначенные узлам.
ms.openlocfilehash: 9675713afba5753378f4d01b70489d0eee93b8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295239"
---
# <a name="tblprincipalrole"></a>tblPrincipalRole
 
ТблпринЦипалроле включает явные роли, назначенные узлам.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Принроленодеид  <br/> |int, NOT NULL  <br/> |Идентификатор узла, к которому относится роль.  <br/> |
|Принролепринид  <br/> |int, NOT NULL  <br/> |Идентификатор участника.  <br/> |
|Принролетипеид  <br/> |int, NOT NULL  <br/> |Идентификатор типа роли (из Тблролетипе).  <br/> |
|Принролеупдатедби  <br/> |int, NOT NULL  <br/> |Идентификатор участника, который последним обновил эту запись.  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Принроленодеид, Принролепринид, Принролетипеид\>  <br/> |Первичный ключ.  <br/> |
|Принроленодеид  <br/> |Внешний ключ с подстановкой в таблице Тблноде. Нодеид.  <br/> |
|Принролепринид  <br/> |Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.  <br/> |
|Принролетипеид  <br/> |Внешний ключ с подстановкой в таблице Тблролетипе. Ртипеид.  <br/> |
   

