---
title: tblScopePrincipal
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
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: ТблскопепринЦипал включает области, назначенные узлам.
ms.openlocfilehash: 24a38ef4acf3e0d500c7652f5ca418af585343b6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812447"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
ТблскопепринЦипал включает области, назначенные узлам.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|скопенодеид  <br/> |int, NOT NULL  <br/> |Идентификатор узла, к которому относится область.  <br/> |
|скопепринид  <br/> |int, NOT NULL  <br/> |Идентификатор участника.  <br/> |
|скопеисдениед  <br/> |bit, NOT NULL  <br/> |Значение true, если тип области — Deny; Значение false, если разрешено.  <br/> |
|скопеупдатедби  <br/> |int, NOT NULL  <br/> |Идентификатор участника, который последним обновил эту запись.  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Скопенодеид, Скопепринид\>  <br/> |Первичный ключ.  <br/> |
|скопенодеид  <br/> |Внешний ключ с подстановкой в таблице Тблноде. Нодеид.  <br/> |
|скопепринид  <br/> |Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.  <br/> |
   

