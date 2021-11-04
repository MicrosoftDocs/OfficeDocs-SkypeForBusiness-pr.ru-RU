---
title: Представление VoIPDetails
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Представление VoIPDetails сохраняет сведения о одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 8e647f79953efc507e63aa4f19e6f1deba53d7a1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765087"
---
# <a name="voipdetails-view"></a>Представление VoIPDetails
 
Представление VoIPDetails сохраняет сведения о одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP. Это представление было представлено в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление VoIPDetails содержит все столбцы в представлении [SessionDetails,](sessiondetails-0.md) а также столбцы, перечисленные ниже.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar (450)  <br/> |Телефон URI пользователя, который начал сеанс.  <br/> |
|**ToPhone** <br/> |nvarchar (450)  <br/> |Телефон URI пользователя, присоединившегося к сеансу.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar (450)  <br/> |URI пользователя, отключившего сеанс.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar (256)  <br/> |Тип URI пользователя, отключившего сеанс. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
|**DisconnectedByTenant** <br/> |nvarchar (256)  <br/> |Клиент пользователя, отключившего сеанс.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar (450)  <br/> |Телефон URI пользователя, отключившего сеанс.  <br/> |
|**FromMediationServer** <br/> |nvarchar (256)  <br/> |Сервер-посредник, используемый пользователем, который начал сеанс.  <br/> |
|**ToMediationServer** <br/> |nvarchar (256)  <br/> |Сервер-посредник, используемый пользователем, присоединившегося к сеансу.  <br/> |
|**FromGateway** <br/> |nvarchar (256)  <br/> |Шлюз, используемый пользователем, который начал сеанс.  <br/> |
|**ToGateway** <br/> |nvarchar (256)  <br/> |Шлюз, используемый пользователем, присоединившегося к сеансу.  <br/> |
   

