---
title: Таблица DeviceDriver
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
ms.assetid: ca91a0b4-98c0-49f6-af9d-7d0f8ac75f1a
description: Таблица DeviceDriver является вспомогательной. Каждая запись представляет драйвер, используемый устройством захвата или отображения.
ms.openlocfilehash: 1f83bfd014fa5fb49f4d0f900e01aeecfe2b5f46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823079"
---
# <a name="devicedriver-table"></a>Таблица DeviceDriver
 
Таблица DeviceDriver является вспомогательной. Каждая запись представляет драйвер, используемый устройством захвата или отображения.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeviceDriverKey** <br/> |int  <br/> |Primary  <br/> |Уникальный номер, идентифицирующий эту запись драйвера устройства.  <br/> |
|**DeviceDriver** <br/> |varchar(256)  <br/> |unique  <br/> |Имя драйвера устройства.  <br/> |
   

