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
localization_priority: Normal
ms.assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
description: ТблскопепринЦипал включает области, назначенные узлам.
ms.openlocfilehash: 2fd8e434710c7bcd266c427fa492e23adacedb22
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295197"
---
# <a name="tblscopeprincipal"></a>tblScopePrincipal
 
ТблскопепринЦипал включает области, назначенные узлам.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Скопенодеид  <br/> |int, NOT NULL  <br/> |Идентификатор узла, к которому относится область.  <br/> |
|Скопепринид  <br/> |int, NOT NULL  <br/> |Идентификатор участника.  <br/> |
|Скопеисдениед  <br/> |bit, NOT NULL  <br/> |Значение true, если тип области — Deny; Значение false, если разрешено.  <br/> |
|Скопеупдатедби  <br/> |int, NOT NULL  <br/> |Идентификатор участника, который последним обновил эту запись.  <br/> |
   
**Параметры**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Скопенодеид, Скопепринид\>  <br/> |Первичный ключ.  <br/> |
|Скопенодеид  <br/> |Внешний ключ с подстановкой в таблице Тблноде. Нодеид.  <br/> |
|Скопепринид  <br/> |Внешний ключ с подстановкой в таблице ТблпринЦипал. Принид.  <br/> |
   

