---
title: Сброс контроля допуска звонков
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Если в устаревшем пуле переднего конца размещено управление приемом вызовов (CAC), необходимо переместить размещение CAC в пул Skype для бизнеса Server 2019 г., прежде чем удалить устаревший пул переднего конца.
ms.openlocfilehash: f660f14adfcdee64d9fa4c79e08393d4f0a0af2d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583453"
---
# <a name="reset-call-admission-control"></a>Сброс контроля допуска звонков

Если в устаревшем пуле переднего конца размещено управление приемом вызовов (CAC), необходимо переместить размещение CAC в пул Skype для бизнеса Server 2019 г., прежде чем удалить устаревший пул переднего конца.
  
### <a name="to-reset-cac"></a>Чтобы сбросить контроль допуска звонков

1. Откройте построитель топологий.
    
2. Щелкните правой кнопкой мыши узел сайта, затем выберите **Изменить свойства**.
    
3. Убедитесь, что в разделе **Параметры контроля допуска звонков** выбран параметр **Включить контроль допуска звонков**. 
    
4. В **пуле Переднего** конца для запуска управления приемом вызовов (CAC) выберите пул Skype для бизнеса Server 2019, который должен принимать CAC, а затем нажмите **кнопку ОК**.
    
5. Опубликуйте топологию.
    

