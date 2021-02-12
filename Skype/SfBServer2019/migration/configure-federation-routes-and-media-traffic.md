---
title: Настройка маршрутов федерации и трафика мультимедиа
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
description: Федерация — это доверительные отношения между двумя или более SIP-доменами, которые позволяют пользователям в различных организациях обмениваться информацией через сетевые границы. После миграции в пилотный пул необходимо перейти с федера>федера>маршрутов серверов предыдущих версий на федерательный маршрут для ваших серверов Skype для бизнеса Server 2019.
ms.openlocfilehash: 2fafe991b8d09a477d084bdf2081d240e4830589
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754039"
---
# <a name="configure-federation-routes-and-media-traffic"></a>Настройка маршрутов федерации и трафика мультимедиа

Федерация — это доверительные отношения между двумя или более SIP-доменами, которые позволяют пользователям в различных организациях обмениваться информацией через сетевые границы. После миграции в пилотный пул необходимо перейти с федера>федера>маршрутов серверов предыдущей версии на федерательный маршрут для ваших серверов Skype для бизнеса Server 2019.
  
Используйте следующие процедуры для перехода федератора и маршрута трафика мультимедиа с сервера и директора предыдущей версии на сервер Skype для бизнеса Server 2019 для развертывания на одном сайте.
  
> [!IMPORTANT]
> Для изменения маршрута федерации и маршрута трафика мультимедиа необходимо запланировать простои обслуживания для skype для бизнеса Server 2019 и серверов предыдущей версии. Весь процесс перехода также означает, что федеративный доступ будет отключен во время простоя. Следует запланировать простой на период, когда активность пользователей будет минимальной. Также следует реализовать своевременное уведомление конечных пользователей. Тщательно запланируйте простой и задайте соответствующие ожидания в организации. 
  
> [!IMPORTANT]
> Если устаревший edge-сервер настроен на использование одного и того же FQDN для службы доступа, службы веб-службы и службы A/V Edge, процедуры в этом разделе не поддерживаются. If the legacy Edge services are configured to use the same FQDN, you must first migrate all your users, then decommission the previous versions Edge Server before enabling federation on the Skype for Business Server 2019 Edge Server. 
  
> [!IMPORTANT]
> If your XMPP federation is routed through a Skype for Business Server 2019 Edge Server, users on the previous version will not be able to communicate with the XMPP federated partner until all users have been moved to Skype for Business Server 2019, XMPP policies and certificates have been configured, the XMPP federated partner has been configured on Skype for Business Server 2019 , и, наконец, были обновлены записи DNS. 
  
## <a name="to-remove-the-legacy-federation-association-from-skype-for-business-server-2019-sites"></a>Удаление устаревшей связи федерации с сайтов Skype для бизнеса Server 2019

1. На сервере переднего сервера Skype для бизнеса Server 2019 откройте существующую топологию в построителье топологий. 
    
2. В левой области перейдите к узлу сайта, расположенного непосредственно под **Skype для бизнеса Server.**
    
3. Щелкните сайт правой кнопкой мыши и выберите команду **Изменить свойства**.
    
4. В левой области выберите **Федеративный маршрут**. 
    
5. В области назначения маршрута  федерации **сайта** с помощью этого окне с помощью этого окне необходимо отключить федерацийный маршрут через устаревшую среду. 
  
6. Нажмите кнопку **ОК**, чтобы закрыть страницу "Изменение свойств". 
    
7. В **построителье** топологий выберите верхний узел **Skype для бизнеса Server.**
    
8. В меню **Действие** выберите пункт **Опубликовать топологию**.
    
9. Нажмите **кнопку** "Далее", чтобы завершить процесс публикации, а затем нажмите кнопку **"Готово"** после завершения публикации. 
    
## <a name="to-configure-the-legacy-edge-server-as-a-non-federating-edge-server"></a>Настройка устаревшего пограничного сервера в качестве пограничного сервера без федерации

1. В левой области перейдите к устаревшему узлу установки, а затем к узлу **"Пулы edge".** 
    
2. Щелкните правой кнопкой мыши пограничный сервер и выберите в контекстном меню пункт **Изменить свойства**.
    
3. Выберите **Общие** в левой панели. 
    
4. Clear the **Enable federation for this Edge pool (port 5061)** check box and select **OK** to close the page. 
  
5. В меню **Действие** выберите пункт **Публикация топологии**, а затем щелкните **Далее**.
    
6. После завершения работы **мастера публикации**, нажмите кнопку **Готово**, чтобы закрыть мастер. 
    
7. Убедитесь, что федерация для устаревшего сервера в построителье топологий отключена.
  
## <a name="to-configure-certificates-on-the-legacy-edge-server"></a>Настройка сертификатов на устаревшем сервере

1. Экспортировать сертификат внешнего прокси-сервера доступа с закрытым ключом с устаревшего сервера. 
    
2. На сервере Skype для бизнеса Server 2019 и импортировать внешний сертификат прокси-сервера Доступа из предыдущего шага.
    
3. Назначьте внешний сертификат прокси-сервера доступа внешнему интерфейсу Skype для бизнеса Server 2019 на edge Server.
    
4. Сертификат внутреннего интерфейса сервера Skype для бизнеса Server 2019 необходимо запросить у доверенного ЦС и на назначенном ему. 
    
## <a name="to-change-the-previous-versions-federation-route-to-use-skype-for-business-server-2019-edge-server"></a>Изменение маршрута федерации предыдущей версии на использование skype для бизнеса Server 2019 Edge Server

1. From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the Edge **pools** node. 
    
2. Щелкните правой кнопкой мыши пограничный сервер и выберите в контекстном меню пункт **Изменить свойства**.
    
3. Выберите **Общие** в левой панели. 
    
4. Выберите для этого пула **(порт 5061)** включить федерацию, а затем нажмите кнопку "ОК", чтобы закрыть страницу.  
  
5. В меню **Действие** выберите пункт **Публикация топологии**, а затем щелкните **Далее**.
    
6. После завершения работы **мастера публикации**, нажмите кнопку **Готово**, чтобы закрыть мастер. 
    
7. **Убедитесь, что для федерации (порт 5061)** установлено **"Включено"** в построителье топологий.
    
  
## <a name="to-update-skype-for-business-server-2019-edge-server-federation-next-hop"></a>Обновление следующего перехода федерации для skype для бизнеса Server 2019

1. From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the Edge **pools** node. 
    
2. Разверните узел, щелкните правой кнопкой указанный пограничный сервер и выберите команду **Изменить свойства**. 
    
3. On the **General** page, under **Next hop selection,** select from the drop-down list the Skype for Business Server 2019 pool.
  
4. Нажмите кнопку **ОК**, чтобы закрыть страницу "Изменение свойств". 
    
5. В **построителье** топологий выберите верхний узел **Skype для бизнеса Server.** 
    
6. В меню **Действие** выберите команду **Опубликовать топологию** и завершите работу мастера. 
    
## <a name="to-configure-skype-for-business-server-2019-edge-server-outbound-media-path"></a>Настройка пути исходящие мультимедиа для сервера Skype для бизнеса Server 2019

1. From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the pool below Standard Edition Front End **Servers** or **Enterprise Edition Front End pools**.
    
2. Щелкните пул правой кнопкой мыши и выберите команду **Изменить свойства**.
    
3. В разделе **Связи** установите флажок **Связать пограничный пул (для компонентов мультимедиа)**. 
  
4. В выпадаемом поле выберите сервер Skype для бизнеса Server 2019.
    
5. Нажмите кнопку **ОК**, чтобы закрыть страницу **изменения свойств**. 
    
## <a name="to-turn-on-skype-for-business-server-2019-edge-server-federation"></a>Чтобы включить федерацию skype для бизнеса Server 2019 Edge Server

1. From Topology Builder, in the left pane, navigate to the **Skype for Business Server 2019** node and then to the Edge **pools** node. 
    
2. Разверните узел, щелкните правой кнопкой указанный пограничный сервер и выберите команду **Изменить свойства**. 
    
    > [!NOTE]
    > Федерацию можно включить только для одного пула. Если у вас несколько пулов, выберите один из них, который будет использовать в качестве федерательных пулов. 
  
3. На странице **"Общие"** убедитесь, что для этого пула **(порт 5061)** выбрана федерация. 
  
4. Нажмите кнопку **ОК**, чтобы закрыть страницу "Изменение свойств". 
    
5. Перейдите к узлу сайта. 
    
6. Щелкните сайт правой кнопкой мыши и выберите команду **Изменить свойства**.
    
7. В левой области, выберите **Федеративный маршрут**.
    
8. Under **Site federation route assignment**, select Enable **SIP federation**, and then from the list select the Skype for Business Server 2019 Edge Server listed. 
  
9. Нажмите кнопку **ОК**, чтобы закрыть страницу **Изменение свойств**. 
    
     В случае развертывании с несколькими сайтами выполните эту процедуру на каждом сайте. 
    
## <a name="to-publish-edge-server-configuration-changes"></a>Публикация изменений конфигурации пограничного сервера

1. В **построителье** топологий выберите верхний узел **Skype для бизнеса Server.** 
    
2. В меню **Действие** выберите команду **Опубликовать топологию** и завершите работу мастера. 
    
3. Дождитесь выполнения репликации Active Directory во всех пулах в развертывании.
    
    > [!NOTE]
    > Может появиться следующее сообщение: **Warning: The topology contains more than one Federated Edge Server. Это может произойти во время миграции на более новую версию продукта. В этом случае для федерации будет активно использоваться только один сервер. Убедитесь, что внешняя запись DNS SRV указывает на правильный сервер. Если вы хотите одновременно развернуть несколько федературных edge server (т. е. не сценарий миграции), убедитесь, что все федературные партнеры используют Skype для бизнеса Server. Убедитесь, что внешняя запись DNS SRV содержит список всех включенных в федерацию серверов.** Появление этого предупреждения ожидаемое и его можно спокойно проигнорировать. 
  
## <a name="to-configure-skype-for-business-server-2019-edge-server"></a>Настройка skype для бизнеса Server 2019 Edge Server

1. Перенесите все серверы Skype для бизнеса Server 2019 в сетевой режим. 
    
2. Обновите правила маршрутки внешнего брандмауэра или параметры аппаратного балансира нагрузки, чтобы отправлять трафик SIP для внешнего доступа (обычно порт 443) и федерации (обычно порт 5061) на сервер Skype для бизнеса Server 2019, а не на устаревший сервер.
    
    > [!NOTE]
    > If you do not have a hardware load balancer, you need to update the DNS A record for federation to resolve to the new Skype for Business Server Access Edge server. To accomplish this with minimal disruption, reduce the TLL value for the external Skype for Business Server Access Edge FQDN so that when DNS is updated to point to the new Skype for Business Server Access Edge, federation and remote access will be updated quickly. 
  
3. Остановите **по краям доступа Skype для бизнеса Server** на каждом компьютере с edge Server. 
    
4. На каждом компьютере устаревшего сервера edge server откройте applet **служб** из средства **администрирования.**
    
5. In the services list, find **Skype for Business Server Access Edge**.
    
6. Щелкните правой кнопкой имя служб, а затем выберите команду **Остановить**, чтобы остановить службу. 
    
7. Выберите тип запуска **Отключено**. 
    
8. Нажмите кнопку **ОК**, чтобы закрыть окно **Свойства**. 
    

