---
title: Представление ConferenceMessageCount
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: Представление ConferenceMessageCount содержит сведения о количества сообщений — пользователя к конференции. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: ce94cd13637b70b87a92fd688ca8ce8aefd2c69e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901417"
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
   

