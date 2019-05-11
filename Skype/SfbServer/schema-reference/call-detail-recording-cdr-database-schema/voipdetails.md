---
title: Представление VoIPDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Представление VoIPDetails сохранение информации о сеансах peer-to-peer, где по крайней мере один пользователь является пользователем VoIP. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 6fb1dede975e59c0ae56fe9872472310c914f685
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930031"
---
# <a name="voipdetails-view"></a>Представление VoIPDetails
 
Представление VoIPDetails сохранение информации о сеансах peer-to-peer, где по крайней мере один пользователь является пользователем VoIP. В этом представлении была введена в Microsoft Lync Server 2013.
  
> [!NOTE]
> Представление VoIPDetails содержит все столбцы [SessionDetails view](sessiondetails-0.md) в дополнение к этому столбцов, перечисленных ниже.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**FromPhone** <br/> |nvarchar(450)  <br/> |URI-адрес пользователя, запустившего сеанс телефона.  <br/> |
|**ToPhone** <br/> |nvarchar(450)  <br/> |URI-адрес пользователя, который присоединился к сеансу телефона.  <br/> |
|**DisconnectedByUri** <br/> |nvarchar(450)  <br/> |URI пользователя, отключившегося от сеанса.  <br/> |
|**DisconnectedByUriType** <br/> |nvarchar(256)  <br/> |Тип URI пользователя, отключившегося от сеанса. В [таблице UriTypes](uritypes.md) для получения дополнительных сведений см. <br/> |
|**DisconnectedByTenant** <br/> |nvarchar(256)  <br/> |Клиент пользователя, отключившегося от сеанса.  <br/> |
|**DisconnectedByPhone** <br/> |nvarchar(450)  <br/> |URI-адрес пользователя, отключившегося от сеанса телефона.  <br/> |
|**FromMediationServer** <br/> |nvarchar(256)  <br/> |Сервер-посредник пользователя, запустившего сеанс.  <br/> |
|**ToMediationServer** <br/> |nvarchar(256)  <br/> |Сервер-посредник пользователя, который присоединился к сеансу.  <br/> |
|**FromGateway** <br/> |nvarchar(256)  <br/> |Шлюз, используемый пользователем, запустившим сеанс.  <br/> |
|**ToGateway** <br/> |nvarchar(256)  <br/> |Шлюз, используемый пользователем, который присоединился к сеансу.  <br/> |
   

