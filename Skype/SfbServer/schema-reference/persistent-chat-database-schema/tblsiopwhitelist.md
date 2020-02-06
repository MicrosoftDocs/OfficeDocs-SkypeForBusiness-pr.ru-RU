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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: Тблсиопвхителист — список зарегистрированных надстроек, которые можно связать с узлами.
ms.openlocfilehash: ae287a1a32b09ce309c688dac2a042913383a263
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812117"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
Тблсиопвхителист — список зарегистрированных надстроек, которые можно связать с узлами.
  
**Столбцов**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|сиопид  <br/> |GUID, а не NULL  <br/> |Идентификатор GUID надстройки.  <br/> |
|сиопнаме  <br/> |nvarchar (50), NOT NULL  <br/> |Отображаемое имя надстройки.  <br/> |
|сиопурл  <br/> |nvarchar (255), NOT NULL  <br/> |URL-адрес надстройки.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|сиопид  <br/> |Первичный ключ.  <br/> |
   

