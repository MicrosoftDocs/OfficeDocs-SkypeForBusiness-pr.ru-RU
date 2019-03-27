---
title: Представление пользователя
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: Представление пользователя хранятся сведения о пользователях, которые не связаны звонков или сеансах с записями в базе данных. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 9e631c101660e8f14bca25f019f5d991a0d9aadd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877645"
---
# <a name="user-view"></a>Представление пользователя
 
Представление пользователя хранятся сведения о пользователях, которые не связаны звонков или сеансах с записями в базе данных. В этом представлении была введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|Идентификатор пользователя  <br/> |целое  <br/> |Уникальный номер, идентифицирующий этого пользователя.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI пользователя.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Клиент пользователя. В [таблице клиентов](tenants.md) для получения дополнительных сведений см. <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Тип URI пользователя. В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см. <br/> |
   

