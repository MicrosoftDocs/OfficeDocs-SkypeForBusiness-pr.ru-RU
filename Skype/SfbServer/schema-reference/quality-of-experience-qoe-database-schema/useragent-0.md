---
title: Представление UserAgent
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: Представление UserAgent хранит информацию об агентах пользователя, участвовавших в сеансах с записями в базе данных. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: c63873f219f5d741925339f52f949be55fc64411
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875006"
---
# <a name="useragent-view"></a>Представление UserAgent
 
Представление UserAgent хранит информацию об агентах пользователя, участвовавших в сеансах с записями в базе данных. В этом представлении была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |целое  <br/> |Уникальный номер, идентифицирующий этот агент пользователя.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Строка агента пользователя.  <br/> |
|UAType  <br/> |smallint  <br/> |Тип агента пользователя. В разделе [Таблица UserAgent](useragent.md) для получения дополнительных сведений. <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Категория, к которой принадлежит агента пользователя. Например агент пользователя Conferencing_Attendant_1.0 принадлежит UACategory CAA.  <br/> |
   

