---
title: Развертывание пилотного пула
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
description: Одним из первых этапов миграции в Skype для бизнеса Server 2019 является развертывание пилотного пула. Пилотный пул — это место тестирования сосуществования Skype для бизнеса Server 2019 с устаревшим развертыванием. Сосуществование — это временное состояние, которое длится до тех пор, пока вы не переместили всех пользователей и пулы в Skype для бизнеса Server 2019.
ms.openlocfilehash: 46d8b6fd6cefa2894f67a1c24732ace01ca65785
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752861"
---
# <a name="deploy-skype-for-business-server-2019-pilot-pool"></a>Развертывание пилотного пула Skype для бизнеса Server 2019

Одним из первых этапов миграции в Skype для бизнеса Server 2019 является развертывание пилотного пула. Пилотный пул — это место тестирования сосуществования Skype для бизнеса Server 2019 с устаревшим развертыванием. Сосуществование — это временное состояние, которое длится до тех пор, пока вы не переместили всех пользователей и пулы в Skype для бизнеса Server 2019. 
  
При развертывании пилотной версии пула используется мастер определения нового интерфейсного пула. В пилотном пуле Skype для бизнеса Server 2019 необходимо развернуть те же функции и рабочие нагрузки, что и в устаревшем пуле. Если вы развернули сервер архивации, сервер мониторинга или System Center Operations Manager для архивации или мониторинга устаревшей среды и хотите продолжить архивацию или мониторинг во время миграции, необходимо также развернуть эти функции в пилотной среде. Версия, развернутая для архива или мониторинга устаревшей среды, не будет захватывать данные в среде Skype для бизнеса Server 2019. 
  
> [!NOTE]
> В описании следующей процедуры рассматриваются компоненты и настройки, которые следует использовать в рамках общего процесса развертывания пилотной версии пула. В этом разделе рассматриваются только ключевые моменты, которые следует учитывать при развертывании пилотной версии пула. <!-- For detailed steps, refer to the 
 [Deploying Skype for Business Server 2019](../deployment/deploying-lync-server-2013/deploying-lync-server-2013.md) deployment guide.  -->
  
### <a name="to-deploy-a-skype-for-business-server-2019-pilot-pool"></a>Развертывание пилотного пула Skype для бизнеса Server 2019

1. Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.
    
2. Разверять дерево, пока не достигнете пулов переднего сервера Skype для бизнеса **Server 2019**  >  **Enterprise Edition.**
    
3. Щелкните правой **кнопкой мыши пулы переднего** входа Enterprise Edition и выберите **"Новый пул переднего входа".**
  
4. Введите полное доменное имя пула. При выборе пилотного пула можно выбрать развертывание пула переднего сервера Enterprise Edition или сервера Standard Edition. Skype для бизнеса Server 2019 не требует, чтобы функции пилотного пула совпадали с возможностями, развернутными в устаревшем пуле.
    
    > [!CAUTION]
    > Пул или серверное FQDN, задаваемое для пилотного пула, должно быть уникальным. Он не может совпадать с именем развернутого в настоящее время устаревшего пула или любых других развернутых в настоящее время серверов. 
  
5. На странице **Выбор компонентов** установите флажки рядом с теми компонентами, которые вы хотите добавить в этот интерфейсный пул. Например, если развертываются только функции обмена мгновенными сообщениями и присутствием, необходимо выбрать флажок "Разрешить многостороннее обмен мгновенными сообщениями", но не флажки для телефонной связи, Корпоративная голосовая связь или контроля допуска вызовов, так как они представляют функции голосовой связи, видеосвязи и совместной работы. <!-- For additional information on selecting features, see 
 [Define and configure a Front End pool or Standard Edition server in Skype for Business Server 2019](../deployment/deploying-lync-server-2013/define-and-configure-a-front-end-pool-or-standard-edition-server.md) in the Deployment documentation.  -->
  
6. On the **Select collocated server roles** page, we recommend that you choose to collocate the Mediation Server in Skype for Business Server 2019. При объединении устаревшей топологии со Skype для бизнеса Server 2019 необходимо сначала выполнив вместе сервер-посредник прежних версиях. After merging the topologies and configuring the Skype for Business Server 2019 Mediation Server, you can decide whether to keep the collocated Mediation Server, or change it to a stand-alone server when you move the Mediation Server role to Skype for Business Server 2019 later in the deployment process. 
   
7. На странице **"Связывание** ролей сервера с этим пулом переднего плана" во время развертывания пилотного пула не выбирайте параметр "Включить пул" для использования компонентом мультимедиа этого пула переднего **плана.**  Эта функция включается и активируется на более позднем этапе миграции. Пока не устанавливайте этот флажок. 
  
8. На странице **Выбор сервера Office Web Apps** выберите **Создать** и укажите полное доменное имя сервера приложений.
  
9. На  странице "Определение SQL Server архива" при определении SQL Server для архива и мониторинга Skype для бизнеса Server выберите экземпляр SQL Server, созданный ранее для Skype для бизнеса Server 2019. 
  
10. Чтобы опубликовать топологию, щелкните правой кнопкой мыши узел **Skype для** бизнеса Server и выберите "Опубликовать **топологию".**
  
11. По завершении процесса публикации нажмите **Готово**.

12. Перед переходом к следующему разделу под названием "Проверка сосуществования пилотного пула с устаревшим пулом" необходимо установить новый пилотный пул переднего плана Skype для бизнеса Server, который мы только что определили в опубликованной топологии, следуя процедурам, описанным в статье Установка Skype для бизнеса Server на серверах в [топологии](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)

13. После завершения предыдущего шага переходить к следующему разделу, чтобы проверить сосуществование пилотного пула с устаревшим пулом.
    
<!-- To install a local copy of the configuration store and start the required services, see 
[Setting up Front End Servers and Front End pools for Skype for Business Server 2019](../deployment/deploying-lync-server-2013/setting-up-front-end-servers-and-front-end-pools.md) in the Deployment documentation.  -->
  

