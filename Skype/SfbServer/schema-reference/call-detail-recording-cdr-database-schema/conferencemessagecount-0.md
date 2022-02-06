---
title: Представление ConferenceMessageCount
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: 'В представлении ConferenceMessageCount хранятся сведения о количестве сообщений, отправленных пользователем во время конференции. Это представление было представлено в Microsoft Lync Server 2013.'
---

# <a name="conferencemessagecount-view"></a>Представление ConferenceMessageCount
 
В представлении ConferenceMessageCount хранятся сведения о количестве сообщений, отправленных пользователем во время конференции. Это представление было представлено в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление ConferenceMessageCount содержит все столбцы в представлении [ConferenceSessionDetails](conferencesessiondetails.md) , а также столбцы, перечисленные ниже.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar (450)  <br/> |URI пользователя, отправившего сообщение.  <br/> |
|**UserUriType** <br/> |nvarchar (256)  <br/> |Тип URI пользователя, отправившего сообщения. Дополнительные сведения [см. в таблице UriTypes](uritypes.md) . <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Клиент пользователя, отправившего сообщения. Дополнительные [сведения см. в таблице Tenants](tenants.md) . <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Количество сообщений, отправленных пользователем во время сеанса конференц-связи.  <br/> |
   

