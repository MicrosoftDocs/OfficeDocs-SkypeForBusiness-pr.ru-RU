---
title: Таблица VoipDetails
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Каждая запись представляет двусторонний звонок, по крайней мере один участник которого является пользователем VoIP.
ms.openlocfilehash: ed21e9f66f393d1f5d15314da522a8f7c4bf30d0
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862016"
---
# <a name="voipdetails-table"></a>Таблица VoipDetails
 
Каждая запись представляет двусторонний звонок, по крайней мере один участник которого является пользователем VoIP.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Время запроса сеанса. В сочетании с параметром **SessionIdSeq** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Идентификатор сеанса. В сочетании с параметром **SessionIdTime** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**FromNumberId** <br/> |int  <br/> |Foreign  <br/> |Идентификатор **PhoneId** звонящего. Дополнительные [сведения см. в](phones.md) таблице Телефоны. Если значение этого параметра, а также параметра **FromGatewayId** отлично от NULL, звонящий являлся пользователем ТСОП. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Foreign  <br/> |Идентификатор **PhoneId** получателя звонка. Дополнительные [сведения см. в](phones.md) таблице Телефоны. Если значение этого параметра, а также параметра **ToGatewayId** отлично от NULL, получатель являлся пользователем ТСОП. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Foreign  <br/> |Сервер-посредник, с которого поступил звонок. Дополнительные сведения см. в таблице [MediationServers.](mediationservers.md) <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Foreign  <br/> |Сервер-посредник, на который направляется звонок. Дополнительные сведения см. в таблице [MediationServers.](mediationservers.md) <br/> |
|**FromGatewayId** <br/> |int  <br/> |Foreign  <br/> |Шлюз, из которого поступил звонок. Дополнительные сведения см. в [таблице Шлюзы Skype для бизнеса Server 2015](gateways.md) г. <br/> |
|**ToGatewayId** <br/> |int  <br/> |Foreign  <br/> |Шлюз, на который направляется звонок. Дополнительные сведения см. в [таблице Шлюзы Skype для бизнеса Server 2015](gateways.md) г. <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Foreign  <br/> |Универсальный код ресурса (URI) пользователя, прервавшего звонок (если имеется). Дополнительные [сведения см.](users.md) в таблице Пользователи. <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Foreign  <br/> |ИД телефона, с которого был прерван звонок. Дополнительные [сведения см. в](phones.md) таблице Телефоны. <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Для внутреннего использования службой мониторинга.  <br/> Это поле было введено Skype для бизнеса Server 2015 г.  <br/> |
   

