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
description: В представлении ConferenceMessageCount хранятся сведения о количестве сообщений, отправленных пользователем во время конференции. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: 8394ed37d4b85e8ec5fcda4234b4c28f4276fb17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813299"
---
# <a name="conferencemessagecount-view"></a>Представление ConferenceMessageCount
 
В представлении ConferenceMessageCount хранятся сведения о количестве сообщений, отправленных пользователем во время конференции. Это представление впервые было введено в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление ConferenceMessageCount содержит все столбцы в представлении [ConferenceSessionDetails,](conferencesessiondetails.md) а также столбцы, перечисленные ниже.
  
|**Столбец**|**Тип данных**|**Details**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |URI пользователя, отправившего сообщение.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Тип URI пользователя, отправившего сообщения. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |Клиент пользователя, отправившего сообщения. Дополнительные [сведения см.](tenants.md) в таблице Tenants. <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |Количество сообщений, отправленных пользователем во время сеанса конференц-связи.  <br/> |
   

