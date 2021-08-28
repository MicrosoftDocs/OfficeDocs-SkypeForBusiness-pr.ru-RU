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
ms.localizationpriority: medium
description: Процесс проверки сосуществования пилотного пула с устаревшим пулом.
ms.openlocfilehash: 5d2e6adad0f3297260137df0abcd082b750f0345
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606818"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Проверка возможности совместного использования пилотного и старого пула

 **Содержание**
  
[Проверка начала Skype для бизнеса Server 2019 г.](#sectionSection0)
  
[Откройте панель Skype для бизнеса Server 2019 г.](#sectionSection1)
  
[Не пытайтесь открыть топологию в устаревшем конструкторе топологии](#sectionSection2)
  
После развертывания пилотного пула вам требуется проверить сосуществование двух пулов, воспользовавшись средствами администрирования для просмотра информации о пуле. Для пулов Skype для бизнеса Server 2019 г. и устаревших пулов необходимо использовать средства управления Skype для бизнеса Server 2019 г. и средства topology Builder. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Проверка начала Skype для бизнеса Server 2019 г.
<a name="sectionSection0"> </a>

1. С Skype для бизнеса Server 2019 front End Server перейдите в applet Administrative Tools\Services.
    
2. Убедитесь, что на сервере переднего плана запущены следующие службы:

    - Агент централизованной службы ведения журналов.
    - Совместное использование приложений
    - Служба тестирования звука
    - Аудио- и видеоконференция
    - Парковка вызовов
    - оповещение для конференц-связи
    - помощник по конференц-связи
    - Внешний интерфейс
    - IM Conferencing
    - Посредничество
    - Агент репликатора
    - Группа ответа
    - Веб-конференции
    - Шлюз для перевода XMPP

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Откройте панель Skype для бизнеса Server 2019 г.
<a name="sectionSection1"> </a>

На переднем сервере в развертывании Skype для бизнеса Server 2019 г. откройте панель управления Skype для бизнеса Server 2019 г. и выберите устаревший пул. Повторите процедуру, чтобы открыть Skype для бизнеса Server 2019.
  
> [!IMPORTANT]
> В Skype для бизнеса Server 2019 г. перед использованием панели управления Skype для бизнеса Server Silverlight необходимо обновить Silverlight до версии 5 Silverlight. 
  
Эта топология теперь включает устаревшие и Skype для бизнеса Server 2019 серверных ролей. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Не пытайтесь открыть топологию в устаревшем конструкторе топологии
<a name="sectionSection2"> </a>

Топология может быть просмотрена только с помощью Skype для бизнеса Server 2019 Topology Builder. Конструктор топологии Skype для бизнеса Server 2019 года должен использоваться для создания пулов как для Skype для бизнеса Server 2019 г., так и для устаревшей установки.

  

