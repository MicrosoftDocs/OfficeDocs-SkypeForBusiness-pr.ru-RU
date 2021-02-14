---
title: Перенос нескольких сайтов и пулов
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype для бизнеса Server 2019 поддерживает развертывание с несколькими сайтами и несколькими пулами. Процесс переноса нескольких пулов в Skype для бизнеса Server 2019 требует следующих факторов:'
ms.openlocfilehash: 4906b05138d546e685a06acecc4f7adc4e88516e
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752661"
---
# <a name="migrating-multiple-sites-and-pools"></a>Перенос нескольких сайтов и пулов

Skype для бизнеса Server 2019 поддерживает развертывание с несколькими сайтами и несколькими пулами. Процесс переноса нескольких пулов в Skype для бизнеса Server 2019 требует следующих факторов: 
  
1. After deploying a Skype for Business Server 2019 pilot pool, you need to define a subset of pilot users that will be moved to the Skype for Business Server 2019 pool, and a methodology for validating the functionality of the users. Например, после перемещения пользователя в пилотный пул убедитесь, что политика конференций пользователя перемещена в Skype для бизнеса Server 2019. 
    
2. After deploying an Edge Server in the pilot pool, you need to validate that external users can communicate with the Skype for Business Server 2019 pool.

3. Функции сохраняемого чата, зеркального SQL и XMPP не являются устаревшими в Skype для бизнеса Server 2019 и больше не доступны в качестве функций Skype для бизнеса Server 2019, но их можно продолжить в среде сосуществования, если они ранее были развернуты в устаревшей среде. Если вы хотите продолжать использовать эти функции, следует запланировать продолжение работы в среде сосуществования, в которой некоторые пользователи останутся в устаревших пулах.
    
4. After transitioning the federated routes' Edge Servers to the pilot Skype for Business Server 2019 Edge Server, you need to validate that federated users can communicate with the Skype for Business Server 2019 pool.
    
5. После перемещения всех пользователей и контактных объектов, не относящихся к пользователям, необходимо проверить, пуст ли устаревший пул.
    
6. После проверки того, что устаревший пул пуст, его можно отключить. 
    
    Сведения о деактивации устаревших пулов и серверов см. в этапе 8. Списание [устаревших пулов.](phase-8-decommission-legacy-pools.md)
    

