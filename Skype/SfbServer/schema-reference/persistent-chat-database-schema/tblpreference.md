---
title: tblPreference
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference содержит клиентские предпочтения пользователей. Это обычно используется клиентами до Lync 2013.
ms.openlocfilehash: 24de89ff74da66023aeac696c7f3ae91fb9b98b1
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768457"
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


