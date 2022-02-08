---
title: Представление VoIPDetails
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
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Представление VoIPDetails сохраняет сведения о одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 5804f32dfebb2fe8c6844acb0bcd343c5b6ead21
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385407"
---
# <a name="voipdetails-view"></a>Представление VoIPDetails
 
Представление VoIPDetails сохраняет сведения о одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP. Это представление было представлено в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление VoIPDetails содержит все столбцы в представлении [SessionDetails](sessiondetails-0.md) , а также столбцы, перечисленные ниже.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar (450)  <br/> |Телефон URI пользователя, который начал сеанс.  <br/> |
|**ToPhone** <br/> |nvarchar (450)  <br/> |Телефон URI пользователя, присоединившегося к сеансу.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar (450)  <br/> |URI пользователя, отключившего сеанс.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar (256)  <br/> |Тип URI пользователя, отключившего сеанс. Дополнительные сведения [см. в таблице UriTypes](uritypes.md) . <br/> |
|**DisconnectedByTenant** <br/> |nvarchar (256)  <br/> |Клиент пользователя, отключившего сеанс.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar (450)  <br/> |Телефон URI пользователя, отключившего сеанс.  <br/> |
|**FromMediationServer** <br/> |nvarchar (256)  <br/> |Сервер-посредник, используемый пользователем, который начал сеанс.  <br/> |
|**ToMediationServer** <br/> |nvarchar (256)  <br/> |Сервер-посредник, используемый пользователем, присоединившегося к сеансу.  <br/> |
|**FromGateway** <br/> |nvarchar (256)  <br/> |Шлюз, используемый пользователем, который начал сеанс.  <br/> |
|**ToGateway** <br/> |nvarchar (256)  <br/> |Шлюз, используемый пользователем, присоединившегося к сеансу.  <br/> |
   

