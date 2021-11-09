---
title: Представление регистрации
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
description: В представлении Registration хранится информация о регистрации пользователей. Это представление было введено в Lync Server 2013.
ms.openlocfilehash: 62cfed96994f11ec7393bacc1e0b77edbe3374e7
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842671"
---
# <a name="registration-view"></a>Представление регистрации
 
В представлении Registration хранится информация о регистрации пользователей. Это представление было введено в Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Время запроса сеанса. Используется вместе с параметром SessionIdSeq для уникального определения сеанса. Дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Идентификационный номер для идентификации сеанса. Используется совместно с параметром SessionIdTime для уникальной идентификации сеанса. Дополнительные сведения см. в таблице [Диалоги Skype для бизнеса Server 2015](dialogs.md) г. <br/> |
|**RegisterTime** <br/> |datetime  <br/> |Время регистрации.  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> |URI зарегистрировавшегося пользователя.  <br/> |
|**UserUriType** <br/> |nvarchar (256)  <br/> |Тип URI зарегистрировавшегося пользователя. Дополнительные сведения см. в таблице [UriTypes.](uritypes.md) <br/> |
|**UserTenant** <br/> |nvarchar (256)  <br/> |Клиент зарегистрировавшегося пользователя. Дополнительные сведения см. в таблице [Tenants.](tenants.md) <br/> |
|**EndpointId** <br/> |uniqueidentifier  <br/> |Уникальный идентификатор конечной точки зарегистрировавшегося пользователя.  <br/> |
|**EndpointEra** <br/> |uniqueidentifier  <br/> |Уникальный идентификатор для различия регистраций с одним пользователем и одной конечной точкой.  <br/> |
|**DeRegisterType** <br/> |datetime  <br/> |Время отмены регистрации.  <br/> |
|**DeRegisterReason** <br/> |nvarchar (256)  <br/> |Причина отмены регистрации.  <br/> |
|**ClientVersion** <br/> |nvarchar (256)  <br/> |Версия клиента зарегистрировавшегося пользователя.  <br/> |
|**ClientType** <br/> |int  <br/> |Версия клиента зарегистрировавшегося пользователя. Дополнительные сведения см. в таблице [UserAgentDef.](useragentdef.md) <br/> |
|**ClientCategory** <br/> |nvarchar (64)  <br/> |Категория клиента зарегистрировавшегося пользователя.  <br/> |
|**IpAddress** <br/> |nvarchar (256)  <br/> |IP-адрес зарегистрировавшегося пользователя. Это может быть IPv4- или IPv6-адрес.  <br/> |
|**Диалоговое окно** <br/> |varstring (775)  <br/> |Код диалога SIP. Формат:  <br/> диалоговое окно; от тега;до тега  <br/> |
|**ResponseCode** <br/> |int  <br/> |Код SIP-ответа на приглашение в сеанс. Это поле обычно заполняется данными, генерируемыми из исходного сообщения INVITE в сеансе. Если сообщения INVITE нет, поле заполняется датой и временем первого релевантного SIP-сообщения (BYE, CANCEL, MESSAGE или INFO).  <br/> |
|**DiagnosticId** <br/> |int  <br/> |Код диагностики из заголовков SIP.  <br/> |
|**Регистратор** <br/> |nvarchar (256)  <br/> |Полное доменное имя регистратора.  <br/> |
|**Pool** <br/> |nvarchar (256)  <br/> |Полное доменное имя пула, который получил данные этого сеанса.  <br/> |
|**EdgeServer** <br/> |nvarchar (256)  <br/> |Полное доменное имя пограничного сервера зарегистрировавшегося пользователя.  <br/> |
|**IsInternal** <br/> |bit  <br/> |Показывает, зашел ли пользователь в систему из внутренней сети.  <br/> |
|**IsUserServiceAvailable** <br/> |bit  <br/> |Указывает, была ли служба UserService доступна во время регистрации.  <br/> |
|**IsPrimaryRegistrar** <br/> |bit  <br/> |Указывает, осуществлялась регистрация в основном регистраторе.  <br/> |
|**DeviceMacAddress** <br/> |bigint  <br/> |MAC-адрес зарегистрировавшегося устройства.  <br/> |
|**DeviceManufacturer** <br/> |nvarchar (256)  <br/> |Производитель зарегистрировавшегося устройства. Дополнительные сведения см. в [таблице Manufacturers Skype для бизнеса Server 2015](manufacturers.md) г. <br/> |
|**DeviceHardwareVersion** <br/> |nvarchar (256)  <br/> |Версия оборудования зарегистрировавшегося устройства. Дополнительные сведения см. в таблице [HardwareVersions Skype для бизнеса Server 2015](hardwareversions.md) г. <br/> |
   

