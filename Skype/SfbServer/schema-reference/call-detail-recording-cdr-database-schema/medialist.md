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
ms.openlocfilehash: 9242f20b3c2192fb1f5cd48c84784a3e8d283f6e91587aee408a9286d291add7
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326275"
---
# <a name="medialist-table"></a>Таблица MediaList
 
Таблица MediaList — это статическая таблица, в которой хранится список различных типов мультимедиа.
  
|**Column**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**MediaId** <br/> |tinyint  <br/> |Primary  <br/> |Значения: 1-7  <br/> |
|**Media** <br/> |nvarchar (256)  <br/> || Статическое сопоставление значений MediaID и Media: <br/>  1 — мгновенные сообщения <br/>  2 . Передача файлов <br/>  3 . Удаленная помощь <br/>  4 . Совместное использование приложений <br/>  5 — звук <br/>  6 — видео <br/>  7 . Приглашение приложения <br/> |
   
Если вы пытаетесь определить тип модальности для значений в LcsCDR.SessionDetailsView.MediaTypes, необходимо использовать следующий фрагмент Join: 
  
```SQL
LEFT JOIN on Media.MediaId = MediaList.MediaId
```
