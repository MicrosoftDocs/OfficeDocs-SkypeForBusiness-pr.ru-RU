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
description: В представлении UserAgent хранятся сведения об агентах пользователей, участвовавших в сеансах, для которых в базе данных есть соответствующие записи. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: d6ed446c429c3e055d3b5387f4675eaed7fb1f9e992d7211346309254549b66d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282991"
---
# <a name="useragent-view"></a>Представление UserAgent
 
В представлении UserAgent хранятся сведения об агентах пользователей, участвовавших в сеансах, для которых в базе данных есть соответствующие записи. Это представление было представлено в Microsoft Lync Server 2013.
  
|**Column**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Уникальное число, идентифицирующее этот агент пользователя.  <br/> |
|UserAgent  <br/> |nvarchar (256)  <br/> |Строка агента пользователя.  <br/> |
|UAType  <br/> |smallint  <br/> |Тип агента пользователя. Дополнительные сведения см. в таблице [UserAgent.](useragent.md) <br/> |
|UACategory  <br/> |nvarchar (64)  <br/> |Категория, к которой принадлежит агент пользователя. Например, агент пользователя Conferencing_Attendant_1.0 принадлежит UACategory CAA.  <br/> |
   

