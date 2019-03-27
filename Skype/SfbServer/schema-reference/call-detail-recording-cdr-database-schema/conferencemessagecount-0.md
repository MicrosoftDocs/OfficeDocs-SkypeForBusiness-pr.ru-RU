---
title: Представление ConferenceMessageCount
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: Представление ConferenceMessageCount содержит сведения о количества сообщений — пользователя к конференции. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: f2290eef7d2738831ed3ce72c794a36659858b8b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874076"
---
# <a name="conferencemessagecount-view"></a>Представление ConferenceMessageCount
 
Представление ConferenceMessageCount содержит сведения о количества сообщений — пользователя к конференции. В этом представлении была введена в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление ConferenceMessageCount содержит все столбцы [ConferenceSessionDetails view](conferencesessiondetails.md) в дополнение к этому столбцов, перечисленных ниже.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |URI пользователя, отправившего сообщение.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Тип URI пользователя, отправившего сообщение. В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см. <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Клиент пользователя, отправившего сообщение. В [таблице клиентов](tenants.md) для получения дополнительных сведений см. <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Число сообщений, отправленных пользователем во время сеанса конференц-связи.  <br/> |
   

