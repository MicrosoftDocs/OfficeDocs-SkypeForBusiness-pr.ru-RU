---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList — это список зарегистрированных надстроек, которые могут быть связаны с узлами.
ms.openlocfilehash: 3f1ad0461bc227970d4a2a0864dbc6318ef0af32d854402180321bab74aa91e5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305381"
---
# <a name="tblsiopwhitelist"></a>tblSiopWhiteList
 
tblSiopWhiteList — это список зарегистрированных надстроек, которые могут быть связаны с узлами.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|siopID  <br/> |GUID, отлично от null  <br/> |GUID надстройки.  <br/> |
|siopName  <br/> |nvarchar (50), отлично от null  <br/> |Отображаемое имя надстройки.  <br/> |
|siopUrl  <br/> |nvarchar (255), отлично от null  <br/> |URL-адрес надстройки.  <br/> |
   
**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|siopID  <br/> |Первичный ключ.  <br/> |
   

