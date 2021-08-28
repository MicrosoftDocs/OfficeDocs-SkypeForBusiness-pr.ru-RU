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
ms.localizationpriority: medium
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Представление VoIPDetails сохраняет сведения о одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: 84f167fc3f4de45142d3bad80acf0fc9803b40db
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593383"
---
# <a name="voipdetails-view"></a>Представление VoIPDetails
 
Представление VoIPDetails сохраняет сведения о одноранговых сеансах, где по крайней мере один пользователь является пользователем VoIP. Это представление было представлено в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление VoIPDetails содержит все столбцы в представлении [SessionDetails,](sessiondetails-0.md) а также столбцы, перечисленные ниже.
  
|**Столбец**|**Тип данных**|**Details**|
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
   

