---
title: Таблица MediaList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.
ms.openlocfilehash: e7d739b27bf45b5f5a21183c30bd5b07108b4a9d
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888518"
---
# <a name="medialist-table"></a>Таблица MediaList
 
Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primary  <br/> |Значения: 1–7  <br/> |
|**Media** <br/> |nvarchar(256)  <br/> || Статическое сопоставление значений MediaID и Media <br/>  1 — мгновенные сообщения <br/>  2 – Передача файлов <br/>  3-Удаленная помощь <br/>  4 – общий доступ к приложениям <br/>  5 — аудио <br/>  6 — видео <br/>  7 — приглашение на приложение <br/> |
   
Если вам нужно определить тип модальности для значений в LcsCDR.SessionDetailsView.MediaTypes, используйте следующий фрагмент кода Join:  
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
