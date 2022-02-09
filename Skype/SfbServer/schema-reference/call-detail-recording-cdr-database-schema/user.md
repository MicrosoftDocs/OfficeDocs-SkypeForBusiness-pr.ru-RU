---
title: Представление пользователя
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: Представление User хранит информацию о пользователях, участвовавших в звонках или сеансах с записями в базе данных. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 448577f4379bc4db690569333c6d912f777e408e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62404511"
---
# <a name="user-view"></a>Представление пользователя
 
Представление User хранит информацию о пользователях, участвовавших в звонках или сеансах с записями в базе данных. Это представление было представлено в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Уникальный номер, идентифицирующий этого пользователя.  <br/> |
|UserUri  <br/> |nvarchar (450)  <br/> |URI пользователя.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Клиент пользователя. Дополнительные [сведения см. в таблице Tenants](tenants.md) . <br/> |
|UriType  <br/> |nvarchar (256)  <br/> |Тип URI пользователя. Дополнительные сведения [см. в таблице UriTypes](uritypes.md) . <br/> |
   

