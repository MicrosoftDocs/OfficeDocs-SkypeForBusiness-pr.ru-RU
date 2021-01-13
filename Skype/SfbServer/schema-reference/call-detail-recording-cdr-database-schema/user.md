---
title: Представление пользователя
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
ms.assetid: 796f77e6-1da6-4969-b18b-3537209a1fe4
description: Представление User хранит информацию о пользователях, участвовавших в звонках или сеансах с записями в базе данных. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: 03af849f9185d90d1c7888c1946b47ee2ef38db4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831699"
---
# <a name="user-view"></a>Представление пользователя
 
Представление User хранит информацию о пользователях, участвовавших в звонках или сеансах с записями в базе данных. Это представление впервые было введено в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Details**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Уникальный номер, идентифицирующий этого пользователя.  <br/> |
|UserUri  <br/> |nvarchar(450)  <br/> |URI пользователя.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Клиент пользователя. Дополнительные [сведения см. в](tenants.md) таблице Tenants. <br/> |
|UriType  <br/> |nvarchar(256)  <br/> |Тип URI пользователя. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
   

