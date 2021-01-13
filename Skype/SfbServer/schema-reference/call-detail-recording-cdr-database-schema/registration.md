---
title: Таблица Registration
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
ms.assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
description: Каждая запись представляет одно событие регистрации пользователя.
ms.openlocfilehash: 1ab9c4b80d7bdbbc379c202978d7639e286128fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823119"
---
# <a name="registration-table"></a>Таблица Registration
 
Каждая запись представляет одно событие регистрации пользователя.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Основной, внешний  <br/> |Время запроса сеанса. В сочетании с параметром **SessionIdSeq** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Основной, внешний  <br/> |Идентификатор для идентификации сеанса. В сочетании с параметром **SessionIdTime** определяет сеанс уникальным образом. Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md) <br/> |
|**UserId** <br/> |int  <br/> |Внешняя  <br/> |Идентификатор пользователя. Дополнительные [сведения см.](users.md) в таблице "Пользователи". <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> ||GUID для идентификации конечной точки регистрации. Обычно события регистрации с одного и того же компьютера и одного и того же пользователя будут иметь одинаковый идентификатор конечной точки. Разные компьютеры имеют разные идентификаторы конечной точки.  <br/> |
|**EndpointEra** <br/> |uniqueIdentifier  <br/> ||Идентификатор, используемый, чтобы отличать друг от друга регистрации, в которых участвует один и тот же пользователь и одна и та же конечная точка.  <br/> Это поле было впервые введено в Microsoft Lync Server 2013.  <br/> |
|**ClientVersionId** <br/> |int  <br/> |Внешняя  <br/> |Версия клиента текущего пользователя. Дополнительные сведения см. в таблице [ClientVersions в Skype для бизнеса Server 2015.](clientversions.md) <br/> |
|**RegistrarId** <br/> |int  <br/> |Внешняя  <br/> |Идентификатор сервера регистратора, использовавшегося для регистрации. Дополнительные [сведения см. в](servers.md) таблице "Серверы". <br/> |
|**PoolId** <br/> |int  <br/> |Внешняя  <br/> |Идентификатор пула, в котором был записан сеанс. Дополнительные [сведения см. в](pools.md) таблице "Пулы". <br/> |
|**EdgeServerId** <br/> |int  <br/> |Внешняя  <br/> |Пограничный сервер, через который проходила регистрация. Дополнительные сведения см. в таблице [EdgeServers в Skype для бизнеса Server 2015.](edgeservers.md) <br/> |
|**IsInternal** <br/> |Bit  <br/> ||Вошел ли пользователь из внутренней сети или нет.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> ||Доступна ли служба UserService.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> ||Является ли регистратор основным.  <br/> |
|**IsPrimaryRegistrarCentral** <br/> |bit  <br/> ||Указывает, регистрировался ли пользователь с помощью устройства для обеспечения связи в филиалах.  <br/> Это поле было впервые введено в Microsoft Lync Server 2013.  <br/> |
|**RegisterTime** <br/> |datetime  <br/> ||Время регистрации.  <br/> |
|**DeRegisterTime** <br/> |datetime  <br/> ||Время отмены регистрации.  <br/> |
|**ResponseCode** <br/> |int  <br/> ||Код ответа запроса регистрации.  <br/> |
|**DiagnosticId** <br/> |int  <br/> ||Диагностический идентификатор запроса регистрации. Указывает тип диагностической информации.  <br/> |
|**DeviceId** <br/> |int  <br/> |Внешняя  <br/> |Устройство, с которого поступил запрос регистрации. Дополнительные сведения см. в таблице ["Устройства" в Skype для бизнеса Server 2015.](devices.md) <br/> |
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Внешняя  <br/> |Причина дерегистрации, например "инициировано пользователем", "срок действия регистрации истек", "сбой клиента" и другие. Дополнительные сведения см. в таблице [DeRegisterType в Skype для бизнеса Server 2015.](deregistertype.md) <br/> |
|**IPAddress** <br/> |nvarchar(256)  <br/> ||IP-адрес конечной точки зарегистрировавшегося пользователя. Это может быть IPv4-адрес или IPv6-адрес.  <br/> Это поле было впервые введено в Microsoft Lync Server 2013.  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||Для внутреннего использования службой мониторинга.  <br/> Это поле было впервые введено в Skype для бизнеса Server 2015.  <br/> |
   

