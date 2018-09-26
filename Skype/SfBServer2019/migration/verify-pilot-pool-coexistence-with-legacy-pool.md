---
title: Проверка возможности совместного использования пилотного пула прежних версий
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Процесс проверка возможности совместного использования пилотного пула прежних версий.
ms.openlocfilehash: 717726acd3654abb2296d622afc5a4d45009430e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028693"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Проверка возможности совместного использования пилотного пула прежних версий

 **В этой статье**
  
[Проверка запуска Скайп для служб Business Server 2019](#sectionSection0)
  
[Откройте Скайп для панели управления Business Server 2019](#sectionSection1)
  
[Не пытайтесь открыть данную топологию в построителе топологии прежних версий](#sectionSection2)
  
После развертывания пилотного пула необходимо проверить сосуществования двух пулов с помощью средства администрирования, чтобы просмотреть сведения о пуле. Для Скайп для пулов Business Server 2019 и старых пулов необходимо использовать Скайп средства панели управления 2019 Business Server и построитель топологий. 
  
## <a name="verify-that-skype-for-business-server-2019-services-have-started"></a>Проверка запуска Скайп для служб Business Server 2019
<a name="sectionSection0"> </a>

1. Из Скайп для сервера переднего плана Business Server 2019 перейдите в приложение административных средств и служб.
    
2. Убедитесь, что на сервере переднего плана запущены следующие службы:

    - Агент службы централизованного ведения журналов
    - Общий доступ к приложениям
    - Служба проверки звука
    - Аудио-и видеоконференций
    - Приостановка вызовов
    - Оповещения для конференц-связи
    - Помощник по конференц-связи
    - Переднего плана
    - Обмен мгновенными Сообщениями конференц-связи
    - Посредник
    - Агент репликации реплики
    - "Группа ответа"
    - Веб-конференции
    - Перевод шлюза XMPP

  
## <a name="open-the-skype-for-business-server-2019-control-panel"></a>Откройте Скайп для панели управления Business Server 2019
<a name="sectionSection1"> </a>

С сервера переднего плана в вашей Скайп Business Server 2019 развертывания откройте Скайп для панели управления 2019 Business Server и выберите устаревшего пула. Повторите процедуру, чтобы открыть Скайп для пула Business Server 2019.
  
> [!IMPORTANT]
> На Скайп для Business Server 2019 следует обновить продукт Silverlight до версии 5 перед использованием Скайп для панели управления Business Server. 
  
Эта топология теперь включает прежних версий и Скайп для ролей сервера Business Server 2019. 

  
## <a name="dont-attempt-to-open-the-topology-in-the-legacy-topology-builder"></a>Не пытайтесь открыть данную топологию в построителе топологии прежних версий
<a name="sectionSection2"> </a>

При попытке открыть топологии, с помощью устаревшего Topology Builder возникнет ошибка ниже. Топология можно просматривать только с помощью Скайп for Business Server 2019 Topology Builder. Скайп для Business Server 2019 Topology Builder необходимо используется для создания пулов для Скайп для Business Server 2019 и установки прежних версий.

  

