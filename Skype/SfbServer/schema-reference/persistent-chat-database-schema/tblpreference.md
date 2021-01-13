---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference содержит настройки клиента пользователей. Обычно это используется клиентами, предшествующими Lync 2013.
ms.openlocfilehash: 96cd017dd67a05f3240269f5bdcbd23f30fffd28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815909"
---
# <a name="tblpreference"></a>tblPreference

tblPreference содержит настройки клиента пользователей. Обычно это используется клиентами, предшествующими Lync 2013.

**Columns**


| **Столбец**            | **Тип**                        | **Описание**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), не равно null  <br/> | Метка в таком формате, как: \<user sip uri\>                   |
| prefSeqID  <br/>      | int, не равно null  <br/>            | Порядковый номер (каждой отдельной метки) для управления версиями.  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | Зашифрованное содержимое.  <br/>                                         |
| lastModifiedBy  <br/> | int, не равно null  <br/>            | Идентификатор субъекта, обновившего параметр.  <br/>         |

**Раздел**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Первичный ключ.  <br/> |


