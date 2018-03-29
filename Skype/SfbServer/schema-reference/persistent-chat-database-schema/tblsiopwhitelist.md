---
title: tblsiopwhitelist —
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
ms.openlocfilehash: 0653ec7f4a663479f7b7d4787eee4dc0a1045aac
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="tblsiopwhitelist"></a>tblsiopwhitelist —
 
tblsiopwhitelist — это список зарегистрированных надстроек, которые могут быть связаны с узлами.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|siopID  <br/> |Идентификатор GUID, не может быть null  <br/> |GUID надстройки.  <br/> |
|siopName  <br/> |nvarchar (50), отлично от null  <br/> |Отображаемое имя надстройки.  <br/> |
|siopUrl  <br/> |nvarchar (255), отлично от null  <br/> |URL-адрес надстройки.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|siopID  <br/> |Первичный ключ.  <br/> |
   

