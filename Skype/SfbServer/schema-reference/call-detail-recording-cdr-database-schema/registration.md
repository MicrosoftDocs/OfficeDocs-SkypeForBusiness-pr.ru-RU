---
title: Таблица регистрации
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
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Каждая запись представляет одно событие регистрации пользователя.
ms.openlocfilehash: 45aa007b242d2a85aa8f19f35571fc367e298433
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60859816"
---
# <a name="registration-table"></a>Таблица регистрации
 
Каждая запись представляет одно событие регистрации пользователя.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Основной, внешний  <br/> |Время запроса сеанса. В сочетании с параметром **SessionIdSeq** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Основной, внешний  <br/> |Идентификатор для идентификации сеанса. В сочетании с параметром **SessionIdTime** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**UserId** <br/> |int  <br/> |Foreign  <br/> |Идентификатор пользователя. Дополнительные [сведения см.](users.md) в таблице Пользователи. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||GUID для идентификации конечной точки регистрации. Обычно события регистрации с одного и того же компьютера и одного и того же пользователя будут иметь одинаковый идентификатор конечной точки. Разные компьютеры имеют разные идентификаторы конечной точки.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||Идентификатор, используемый, чтобы отличать друг от друга регистрации, в которых участвует один и тот же пользователь и одна и та же конечная точка.  <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Foreign  <br/> |Версия клиента текущего пользователя. Дополнительные сведения см. в таблице [ClientVersions Skype для бизнеса Server 2015](clientversions.md) г. <br/> |
|**RegistrarId** <br/> |int  <br/> |Foreign  <br/> |Идентификатор сервера регистратора, использовавшегося для регистрации. Дополнительные сведения см. в таблице [Servers.](servers.md) <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |Идентификатор пула, в котором был записан сеанс. Дополнительные [сведения см. в](pools.md) таблице Пулы. <br/> |
|**EdgeServerId** <br/> |int  <br/> |Foreign  <br/> |Пограничный сервер, через который проходила регистрация. Дополнительные сведения см. в таблице [EdgeServers Skype для бизнеса Server 2015](edgeservers.md) г. <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Вошел ли пользователь из внутренней сети или нет.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Доступна ли служба UserService.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||Является ли регистратор основным.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Указывает, регистрировался ли пользователь с помощью устройства для обеспечения связи в филиалах.  <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||Время регистрации.  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||Время отмены регистрации.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Код ответа запроса регистрации.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||Диагностический идентификатор запроса регистрации. Указывает тип диагностической информации.  <br/> |
|**DeviceId** <br/> |int  <br/> |Foreign  <br/> |Устройство, с которого поступил запрос регистрации. Дополнительные [сведения см. в таблице Devices Skype для бизнеса Server 2015](devices.md) г. <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Foreign  <br/> |Причина дерегистрации, такая как "инициированный пользователем", "регистрация истекла", "сбой клиента" и другие. Дополнительные сведения см. в таблице [DeRegisterType Skype для бизнеса Server 2015](deregistertype.md) г. <br/> |
|**IPAddress** <br/> |nvarchar (256)  <br/> ||IP-адрес конечной точки зарегистрировавшегося пользователя. Это может быть IPv4-адрес или IPv6-адрес.  <br/> Это поле было внедрено в Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Для внутреннего использования службой мониторинга.  <br/> Это поле было введено Skype для бизнеса Server 2015 г.  <br/> |
   

