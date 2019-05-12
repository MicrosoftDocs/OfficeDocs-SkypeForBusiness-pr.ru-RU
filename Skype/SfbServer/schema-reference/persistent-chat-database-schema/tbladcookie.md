---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie содержит текущий файлы cookie синхронизации Lightweight Directory Access Protocol (LDAP).
ms.openlocfilehash: d990d02e73be9a4d6178037a314e36add448ad40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929947"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie содержит текущий файлы cookie синхронизации Lightweight Directory Access Protocol (LDAP).
  
**Столбцы**

|**Столбец**|**Тип**|**Описание**|
|:-----|:-----|:-----|
|prinGuid  <br/> |Идентификатор GUID, не может быть null  <br/> |GUID субъекта домена, за которым ведется наблюдение.  <br/> |
|prinDCHost  <br/> |nvarchar (255)  <br/> |Полное доменное имя (FQDN) текущего контроллера домена, используемого для синхронизации службы домена Active Directory. Информационные значение равно.  <br/> |
|adcContent  <br/> |изображение (двоичный)  <br/> |Файл cookie Active Directory синхронизации.  <br/> |
|lastUpdated  <br/> |datetime  <br/> |Метка времени со временем обновления строки.  <br/> |
|lockedUntil  <br/> |datetime  <br/> |Время, пока не заблокирован строку для изменения. Это часть механизм блокировка программного обеспечения, чтобы гарантировать, что только один из службы чата не синхронизации Active Directory за раз.  <br/> |
   
**Ключи**

|**Столбцы**|**Описание**|
|:-----|:-----|
|prinGuid  <br/> |Первичный ключ.  <br/> |
|prinGuid  <br/> |Внешний ключ с поиском в таблице Principal.prinGuid.  <br/> |
   

