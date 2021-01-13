---
title: Очистка кэша
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: Сводка. Сведения об операции очистки кэша, которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
ms.openlocfilehash: c9b966bb1e35a5a6255cd75ea6c685daaf220a09
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806419"
---
# <a name="clear-cache"></a>Очистка кэша
 
**Сводка:** Сведения об операции "Очистить кэш", которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества звонков — это инструмент для Skype для бизнеса Server.
  
Операция "Очистить кэш" является частью API данных для панели мониторинга качества вызовов.
  
## <a name="clear-cache"></a>Очистка кэша

Операция очистки кэша удаляет кэш на сервере для запросов и данных. После этого будет сброшен кэш, и мы будем получать новые данные из куба QoE для новых запросов.
  

|**Способ**|**URI запроса**|**Версия HTTP**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** — нет.
  
 **Request Headers** - No additional headers.
  
 **Тело запроса** — нет.
  
 **Ответ.** Ответ включает код состояния HTTP и набор загодеров отклика.
  
 **Код состояния** — успешная операция возвращает код состояния 200 (OK).
  
 **Response Headers** - No additional headers.
  
 **Тело ответа** — нет.
  

