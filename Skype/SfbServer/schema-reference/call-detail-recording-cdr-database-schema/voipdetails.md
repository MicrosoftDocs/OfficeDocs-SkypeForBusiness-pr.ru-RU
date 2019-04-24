---
title: Представление VoIPDetails
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Представление VoIPDetails сохранение информации о сеансах peer-to-peer, где по крайней мере один пользователь является пользователем VoIP. В этом представлении была введена в Microsoft Lync Server 2013.
ms.openlocfilehash: 940c3874d5ce8eb8a4d2261de56b8988b6d3a4c9
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212707"
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
   

