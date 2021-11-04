---
title: Представление ClientVersions
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: В представлении ClientVersions сохраняются сведения о различных типах клиентов и версиях, которые участвовали в сеансах, зарегистрированных в базе данных. Каждая запись в этом представлении относится к одной версии клиента. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 91f206a482803cbecd2704638cffdff1aec5c8c8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740315"
---
# <a name="clientversions-view"></a>Представление ClientVersions
 
В представлении ClientVersions сохраняются сведения о различных типах клиентов и версиях, которые участвовали в сеансах, зарегистрированных в базе данных. Каждая запись в этом представлении относится к одной версии клиента. Это представление было представлено в Microsoft Lync Server 2013.
  
> [!NOTE]
> Возможно наличие нескольких записей для определенных столбцов. 
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**VersionId** <br/> |int  <br/> |Уникальный номер, идентифицирующий данный тип клиента и его версию.  <br/> |
|**Версия** <br/> |nvarchar (256)  <br/> |Служит для указания агента пользователя.  <br/> |
|**ClientType** <br/> |int  <br/> |Тип клиента.  <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Категория, к которой относится клиент. Например, клиент Conferencing_Attendant_1.0 относится к категории ClientCategory CAA.  <br/> |
   

