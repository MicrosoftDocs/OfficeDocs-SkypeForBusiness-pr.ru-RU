---
title: Таблица MediaList
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.
ms.openlocfilehash: 6f593876a1b42163b6f2e75dbe44c1eb26b2ff16
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813139"
---
# <a name="medialist-table"></a>Таблица MediaList
 
Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primary  <br/> |Значения: 1–7  <br/> |
|**Media** <br/> |nvarchar(256)  <br/> || Статическое сопоставление значений MediaID и Media: <br/>  1 — мгновенные сообщения <br/>  2 — передача файлов <br/>  3 — удаленная помощь <br/>  4 — общий доступ к приложениям <br/>  5 — звук <br/>  6 — видео <br/>  7 — приглашение приложения <br/> |
   
Если вы пытаетесь определить тип модальности для значений в LcsCDR.SessionDetailsView.MediaTypes, необходимо использовать следующий фрагмент кода join: 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
