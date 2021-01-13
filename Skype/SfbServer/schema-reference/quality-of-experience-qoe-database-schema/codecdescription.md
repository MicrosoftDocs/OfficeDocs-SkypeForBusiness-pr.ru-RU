---
title: Таблица CodecDescription
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: В таблице CodecDescription сопоставляются уникальные идентификаторы кодеков с соответствующими кодеками. Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем расшифровки этих сигналов для воспроизведения. Эта таблица была представлена в Microsoft Lync Server 2013
ms.openlocfilehash: 95ba2218ff20aa6c67de6f60d6966916b6648a58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831349"
---
# <a name="codecdescription-table"></a>Таблица CodecDescription
 
В таблице CodecDescription сопоставляются уникальные идентификаторы кодеков с соответствующими кодеками. Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем расшифровки этих сигналов для воспроизведения. Эта таблица была представлена в Microsoft Lync Server 2013
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**CodecDescriptionKey** <br/> |smallint  <br/> |Primary  <br/> |Уникальный идентификатор, назначенный кодеку.  <br/> |
|**CodecDescription** <br/> |varchar(256)  <br/> |Уникальные  <br/> |Уникальное описание кодека, соответствующего CodecDescriptionKey.  <br/> |
   

