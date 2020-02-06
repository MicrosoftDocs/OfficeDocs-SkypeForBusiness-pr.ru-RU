---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: Тблпреференце включает клиентские настройки пользователей. Обычно используется клиентами, предшествующими Lync 2013.
ms.openlocfilehash: 426a9f6aebe6cc6e510e2a75093b9210d3a0ba46
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814557"
---
# <a name="tblpreference"></a>tblPreference

Тблпреференце включает клиентские настройки пользователей. Обычно используется клиентами, предшествующими Lync 2013.

**Столбцов**


| **Столбец**            | **Тип**                        | **Описание**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| префлабел  <br/>      | nvarchar (255), NOT NULL  <br/> | Метка с таким же форматом, \<как URL-адрес пользователя SIP\>                   |
| префсекид  <br/>      | int, NOT NULL  <br/>            | Последовательный номер (на метку) для целей управления версиями.  <br/> |
| префконтент  <br/>    | nvarchar (max)  <br/>           | Закодированное содержимое.  <br/>                                         |
| ластмодифиедби  <br/> | int, NOT NULL  <br/>            | Идентификатор участника, который обновил предпочтение.  <br/>         |

**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Префлабел, Префсекид\>  <br/> |Первичный ключ.  <br/> |


