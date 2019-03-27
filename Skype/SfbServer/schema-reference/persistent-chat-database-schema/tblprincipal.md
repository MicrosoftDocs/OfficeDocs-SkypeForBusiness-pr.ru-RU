---
title: tblPrincipal
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: Таблица tblPrincipal содержит все субъекты, включая пользователей, папки и группы.
ms.openlocfilehash: adeb4e52ea9bd276de09d90945443431fb3be94f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880975"
---
# <a name="tblprincipal"></a>tblPrincipal
 
Таблица tblPrincipal содержит все субъекты, включая пользователей, папки и группы.
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**.|
|:-----|:-----|:-----|
|prinID  <br/> |int, не null  <br/> |Идентификатор субъекта.  <br/> |
|prinGuid  <br/> |Идентификатор GUID, не может быть null  <br/> |GUID субъекта. Широко используется в качестве альтернативного первичный ключ, так как его значение переходит в пространство доменных служб Active Directory. (Идентификатор GUID для кэширования участника равен соответствующего объекта Active Directory GUID).  <br/> |
|prinUri  <br/> |nvarchar (256), отлично от null  <br/> |URI-идентификатор субъекта. Схема SIP используется для пользователей и группу агент управления используется для практически все остальное.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |Общее имя. Используется только введенных пользователем.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Отображаемое имя. Используется только введенных пользователем.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Название компании. Используется только введенных пользователем.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Отправить по электронной почте. Используется только введенных пользователем.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Доменное имя объекта Active Directory, кэшированной версии субъекта. Может быть Null для типов, которые не являются объектами Active Directory (например, пользователи системы).  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Пользователя имя участника-пользователя (UPN). Использовать только с типами обычный пользователь.  <br/> |
|prinDisabled  <br/> |smallint, не может быть null  <br/> | 0: субъект активен. <br/>  1: субъект отключен, поскольку отключены возможности SIP пользователя. <br/>  2: субъект удален, поскольку удален связанный объект AD. <br/> |
|prinTypeID  <br/> |smallint, не может быть null  <br/> |Тип субъекта (из таблицы tblPrincipalType).  <br/> |
|prinPoolID  <br/> |Int  <br/> |Скайп для бизнеса клиента пула, назначенный субъекту.  <br/> |
|prinPolicyID  <br/> |Int  <br/> |Значение политики persistent Chat Server для пользователя, если определена политика типов тегов.  <br/> |
|prinAddedBy  <br/> |целое  <br/> |Идентификатор субъекта создателя.  <br/> |
|prinAddedOn  <br/> |bigint, не может быть null  <br/> |Метка времени создания.  <br/> |
|prinUpdatedBy  <br/> |целое  <br/> |Идентификатор субъекта, выполнившего последнее обновление.  <br/> |
|prinUpdatedOn  <br/> |bigint, не может быть null  <br/> |Метка времени последнего обновления.  <br/> |
|prinVerifiedOn  <br/> |DateTime, не может быть null  <br/> |Дата и время последней синхронизации Active Directory обновления субъекта в результате.  <br/> |
   
**Ключи**

|**Столбец**|**Описание**.|
|:-----|:-----|
|prinID  <br/> |Первичный ключ.  <br/> |
|prinTypeID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipalType.ptypeID.  <br/> |
   

