---
title: Таблица CallType в Скайп для Business Server 2015
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
ms.openlocfilehash: e2353176a69db9eada137525561541d26caa7a8e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Таблица CallType в Скайп для Business Server 2015
 
Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.
  
|**Столбец**|**Тип данных**|**Ключ или индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |целое  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Допускаются следующие значения: <br/>  0 — Неизвестный <br/>  1 — обмен мгновенными сообщениями <br/>  2 — Общий доступ к приложениям <br/>  3 — аудио <br/>  4 — аудио и видео <br/>  5 - Передача файла <br/> |
   

