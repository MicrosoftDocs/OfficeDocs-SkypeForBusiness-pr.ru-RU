---
title: tblPrincipal
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 79a24502-b4ce-41f0-8979-8caddf535338
description: Таблица tblPrincipal содержит все субъекты, включая пользователей, папки и группы.
ms.openlocfilehash: 6cd47f3f58d7c68f26b5b8d35eb71db64d4d5131
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60776139"
---
# <a name="tblprincipal"></a>tblPrincipal
 
Таблица tblPrincipal содержит все субъекты, включая пользователей, папки и группы.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinID  <br/> |int, not null  <br/> |Идентификатор субъекта.  <br/> |
|prinGuid  <br/> |GUID, не null  <br/> |Идентификатор GUID субъекта. Это широко используется в качестве альтернативного основного ключа, так как его значение пересекается в пространстве служб домена Active Directory. (GUID кэшированного субъекта аналогичен GUID соответствующего объекта Active Directory.)  <br/> |
|prinUri  <br/> |nvarchar (256), не может быть null  <br/> |Универсальный код ресурса (URI) субъекта. Схема SIP используется для пользователей, а ma-grp — практически для всех остальных субъектов.  <br/> |
|prinName  <br/> |nvarchar (256)  <br/> |Общее имя. Используется только для пользователей.  <br/> |
|prinDisplayName  <br/> |Nvarchar (256)  <br/> |Отображаемое имя. Используется только для пользователей.  <br/> |
|prinCompanyName  <br/> |nvarchar (256)  <br/> |Название компании. Используется только для пользователей.  <br/> |
|prinEmail  <br/> |nvarchar (256)  <br/> |Электронная почта. Используется только для пользователей.  <br/> |
|prinADPath  <br/> |nvarchar (384)  <br/> |Имя домена объекта Active Directory, кэшированной версией которого является субъект. Может иметь значение Null для типов, не являющихся объектами Active Directory (например, системных пользователей).  <br/> |
|prinADUserPrincipalName  <br/> |nvarchar (256)  <br/> |Основное имя пользователя (UPN). Используется только для обычных типов пользователя.  <br/> |
|prinDisabled  <br/> |smallint, не null  <br/> | 0 — субъект активен. <br/>  1. Принцип отключен, так как возможности SIP пользователя отключены. <br/>  2 — субъект удален, поскольку удален связанный объект Active Directory. <br/> |
|prinTypeID  <br/> |smallint, не может быть null  <br/> |Тип субъекта (из таблицы tblPrincipalType).  <br/> |
|prinPoolID  <br/> |Целое  <br/> |Skype для бизнеса клиентского пула для директора.  <br/> |
|prinPolicyID  <br/> |Целое  <br/> |Значение политики сохраняемого сервера чата для пользователя, если политика типа тегов присутствует.  <br/> |
|prinAddedBy  <br/> |int  <br/> |Идентификатор субъекта создателя.  <br/> |
|prinAddedOn  <br/> |bigint, не может быть null  <br/> |Метка времени создания.  <br/> |
|prinUpdatedBy  <br/> |int  <br/> |Идентификатор субъекта, выполнившего последнее обновление.  <br/> |
|prinUpdatedOn  <br/> |bigint, не может быть null  <br/> |Метка времени последнего обновления.  <br/> |
|prinVerifiedOn  <br/> |datetime, не может быть null  <br/> |Дата и время последнего обновления субъекта в результате синхронизации с Active Directory.  <br/> |
   
**Keys**

|**Столбец**|**Описание**|
|:-----|:-----|
|prinID  <br/> |Первичный ключ.  <br/> |
|prinTypeID  <br/> |Внешний ключ с подстановкой в таблице tblPrincipalType.ptypeID.  <br/> |
   

