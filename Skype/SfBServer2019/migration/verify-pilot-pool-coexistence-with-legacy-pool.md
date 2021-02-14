---
title: Проверка возможности совместного использования пилотного и старого пула
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
description: Проверка сосуществования пилотного пула с устаревшим пулом.
ms.openlocfilehash: e9fe944c03c88aad2ca2b40f0e995842363e7a85
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751661"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Проверка возможности совместного использования пилотного и старого пула

 **Содержание**
  
[Проверка того, что службы Skype для бизнеса Server 2019 запущены](#sectionSection0)
  
[Открытие панели управления Skype для бизнеса Server 2019](#sectionSection1)
  
[Не пытайтесь открыть топологию в устаревшем построитель топологий](#sectionSection2)
  
После развертывания пилотного пула вам требуется проверить сосуществование двух пулов, воспользовавшись средствами администрирования для просмотра информации о пуле. Для пулов Skype для бизнеса Server 2019 и устаревших пулов необходимо использовать панель управления Skype для бизнеса Server 2019 и средства построитель топологий. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Проверка того, что службы Skype для бизнеса Server 2019 запущены
<a name="sectionSection0"> </a>

1. From the Skype for Business Server 2019 Front End Server, navigate to the Administrative Tools\Services applet.
    
2. Убедитесь, что на сервере переднего плана запущены следующие службы:

    - Агент централизованной службы ведения журналов.
    - Совместное использование приложений
    - Служба проверки аудиосвязи
    - Аудио- и видеоконференция
    - Парковка вызовов
    - Извещание оглавлении для видеоконференций
    - Помощник по конференцию
    - Внешний интерфейс
    - IM Conferencing
    - Посредник
    - Агент репликатора репликации
    - Группа ответа
    - Веб-конференции
    - Шлюз перевода XMPP

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Открытие панели управления Skype для бизнеса Server 2019
<a name="sectionSection1"> </a>

На сервере переднего сервера в развертывании Skype для бизнеса Server 2019 откройте панель управления Skype для бизнеса Server 2019 и выберите устаревший пул. Повторите эту процедуру, чтобы открыть пул Skype для бизнеса Server 2019.
  
> [!IMPORTANT]
> В Skype для бизнеса Server 2019 необходимо обновить Silverlight до silverlight версии 5, прежде чем использовать панель управления Skype для бизнеса Server. 
  
Эта топология теперь включает устаревшие роли сервера и роли сервера Skype для бизнеса Server 2019. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Не пытайтесь открыть топологию в устаревшем построитель топологий
<a name="sectionSection2"> </a>

Топологию можно просмотреть только с помощью построитель топологий Skype для бизнеса Server 2019. Skype for Business Server 2019 Topology Builder must be used to create pools for both Skype for Business Server 2019 and the legacy install.

  

