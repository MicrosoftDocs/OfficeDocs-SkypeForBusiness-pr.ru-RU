---
title: Таблица Кодекдескриптион
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: В таблице Кодекдескриптион уникальные идентификаторы кодека сопоставляются с соответствующими кодеками. Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем для расшифровки этих сигналов для воспроизведения. Эта таблица введена в Microsoft Lync Server 2013
ms.openlocfilehash: 53410b1bdf4875bd66a80c107dc56c5316fc30a3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810367"
---
# <a name="codecdescription-table"></a>Таблица Кодекдескриптион
 
В таблице Кодекдескриптион уникальные идентификаторы кодека сопоставляются с соответствующими кодеками. Кодеки используются для кодирования цифровых сигналов для передачи и трансляции, а затем для расшифровки этих сигналов для воспроизведения. Эта таблица введена в Microsoft Lync Server 2013
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**кодекдескриптионкэй** <br/> |smallint  <br/> |Primary  <br/> |Уникальный идентификатор, присвоенный кодеку.  <br/> |
|**CodecDescription** <br/> |varchar (256)  <br/> |Повторя  <br/> |Уникальное описание кодека, соответствующего Кодекдескриптионкэй.  <br/> |
   

