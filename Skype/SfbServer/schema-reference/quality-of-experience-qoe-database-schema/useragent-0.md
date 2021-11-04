---
title: Представление UserAgent
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: В представлении UserAgent хранятся сведения об агентах пользователей, участвовавших в сеансах, для которых в базе данных есть соответствующие записи. Это представление было представлено в Microsoft Lync Server 2013.
ms.openlocfilehash: a6390689af0da442561ff02fbf54e8843d93fe4f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60768297"
---
# <a name="useragent-view"></a>Представление UserAgent
 
В представлении UserAgent хранятся сведения об агентах пользователей, участвовавших в сеансах, для которых в базе данных есть соответствующие записи. Это представление было представлено в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Сведения**|
|:-----|:-----|:-----|
|UserAgentKey  <br/> |int  <br/> |Уникальное число, идентифицирующее этот агент пользователя.  <br/> |
|UserAgent  <br/> |nvarchar (256)  <br/> |Строка агента пользователя.  <br/> |
|UAType  <br/> |smallint  <br/> |Тип агента пользователя. Дополнительные сведения см. в таблице [UserAgent.](useragent.md) <br/> |
|UACategory  <br/> |nvarchar (64)  <br/> |Категория, к которой принадлежит агент пользователя. Например, агент пользователя Conferencing_Attendant_1.0 принадлежит UACategory CAA.  <br/> |
   

