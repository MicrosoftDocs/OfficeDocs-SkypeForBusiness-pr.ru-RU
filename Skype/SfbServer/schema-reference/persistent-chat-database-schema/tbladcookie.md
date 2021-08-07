---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie содержит текущие файлы cookie синхронизации для протокола LDAP.
ms.openlocfilehash: 19914e31819ea38df6de39e5b0afebcb6bb59fdb15b8d2fbe7d7d59b30271a38
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276594"
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

|**Column(s)**|**Description**|
|:-----|:-----|
|prinGuid  <br/> |Первичный ключ.  <br/> |
|prinGuid  <br/> |Внешний ключ с поиском в таблице Principal.prinGuid.  <br/> |
   

