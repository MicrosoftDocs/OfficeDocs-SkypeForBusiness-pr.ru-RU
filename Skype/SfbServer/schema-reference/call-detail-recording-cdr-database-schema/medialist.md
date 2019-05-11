---
title: Таблица MediaList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/12/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1f440590-c1bc-483e-b7bc-6cc763847768
description: Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.
ms.openlocfilehash: 3eaa40cb5ae03129edaa36effa7b40012fc38429
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930653"
---
# <a name="medialist-table"></a>Таблица MediaList
 
Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primary  <br/> |Значения: 1–7  <br/> |
|**Media** <br/> |nvarchar(256)  <br/> || Статическое сопоставление значений MediaID и Media <br/>  1 — мгновенные сообщения <br/>  2 - передача файлов <br/>  3 — удаленный помощник <br/>  4 - общий доступ к приложениям <br/>  5 — аудио <br/>  6 — видео <br/>  7 - приглашение из приложения <br/> |
   
Если вам нужно определить тип модальности для значений в LcsCDR.SessionDetailsView.MediaTypes, используйте следующий фрагмент кода Join:  
  
```
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
