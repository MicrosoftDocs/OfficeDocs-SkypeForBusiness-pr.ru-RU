---
title: Таблица CodecDescription
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: В таблице CodecDescription сопоставляются уникальные идентификаторы кодеков с соответствующими кодеками. Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем расшифровки этих сигналов для воспроизведения. Эта таблица была представлена в Microsoft Lync Server 2013
ms.openlocfilehash: 3f95de9cf7b6e9aaa778644896bcc458229a23d3
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384177"
---
# <a name="codecdescription-table"></a>Таблица CodecDescription
 
В таблице CodecDescription сопоставляются уникальные идентификаторы кодеков с соответствующими кодеками. Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем расшифровки этих сигналов для воспроизведения. Эта таблица была представлена в Microsoft Lync Server 2013
  
|**Столбец**|**Тип данных**|**Key/Index**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |Уникальный идентификатор, назначенный кодеку.  <br/> |
|**CodecDescription** <br/> |varchar (256)  <br/> |Уникальные  <br/> |Уникальное описание кодека, соответствующего CodecDescriptionKey.  <br/> |
   

