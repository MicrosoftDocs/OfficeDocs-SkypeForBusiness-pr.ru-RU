---
title: Настройка компьютеров Skype для бизнеса Server для мониторинга
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/7/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Сводка: Установить файлы агента Operations Manager на Скайп для компьютера Business Server 2019 для мониторинга и настроить компьютер в качестве прокси-сервер System Center.'
ms.openlocfilehash: 90608d9233bea466b523418553d5421735234aee
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875420"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Настройка компьютеров Skype для бизнеса Server для мониторинга

**Сводка:** Установить файлы агента Operations Manager на Скайп для компьютера Business Server 2019 для мониторинга и настроить компьютер в качестве прокси-сервер System Center.

Каждый Скайп для компьютера Business Server 2019, которую необходимо отслеживать должны иметь возможность самостоятельно сообщить о его существования на сервере управления. Этот процесс возможен только после установки файлов агента Operations Manager на каждом из таких компьютеров. После установки файлов агента необходимо настроить компьютер для работы в качестве прокси-сервера System Center. Убедитесь, что вы сначала установки и настройки Скайп для Business Server на следующих компьютерах перед выполнением этих процедур.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Установка сертификата на узел-наблюдатель, расположенный вне сети периметра
<a name="watcher_node_outside"> </a>

System Center Operations Manager агентов в демилитаризованной зоны сети (например, Скайп для пограничного сервера Business Server), за пределами организации (например, узел-наблюдатель внешних искусственная транзакция), или через доверия Active Directory может потребоваться границы Конфигурация шлюза системы центр Operations Manager. This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts. Для получения дополнительных сведений обратитесь к разделу [Управление Servers шлюза в Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).

Если развернуть агент в одном из этих расположений, также необходимо запрос и Настройка сертификата, который позволяет узла-наблюдателя для отправки оповещений для System Center Operations Manager. Чтобы упростить этот процесс, Operations Manager создала набор служебных программ, которые позволяют запросить и установить правильный тип сертификата на компьютере узла-наблюдателя. Для получения дополнительных сведений и загрузки этих служебных программ увидеть [Получение сертификатов для домена не присоединился к агентам простая с помощью мастера создания сертификатов](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).

### <a name="installing-the-operation-manager-agent-files"></a>Установка файлов агента Operation Manager

1. В установочном носителе System Center дважды щелкните **SetupOM.exe**.

2. В мастере установки System Center Operation Manager выберите **Установить агент Operations Manager**, из установить агент в разделе необязательные установок

3. В мастере установки System Center на начальной странице мастера установки System Center Operations Manager нажмите кнопку **Далее**.

4. На странице папка назначения выберите папку, где должны устанавливаться файлы агента Operations Manager и нажмите кнопку **Далее**.

5. На странице "Конфигурация группы управления" выберите **Указать сведения о группе управления** и нажмите кнопку **Далее**.

6. На странице Конфигурация группы управления введите имя своей группы управления Operations Manager в поле **Имя группы управления** , а затем введите имя узла сервера Operations Manager (например, atl-scom-001) в **Management Server **поле. Если номер порта, используемый программой Operations Manager, изменен, введите новый номер порта в поле **Порт сервера управления**. В противном случае оставьте для порта значение по умолчанию 5723, затем нажмите кнопку **Далее**.

7. На странице "Учетная запись действий агента" выберите **Локальная система** и нажмите кнопку **Далее**.

8. On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.

9. На странице "Все готово для установки" нажмите кнопку **Установить**.

10. На странице завершения работы мастера установки System Center Operations Manager нажмите кнопку **Готово**.

11. Нажмите кнопку **Выход**.

Для System Center 2012 вы можете проверить, что агент была создана, и нажмите кнопку **Пуск**, **Все программы**, **System Center Operations Manager 2012**и **Оболочка Operations Manager 2012 г.** In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:
```
Get-SCOMAgent
```

Отображается список всех агентов Operations Manager.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Настройка компьютера Skype для бизнеса Server для участия в обнаружении System Center
<a name="watcher_node_outside"> </a>

Чтобы убедиться в том, что ваш новый Скайп для агента Business Server участвует в процессе обнаружения для System Center Operations Manager, необходимо выполнить следующую процедуру на каждом компьютере, где была установлена консоль System Center Operations Manager.

1. На вкладке "Администрирование" щелкните **Управляемые агентом**.

2. Щелкните **мастер обнаружения** обнаружьте компьютер с помощью мастера.

3. Перезапустите службу агента работоспособности. При перезапуске службы принудительно выполняется обнаружение нового компьютера. Если вы не перезагрузите службу, может получить до 4 часов до обнаружения новый компьютер с System Center Operations Manager.

4. Проверьте отсутствие записей об ошибках в журнале событий Operations Manager.

5. Компьютер, где агент помещается успешно будут отображаться в списке «Управляемые агента» и компьютер, где была установлена агента вручную будут отображаться в разделе «Управление ожидающие», щелкните имя компьютера и утверждение.

6. 	Right-click the name of the computer, and then click **Properties**. In the Properties dialog box, on the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.


