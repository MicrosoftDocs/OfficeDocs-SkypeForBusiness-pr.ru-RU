---
title: Представление ClientVersions
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: Представление ClientVersions сохранение информации о различных типов клиентов и версии, которые участвовали в сеансах, записанные в базе данных. Каждая запись в представлении представляет одной версии клиента. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: abf1436a2c3309e95bec8371b586c017e11b816d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213398"
---
# <a name="clientversions-view"></a>Представление ClientVersions
 
Представление ClientVersions сохранение информации о различных типов клиентов и версии, которые участвовали в сеансах, записанные в базе данных. Каждая запись в представлении представляет одной версии клиента. В этом представлении была введена в Microsoft Lync Server 2013.
  
> [!NOTE]
> Возможно наличие нескольких записей для определенных столбцов. 
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**VersionId** <br/> |целое  <br/> |Уникальный номер, идентифицирующий этот тип и версию клиента.  <br/> |
|**Версия** <br/> |nvarchar(256)  <br/> |Представляет агент пользователя.  <br/> |
|**Типа клиента** <br/> |целое  <br/> |Тип клиента.  <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Категория, к которой принадлежит клиент. Например клиент Conferencing_Attendant_1.0 принадлежит ClientCategory CAA.  <br/> |
   

