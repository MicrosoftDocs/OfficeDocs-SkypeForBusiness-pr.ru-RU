---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: Тблсиопвхителист — список зарегистрированных надстроек, которые можно связать с узлами.
ms.openlocfilehash: 3277ec3a2d4fe11000b2eda60fa2327547c77d2b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295176"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
Тблсиопвхителист — список зарегистрированных надстроек, которые можно связать с узлами.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|Сиопид  <br/> |GUID, а не NULL  <br/> |Идентификатор GUID надстройки.  <br/> |
|Сиопнаме  <br/> |nvarchar (50), NOT NULL  <br/> |Отображаемое имя надстройки.  <br/> |
|Сиопурл  <br/> |nvarchar (255), NOT NULL  <br/> |URL-адрес надстройки.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|Сиопид  <br/> |Первичный ключ.  <br/> |
   

