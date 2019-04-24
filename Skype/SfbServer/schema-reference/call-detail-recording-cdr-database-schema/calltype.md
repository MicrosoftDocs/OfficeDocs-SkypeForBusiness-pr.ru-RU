---
title: Таблица CallType в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.
ms.openlocfilehash: 29e5ed85de5917092ad00cd0e1aa60fec1a31b22
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213363"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Таблица CallType в Скайп для Business Server 2015
 
Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |целое  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Допускаются следующие значения: <br/>  0 — Неизвестный <br/>  1 — обмен мгновенными сообщениями <br/>  2 — Общий доступ к приложениям <br/>  3 — аудио <br/>  4 — аудио и видео <br/>  5 - Передача файла <br/> |
   

