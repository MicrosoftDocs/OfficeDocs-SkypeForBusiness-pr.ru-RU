---
title: Таблица CallType в Skype для бизнеса Server 2015 г.
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
ms.assetid: a1d7187c-f851-4967-88ea-73922911ee7a
description: Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.
ms.openlocfilehash: 05bfcf5b13735a460f8122fc6b1ce5eeddf94b97
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743195"
---
# <a name="calltype-table-in-skype-for-business-server-2015"></a>Таблица CallType в Skype для бизнеса Server 2015 г.
 
Таблица CallType — это статическая таблица, в которой хранится список допустимых типов звонков.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**CallTypeId** <br/> |int  <br/> |Primary  <br/> ||
|**CallType** <br/> |nvarchar  <br/> || Допустимые значения: <br/>  0 — неизвестный <br/>  1 . Обмен мгновенными сообщениями <br/>  2. Совместное использование приложений <br/>  3 — аудио <br/>  4 . Аудио и видео <br/>  5 . Передача файлов <br/> |
   

