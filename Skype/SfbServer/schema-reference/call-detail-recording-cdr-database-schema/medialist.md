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
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.
ms.openlocfilehash: 308a9eee57089a02b8e3ff9924e0d9d34162f33e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295987"
---
# <a name="medialist-table"></a>Таблица MediaList
 
Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primary  <br/> |Значения: 1–7  <br/> |
|**Media** <br/> |nvarchar(256)  <br/> || Статическое сопоставление значений MediaID и Media <br/>  1 — мгновенные сообщения <br/>  2 – Передача файлов <br/>  3-Удаленная помощь <br/>  4 – общий доступ к приложениям <br/>  5 — аудио <br/>  6 — видео <br/>  7 — приглашение на приложение <br/> |
   
Если вам нужно определить тип модальности для значений в LcsCDR.SessionDetailsView.MediaTypes, используйте следующий фрагмент кода Join:  
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
