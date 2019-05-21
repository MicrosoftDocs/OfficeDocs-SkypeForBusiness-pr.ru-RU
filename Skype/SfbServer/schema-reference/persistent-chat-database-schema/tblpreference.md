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
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: Тблпреференце включает клиентские настройки пользователей. Обычно используется клиентами, предшествующими Lync 2013.
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295344"
---
# <a name="tblpreference"></a>tblPreference

Тблпреференце включает клиентские настройки пользователей. Обычно используется клиентами, предшествующими Lync 2013.

**Столбцов**


| **Столбец**            | **Тип**                        | **Описание**                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| Префлабел  <br/>      | nvarchar (255), NOT NULL  <br/> | Метка с таким же форматом, \<как URL-адрес пользователя SIP\>                   |
| Префсекид  <br/>      | int, NOT NULL  <br/>            | Последовательный номер (на метку) для целей управления версиями.  <br/> |
| Префконтент  <br/>    | nvarchar (max)  <br/>           | Закодированное содержимое.  <br/>                                         |
| Ластмодифиедби  <br/> | int, NOT NULL  <br/>            | Идентификатор участника, который обновил предпочтение.  <br/>         |

**Ключ**

|**Столбец**|**Описание**|
|:-----|:-----|
|\<Префлабел, Префсекид\>  <br/> |Первичный ключ.  <br/> |


