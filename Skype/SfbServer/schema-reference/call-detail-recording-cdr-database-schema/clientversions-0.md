---
title: Представление ClientVersions
ms.reviewer: null
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: 'В представлении ClientVersions сохраняются сведения о различных типах клиентов и версиях, которые участвовали в сеансах, зарегистрированных в базе данных. Каждая запись в этом представлении относится к одной версии клиента. Это представление было представлено в Microsoft Lync Server 2013.'
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
   

