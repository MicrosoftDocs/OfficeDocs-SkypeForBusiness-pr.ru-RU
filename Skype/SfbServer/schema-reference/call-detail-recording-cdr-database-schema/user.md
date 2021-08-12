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
description: Представление User хранит информацию о пользователях, участвовавших в звонках или сеансах с записями в базе данных. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 200280f6a82a50490aee77177464b435e647a0a44852ca0db5b59c64bda836f3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302253"
---
# <a name="user-view"></a>Представление пользователя
 
Представление User хранит информацию о пользователях, участвовавших в звонках или сеансах с записями в базе данных. Это представление было представлено в Microsoft Lync Server 2013.
  
|**Column**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|UserId  <br/> |int  <br/> |Уникальный номер, идентифицирующий этого пользователя.  <br/> |
|UserUri  <br/> |nvarchar (450)  <br/> |URI пользователя.  <br/> |
|TenantKey  <br/> |uniqueidentifier  <br/> |Клиент пользователя. Дополнительные сведения см. в таблице [Tenants.](tenants.md) <br/> |
|UriType  <br/> |nvarchar (256)  <br/> |Тип URI пользователя. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
   

