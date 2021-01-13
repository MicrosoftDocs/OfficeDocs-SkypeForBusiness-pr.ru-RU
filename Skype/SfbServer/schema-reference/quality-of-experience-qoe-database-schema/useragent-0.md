---
title: Представление UserAgent
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: В представлении UserAgent хранятся сведения об агентах пользователей, участвовавших в сеансах, для которых в базе данных есть соответствующие записи. Это представление впервые было введено в Microsoft Lync Server 2013.
ms.openlocfilehash: 90db61df5bd947b101823172602103e47d4182a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800019"
---
# <a name="useragent-view"></a>Представление UserAgent
 
В представлении UserAgent хранятся сведения об агентах пользователей, участвовавших в сеансах, для которых в базе данных есть соответствующие записи. Это представление впервые было введено в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Details**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Уникальное число, идентифицирующее этот агент пользователя.  <br/> |
|UserAgent  <br/> |nvarchar(256)  <br/> |Строка агента пользователя.  <br/> |
|UAType  <br/> |smallint  <br/> |Тип агента пользователя. Дополнительные сведения см. в таблице [UserAgent.](useragent.md) <br/> |
|UACategory  <br/> |nvarchar(64)  <br/> |Категория, к которой принадлежит агент пользователя. Например, агент пользователя Conferencing_Attendant_1.0 принадлежит UACategory CAA.  <br/> |
   

