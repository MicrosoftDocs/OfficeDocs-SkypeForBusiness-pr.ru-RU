---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblsiopwhitelist — это список зарегистрированных надстроек, которые могут быть связаны с узлами.
ms.openlocfilehash: e5201fff31982da039d864adc4d29d900dbdcf99
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899717"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblsiopwhitelist — это список зарегистрированных надстроек, которые могут быть связаны с узлами.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**.|
|:-----|:-----|:-----|
|siopID  <br/> |Идентификатор GUID, не может быть null  <br/> |GUID надстройки.  <br/> |
|siopName  <br/> |nvarchar (50), отлично от null  <br/> |Отображаемое имя надстройки.  <br/> |
|siopUrl  <br/> |nvarchar (255), отлично от null  <br/> |URL-адрес надстройки.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**.|
|:-----|:-----|
|siopID  <br/> |Первичный ключ.  <br/> |
   

