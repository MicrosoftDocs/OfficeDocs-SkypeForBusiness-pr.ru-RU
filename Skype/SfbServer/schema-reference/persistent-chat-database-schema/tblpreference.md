---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference содержит клиентские предпочтения пользователей. Это обычно используется клиентами до Lync 2013.
ms.openlocfilehash: 8c719ba33196e32d48f045c07ea89ded317ab5ab
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60846192"
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


