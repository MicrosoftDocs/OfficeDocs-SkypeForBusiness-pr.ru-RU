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
ms.localizationpriority: medium
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: tblSiopWhiteList — это список зарегистрированных надстроек, которые могут быть связаны с узлами.
ms.openlocfilehash: 78cc98f584f20d3a08e9ed750ed9ac406f7e5780
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613829"
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
   

