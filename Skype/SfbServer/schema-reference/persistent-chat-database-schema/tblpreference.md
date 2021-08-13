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
description: tblPreference содержит клиентские предпочтения пользователей. Это обычно используется клиентами до Lync 2013.
ms.openlocfilehash: 698976f3f98b939578787a0f8a2c0aeb8167888ad09ea20a09d0d7e4d83e900c
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54315435"
---
# <a name="tblpreference"></a>tblPreference

tblPreference содержит клиентские предпочтения пользователей. Это обычно используется клиентами до Lync 2013.

**Columns**


| **Столбец**            | **Тип**                        | **Описание**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), не равно null  <br/> | Метка с таким форматом, как: \<user sip uri\>                   |
| prefSeqID  <br/>      | int, не равно null  <br/>            | Порядковый номер (каждой отдельной метки) для управления версиями.  <br/> |
| prefContent  <br/>    | nvarchar (max)  <br/>           | Зашифрованное содержимое.  <br/>                                         |
| lastModifiedBy  <br/> | int, не равно null  <br/>            | Идентификатор субъекта, обновившего параметр.  <br/>         |

**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |Первичный ключ.  <br/> |


