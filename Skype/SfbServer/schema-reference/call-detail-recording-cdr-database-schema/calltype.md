---
title: Таблица CallType в Skype для бизнеса Server 2015 г.
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.
ms.openlocfilehash: d5dce646dfff73d9935aba568827e21671daf4073721f8b892f369d62348e945
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296968"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Таблица CallType в Skype для бизнеса Server 2015 г.
 
Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Допустимые значения: <br/>  0 — неизвестный <br/>  1 . Обмен мгновенными сообщениями <br/>  2. Совместное использование приложений <br/>  3 — аудио <br/>  4 . Аудио и видео <br/>  5 . Передача файлов <br/> |
   

