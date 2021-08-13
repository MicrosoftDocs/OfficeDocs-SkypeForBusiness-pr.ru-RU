---
title: Представление VoIPDetails
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
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Представление VoIPDetails сохраняет сведения о одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 9e8eeaa0e907496d03a4541792f6f100a9191324497ee7603a65ec5a71fba592
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351958"
---
# <a name="voipdetails-view"></a>Представление VoIPDetails
 
Представление VoIPDetails сохраняет сведения о одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP. Это представление было представлено в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление VoIPDetails содержит все столбцы в представлении [SessionDetails,](sessiondetails-0.md) а также столбцы, перечисленные ниже.
  
|**Column**|**Тип данных**|**Сведения**|
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
   

