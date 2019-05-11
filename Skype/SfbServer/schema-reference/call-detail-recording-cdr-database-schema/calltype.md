---
title: Таблица CallType в Скайп для Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.
ms.openlocfilehash: a75ae3e22d435241e6bf2eb81b8268a7f1bb5a40
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924796"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Таблица CallType в Скайп для Business Server 2015
 
Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |целое  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Допускаются следующие значения: <br/>  0 — Неизвестный <br/>  1 — обмен мгновенными сообщениями <br/>  2 — Общий доступ к приложениям <br/>  3 — аудио <br/>  4 — аудио и видео <br/>  5 - Передача файла <br/> |
   

