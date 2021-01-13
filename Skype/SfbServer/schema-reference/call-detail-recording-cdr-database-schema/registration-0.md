---
title: Представление регистрации
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
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: В представлении Registration хранится информация о регистрации пользователей. Это представление впервые было введено в Lync Server 2013.
ms.openlocfilehash: 12508e7efcd96bdb9e3956b4e62c1065235a3f60
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823129"
---
# <a name="registration-view"></a>Представление регистрации
 
В представлении Registration хранится информация о регистрации пользователей. Это представление впервые было введено в Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Details**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Время запроса сеанса. Используется вместе с параметром SessionIdSeq для уникального определения сеанса. Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md) <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Идентификационный номер для идентификации сеанса. Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса. Дополнительные сведения см. в таблице [Dialogs в Skype для бизнеса Server 2015.](dialogs.md) <br/> |
|**RegisterTime** <br/> |datetime  <br/> |Время регистрации.  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> |URI зарегистрировавшегося пользователя.  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |Тип URI зарегистрировавшегося пользователя. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
|**UserTenant** <br/> |nvarchar(256)  <br/> |Клиент зарегистрировавшегося пользователя. Дополнительные [сведения см. в](tenants.md) таблице Tenants. <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |Уникальный идентификатор конечной точки зарегистрировавшегося пользователя.  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |Уникальный идентификатор для различия регистраций с одним пользователем и одной конечной точкой.  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |Время отмены регистрации.  <br/> |
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> |Причина отмены регистрации.  <br/> |
|**ClientVersion** <br/> |nvarchar(256)  <br/> |Версия клиента зарегистрировавшегося пользователя.  <br/> |
|**ClientType** <br/> |int  <br/> |Версия клиента зарегистрировавшегося пользователя. Дополнительные сведения см. в таблице [UserAgentDef.](useragentdef.md) <br/> |
|**ClientCategory** <br/> |nvarchar(64)  <br/> |Категория клиента зарегистрировавшегося пользователя.  <br/> |
|**IpAddress** <br/> |nvarchar(256)  <br/> |IP-адрес зарегистрировавшегося пользователя. Это может быть IPv4- или IPv6-адрес.  <br/> |
|**DialogId** <br/> |varstring(775)  <br/> |Код диалога SIP. Формат:  <br/> dialog;from-tag;to-tag  <br/> |
|**ResponseCode** <br/> |int  <br/> |Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |Код диагностики из заголовков SIP.  <br/> |
|**Registrar** <br/> |nvarchar(256)  <br/> |Полное доменное имя регистратора.  <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |Полное доменное имя пула, который получил данные этого сеанса.  <br/> |
|**EdgeServer** <br/> |nvarchar(256)  <br/> |Полное доменное имя пограничного сервера зарегистрировавшегося пользователя.  <br/> |
|**IsInternal** <br/> |bit  <br/> |Показывает, зашел ли пользователь в систему из внутренней сети.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Указывает, была ли служба UserService доступна во время регистрации.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Указывает, осуществлялась регистрация в основном регистраторе.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |MAC-адрес зарегистрировавшегося устройства.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar(256)  <br/> |Производитель зарегистрировавшегося устройства. Дополнительные сведения см. в таблице [Manufacturers в Skype для бизнеса Server 2015.](manufacturers.md) <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar(256)  <br/> |Версия оборудования зарегистрировавшегося устройства. Дополнительные сведения см. в таблице [HardwareVersions в Skype для бизнеса Server 2015.](hardwareversions.md) <br/> |
   

