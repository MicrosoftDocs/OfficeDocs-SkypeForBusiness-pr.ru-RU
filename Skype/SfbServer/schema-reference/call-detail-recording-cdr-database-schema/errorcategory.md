---
title: Таблица Ерроркатегори в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'В таблице Ерроркатегори содержится понятное имя для каждой классификации диагностики Skype для Business Server 2015. По умолчанию в Skype для бизнеса Server 2015 используются следующие классификации:'
ms.openlocfilehash: bafeb75ee9e6ae0f96b08e26909828f1b36f7e7b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296289"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a>Таблица Ерроркатегори в Skype для бизнеса Server 2015
 
В таблице Ерроркатегори содержится понятное имя для каждой классификации диагностики Skype для Business Server 2015. По умолчанию в Skype для бизнеса Server 2015 используются следующие классификации:
  
- 0 — успех
    
- 1 — ожидаемый сбой
    
- 2 — непредвиденный сбой
    
Эта таблица введена в Microsoft Lync Server 2013.
  
|**Столбец**|**Тип данных**|**Ключ/индекс**|**Сведения**|
|:-----|:-----|:-----|:-----|
|**КодТипа** <br/> |tinyint  <br/> |Primary  <br/> |Уникальный идентификатор для классификации.  <br/> |
|**Имя**. <br/> |nvarchar(256)  <br/> || Значение и понятное имя, присвоенное классификации. Допустимые значения: <br/>  0 — успех <br/>  1 — ожидаемый сбой <br/>  2 — непредвиденный сбой <br/> |
   

