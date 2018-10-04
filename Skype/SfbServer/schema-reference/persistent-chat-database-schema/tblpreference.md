---
title: tblPreference
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
ms.openlocfilehash: c76c62ec453ab1a152738cb16d76e5c5394a2a98
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375945"
---
# <a name="tblpreference"></a>tblPreference

tblPreference содержит параметры клиента пользователей. Обычно используется клиентами предшествующих Lync 2013.

**Столбцы**


| **Столбец**            | **Тип**                        | **Описание**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| prefLabel  <br/>      | nvarchar (255), отлично от null  <br/> | Метка имеет формат, таких как: \<uri sip пользователя\>                   |
| prefSeqID  <br/>      | int, не null  <br/>            | Порядковый номер (каждой отдельной метки) для управления версиями.  <br/> |
| prefContent  <br/>    | nvarchar (максимум)  <br/>           | Зашифрованное содержимое.  <br/>                                         |
| lastModifiedBy  <br/> | int, не null  <br/>            | Идентификатор субъекта, обновившего.  <br/>         |

**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<prefLabel prefSeqID\>  <br/> |Первичный ключ.  <br/> |


