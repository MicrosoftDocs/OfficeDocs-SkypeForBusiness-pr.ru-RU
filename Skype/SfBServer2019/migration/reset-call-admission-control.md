---
title: Сброс контроля допуска звонков
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Если в устаревшем пуле переднего плана размещается управление допуском звонков (CAC), перед удалением устаревшего пула переднего плана необходимо переместить сервер CAC в пул 2019 в Skype для бизнеса Server.
ms.openlocfilehash: cbc481e55d044ef196bd91dbfa8f7ebc796f28b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812807"
---
# <a name="reset-call-admission-control"></a>Сброс контроля допуска звонков

Если в устаревшем пуле переднего плана размещается управление допуском звонков (CAC), перед удалением устаревшего пула переднего плана необходимо переместить сервер CAC в пул 2019 в Skype для бизнеса Server.
  
### <a name="to-reset-cac"></a>Чтобы сбросить параметры CAC

1. Открытие построителя топологии.
    
2. Щелкните правой кнопкой мыши узел сайта и выберите команду **изменить свойства**.
    
3. Убедитесь, что в разделе **параметр управления**допуском звонков установлен флажок **включить управление допуском звонков** . 
    
4. В разделе **пул переднего плана, чтобы запустить управление допуском звонков (CAC)**, выберите пул 2019 Skype для бизнеса Server, на котором размещается CAC, и нажмите кнопку **ОК**.
    
5. Опубликуйте топологию.
    

