---
title: Таблица MediaList
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/12/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.
ms.openlocfilehash: 00667806e5099db35cce29b07248569faf09ee24
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767497"
---
# <a name="medialist-table"></a>Таблица MediaList
 
Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primary  <br/> |Значения: 1-7  <br/> |
|**Media** <br/> |nvarchar (256)  <br/> || Статическое сопоставление значений MediaID и Media: <br/>  1 — мгновенные сообщения <br/>  2 . Передача файлов <br/>  3 . Удаленная помощь <br/>  4 . Совместное использование приложений <br/>  5 — звук <br/>  6 — видео <br/>  7 . Приглашение приложения <br/> |
   
Если вы пытаетесь определить тип модальности для значений в LcsCDR.SessionDetailsView.MediaTypes, необходимо использовать следующий фрагмент Join: 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
