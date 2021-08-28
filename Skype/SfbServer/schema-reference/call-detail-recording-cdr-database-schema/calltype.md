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
ms.localizationpriority: medium
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.
ms.openlocfilehash: 7c84e245cac2ceb25a5012f9caf4a2a31d4cb67b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58620915"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Таблица CallType в Skype для бизнеса Server 2015 г.
 
Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Details**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Допустимые значения: <br/>  0 — неизвестный <br/>  1 . Обмен мгновенными сообщениями <br/>  2. Совместное использование приложений <br/>  3 — аудио <br/>  4 . Аудио и видео <br/>  5 . Передача файлов <br/> |
   

