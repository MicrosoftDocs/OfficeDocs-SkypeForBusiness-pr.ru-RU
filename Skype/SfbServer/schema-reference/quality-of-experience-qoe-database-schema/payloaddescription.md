---
title: Таблица PayloadDescription
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
ms.assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
description: Таблица PayloadDescription является вспомогательной. Каждая запись представляет один кодек, используемый в аудио- или видеосеансе.
ms.openlocfilehash: c9476aea28993a053096a095469d2d4e13251581
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806299"
---
# <a name="payloaddescription-table"></a>Таблица PayloadDescription
 
Таблица PayloadDescription является вспомогательной. Каждая запись представляет один кодек, используемый в аудио- или видеосеансе.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**PayloadDescriptionKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, обозначающий кодек.  <br/> |
|**PayloadDescription** <br/> |nvarchar(256)  <br/> |Уникальные  <br/> |Имя кодека.  <br/> |
   

