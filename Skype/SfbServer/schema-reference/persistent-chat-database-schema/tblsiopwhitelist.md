---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: 43277bec50baa3224d52aa247e20d417104b16e6
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398595"
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
   

