---
title: Удаление сервера переднего плана из пула
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
description: Сервер переднего сервера не может существовать как автономный компьютер. Его необходимо определить как пул переднего входа, даже если в пуле имеется только один компьютер.
ms.openlocfilehash: 7675ba119fa2937d765d5f4e497fca0a040b3b62
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752321"
---
# <a name="remove-a-front-end-server-from-a-pool"></a>Удаление сервера переднего плана из пула

Сервер переднего сервера не может существовать как автономный компьютер. Его необходимо определить как пул переднего входа, даже если в пуле имеется только один компьютер.
  
В этом разделе вы можете удалить отдельный сервер переднего сервера из существующего пула переднего сервера. Если сервер переднего сервера является последним сервером в пуле или пул полностью удаляется, см. "Удаление пула переднего сервера" или сервера [Standard Edition.](remove-front-end-pool-or-standard-edition-server.md) Нет необходимости удалять отдельные серверы переднего сервера перед удалением пула переднего сервера. При удалите пул, удалите каждый сервер переднего сервера.
  
### <a name="to-remove-a-front-end-server-from-a-pool"></a>Удаление сервера переднего плана из пула

1. On the Skype for Business Server 2019 Front End Server, open Topology Builder.
    
2. Перейдите к устаревшему узлу установки.
    
3. Развернув пулы переднего сервера **Enterprise Edition,** развернув пул переднего сервера с сервером переднего сервера, который нужно удалить, щелкните правой кнопкой мыши сервер переднего сервера, который нужно удалить, и выберите "Удалить". 
    

