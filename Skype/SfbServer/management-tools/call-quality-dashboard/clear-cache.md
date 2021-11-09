---
title: Очистка кэша
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: Сводка. Сведения о операции Clear Cache, которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
ms.openlocfilehash: de956a3541416100cf7877b46340f2eccb38b3ea
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843822"
---
# <a name="clear-cache"></a>Очистка кэша
 
**Сводка:** Сведения о операции Clear Cache, которая входит в API данных для панели мониторинга качества вызовов. Панель мониторинга качества вызовов — это средство для Skype для бизнеса Server.
  
Операция Clear Cache является частью API данных для панели мониторинга качества вызовов.
  
## <a name="clear-cache"></a>Очистка кэша

Операция Clear Cache удаляет кэш на сервере для запросов и данных. Это сбросит кэш, после чего мы будем получать свежие данные из QoE Cube для новых запросов.
  

|**Способ**|**Запрос URI**|**ВЕРСИЯ HTTP**|
|:-----|:-----|:-----|
|POST  <br/> |https:// \<portal\> /QoEDataService/ClearCache  <br/> |HTTP/1.1  <br/> |
   
 **Параметры URI** . Нет.
  
 **Заглавные заглавные** запросы — дополнительных загонах не будет.
  
 **Тело запроса** . Нет.
  
 **Ответ.** Ответ включает код состояния HTTP и набор заглавных заглавных ответов.
  
 **Код состояния** — успешная операция возвращает код состояния 200 (OK).
  
 **Заготчики** ответа . Дополнительные заготчики не имеются.
  
 **Тело отклика** . Нет.
  

