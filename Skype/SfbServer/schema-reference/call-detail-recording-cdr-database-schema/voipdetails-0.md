---
title: Таблица VoipDetails
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Каждая запись представляет двусторонний звонок, по крайней мере один участник которого является пользователем VoIP.
ms.openlocfilehash: 900598c99965292e7d349520cc2dfa55443bb5a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813099"
---
# <a name="voipdetails-table"></a>Таблица VoipDetails
 
Каждая запись представляет двусторонний звонок, по крайней мере один участник которого является пользователем VoIP.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Время запроса сеанса. В сочетании с параметром **SessionIdSeq** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |Идентификатор сеанса. В сочетании с параметром **SessionIdTime** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md) <br/> |
|**FromNumberId** <br/> |int  <br/> |Внешняя  <br/> |Идентификатор **PhoneId** звонящего. Дополнительные [сведения см. в](phones.md) таблице "Телефоны". Если значение этого параметра, а также параметра **FromGatewayId** отлично от NULL, звонящий являлся пользователем ТСОП. <br/> |
|**ConnectedNumberId** <br/> |int  <br/> |Внешняя  <br/> |Идентификатор **PhoneId** получателя звонка. Дополнительные [сведения см. в](phones.md) таблице "Телефоны". Если значение этого параметра, а также параметра **ToGatewayId** отлично от NULL, получатель являлся пользователем ТСОП. <br/> |
|**FromMediationServerId** <br/> |int  <br/> |Внешняя  <br/> |Сервер-посредник, с которого поступил звонок. Дополнительные сведения см. в таблице [MediationServers.](mediationservers.md) <br/> |
|**ToMediationServerId** <br/> |int  <br/> |Внешняя  <br/> |Сервер-посредник, на который направляется звонок. Дополнительные сведения см. в таблице [MediationServers.](mediationservers.md) <br/> |
|**FromGatewayId** <br/> |int  <br/> |Внешняя  <br/> |Шлюз, из которого поступил звонок. Дополнительные сведения см. в таблице [Gateways в Skype для бизнеса Server 2015.](gateways.md) <br/> |
|**ToGatewayId** <br/> |int  <br/> |Внешняя  <br/> |Шлюз, на который направляется звонок. Дополнительные сведения см. в таблице [Gateways в Skype для бизнеса Server 2015.](gateways.md) <br/> |
|**DisconnectedbyURIId** <br/> |int  <br/> |Внешняя  <br/> |Универсальный код ресурса (URI) пользователя, прервавшего звонок (если имеется). Дополнительные [сведения см.](users.md) в таблице "Пользователи". <br/> |
|**DisconnectedbyPhoneId** <br/> |int  <br/> |Внешняя  <br/> |ИД телефона, с которого был прерван звонок. Дополнительные [сведения см. в](phones.md) таблице "Телефоны". <br/> |
|**LastModifiedTime** <br/> |Дата и время  <br/> ||Для внутреннего использования службой мониторинга.  <br/> Это поле было впервые введено в Skype для бизнеса Server 2015.  <br/> |
   

