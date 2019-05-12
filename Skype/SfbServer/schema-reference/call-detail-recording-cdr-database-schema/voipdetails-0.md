---
title: Таблица VoipDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 74ffbb71-569b-4018-be1f-4db2bbafcf36
description: Каждая запись представляет один двусторонний звонок по крайней мере один пользователь является пользователем VoIP.
ms.openlocfilehash: e29cfe19ec8c478215c8dd011a8479de5e18c18c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929961"
---
# <a name="voipdetails-table"></a>Таблица VoipDetails
 
Каждая запись представляет один двусторонний звонок по крайней мере один пользователь является пользователем VoIP.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |Время запроса сеанса. Используется совместно с **SessionIdSeq** для уникальной идентификации сеанса. В разделе [диалоговых окон в таблице в Скайп для Business Server 2015](dialogs.md) для получения дополнительных сведений. <br/> |
|**SessionIdSeq** <br/> |целое  <br/> |Primary  <br/> |Номер идентификатора для идентификации сеанса. Используется в сочетании с **SessionIdTime** для уникальной идентификации сеанса. В разделе [диалоговых окон в таблице в Скайп для Business Server 2015](dialogs.md) для получения дополнительных сведений. <br/> |
|**FromNumberId** <br/> |целое  <br/> |Внешний  <br/> |**PhoneId** вызывающего абонента. В разделе [Таблица Phones](phones.md) для получения дополнительных сведений. Если не NULL и **FromGatewayId** не равно NULL, вызывающего была Пользователь ТСОП. <br/> |
|**ConnectedNumberId** <br/> |целое  <br/> |Внешний  <br/> |**PhoneId** получателя вызова. В разделе [Таблица Phones](phones.md) для получения дополнительных сведений. Если не NULL и **ToGatewayId** не равно NULL, получателя вызова была Пользователь ТСОП. <br/> |
|**FromMediationServerId** <br/> |целое  <br/> |Внешний  <br/> |Сервер-посредник звонок поступает из. [Таблица mediationservers](mediationservers.md) для получения дополнительных сведений см. <br/> |
|**ToMediationServerId** <br/> |целое  <br/> |Внешний  <br/> |Будет вызван сервера-посредника. [Таблица mediationservers](mediationservers.md) для получения дополнительных сведений см. <br/> |
|**FromGatewayId** <br/> |целое  <br/> |Внешний  <br/> |Шлюз звонок поступает из. В разделе [Таблица шлюзы в Скайп для Business Server 2015](gateways.md) для получения дополнительных сведений. <br/> |
|**ToGatewayId** <br/> |целое  <br/> |Внешний  <br/> |Шлюз звонок будет. В разделе [Таблица шлюзы в Скайп для Business Server 2015](gateways.md) для получения дополнительных сведений. <br/> |
|**DisconnectedbyURIId** <br/> |целое  <br/> |Внешний  <br/> |URI пользователя, отключившегося от вызова, если у пользователя есть URI. В [таблице пользователей](users.md) для получения дополнительных сведений см. <br/> |
|**DisconnectedbyPhoneId** <br/> |целое  <br/> |Внешний  <br/> |Идентификатор телефона, который отключен звонок был отключен с телефона. В разделе [Таблица Phones](phones.md) для получения дополнительных сведений. <br/> |
|**LastModifiedTime** <br/> |Даты и времени  <br/> ||Для внутреннего использования службой мониторинга.  <br/> В этом поле было представлено в Скайп для Business Server 2015.  <br/> |
   

