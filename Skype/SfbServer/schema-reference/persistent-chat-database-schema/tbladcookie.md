---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie содержит текущие файлы cookie синхронизации для протокола LDAP.
ms.openlocfilehash: 4d8604699eac26ce599a081069c85c57095f4fda
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852853"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie содержит текущие файлы cookie синхронизации для протокола LDAP.
  
**Columns**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, не NULL  <br/> |GUID субъекта для домена, за которым осуществляется мониторинг.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Полное доменное имя (FQDN) текущего контроллера домена, используемого для синхронизации служб домена Active Directory. Имеет информационное значение.  <br/> |
|adcContent  <br/> |image (binary)  <br/> |Файл cookie синхронизации Active Directory.  <br/> |
|lastUpdated  <br/> |datetime  <br/> |Метка времени со временем обновления строки.  <br/> |
|lockedUntil  <br/> |datetime  <br/> |время, до которого строка заблокирована для внесения изменений. Это часть механизма программной блокировки, которая обеспечивает одновременное выполнение синхронизации Active Directory только одной службой чата.  <br/> |
   
**Keys**

|**Column(s)**|**Описание**|
|:-----|:-----|
|prinGuid  <br/> |Первичный ключ.  <br/> |
|prinGuid  <br/> |Внешний ключ с поиском в таблице Principal.prinGuid.  <br/> |
   

