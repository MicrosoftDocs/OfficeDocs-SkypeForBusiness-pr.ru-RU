---
title: tblPreference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference содержит параметры клиента пользователей. Обычно используется клиентами предшествующих Lync 2013.
ms.openlocfilehash: b5036d9c71feaea6406ecdcaa6f15b61f64d5ad3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879793"
---
# <a name="tblpreference"></a>tblPreference

tblPreference содержит параметры клиента пользователей. Обычно используется клиентами предшествующих Lync 2013.

**Столбцы**


| **Столбец**            | **Тип**                        | **Описание**.                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), отлично от null  <br/> | Метка имеет формат, таких как: \<uri sip пользователя\>                   |
| prefSeqID  <br/>      | int, не null  <br/>            | Порядковый номер (каждой отдельной метки) для управления версиями.  <br/> |
| prefContent  <br/>    | nvarchar (максимум)  <br/>           | Зашифрованное содержимое.  <br/>                                         |
| lastModifiedBy  <br/> | int, не null  <br/>            | Идентификатор субъекта, обновившего.  <br/>         |

**Ключ**

|**Столбец**|**Описание**.|
|:-----|:-----|
|\<prefLabel prefSeqID\>  <br/> |Первичный ключ.  <br/> |


