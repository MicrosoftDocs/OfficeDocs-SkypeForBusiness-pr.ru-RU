---
title: Представление ConferenceMessageCount
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: В представлении ConferenceMessageCount хранятся сведения о количестве сообщений, отправленных пользователем во время конференции. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: f3ec657147967a783cbe27a7a78acd6dd0fbfbb9b260d3673bcda0bdf353e5fc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54322971"
---
# <a name="conferencemessagecount-view"></a>Представление ConferenceMessageCount
 
В представлении ConferenceMessageCount хранятся сведения о количестве сообщений, отправленных пользователем во время конференции. Это представление было представлено в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление ConferenceMessageCount содержит все столбцы в представлении [ConferenceSessionDetails,](conferencesessiondetails.md) а также столбцы, перечисленные ниже.
  
|**Column**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar (450)  <br/> |URI пользователя, отправившего сообщение.  <br/> |
|**UserUriType** <br/> |nvarchar (256)  <br/> |Тип URI пользователя, отправившего сообщения. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Клиент пользователя, отправившего сообщения. Дополнительные сведения см. в таблице [Tenants.](tenants.md) <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Количество сообщений, отправленных пользователем во время сеанса конференц-связи.  <br/> |
   

