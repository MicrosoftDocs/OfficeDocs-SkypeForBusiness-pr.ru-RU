---
title: Настройка компьютеров Skype для бизнеса Server для мониторинга
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b24ea184-4b3e-4277-a244-157afb4b368b
description: 'Сводка: Установите на компьютере с операционной системой Skype для Business Server 2015 файлы агента Operations Manager и настройте компьютер так, чтобы он действовал как прокси System Center.'
ms.openlocfilehash: f5da9d309fd2353fbfd4009b825b731074c81fbb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816138"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a>Настройка компьютеров Skype для бизнеса Server для мониторинга

**Сводка:** Установите файлы агента Operations Manager на компьютере Skype для бизнеса Server 2015 и настройте компьютер так, чтобы он действовал как прокси System Center.

Каждый сервер Skype для бизнеса Server 2015, на котором вы хотите наблюдать, должен иметь возможность самостоятельного отчета о существовании сервера управления. Этот процесс возможен только после установки файлов агента Operations Manager на каждом из таких компьютеров. После установки файлов агента необходимо настроить компьютер для работы в качестве прокси-сервера System Center. Перед выполнением этих процедур убедитесь, что вы установили и настроили сервер Skype для бизнеса на этих компьютерах.

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a>Установка сертификата на узел-наблюдатель, расположенный вне сети периметра
<a name="watcher_node_outside"> </a>

Агенты System Center Operations Manager, работающие в демилитаризованной зоне (например, на пограничном сервере Skype для бизнеса Server), вне Организации (например, на внешнем виртуальном узле наблюдения за транзакциями) или на границе доверия Active Directory, могут потребовать Конфигурация сервера шлюза System Center Operations Manager. This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts. Подробные сведения можно найти [в разделе Управление серверами шлюзов в Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).

Если вы развертываете агент в одном из этих местоположений, вам также потребуется запросить и настроить сертификат, который позволит узлу-наблюдателю отправлять оповещения в System Center Operations Manager. Для упрощения этого процесса группа Operations Manager создала набор служебных программ, которые позволят вам запросить и установить правильный тип сертификата на компьютере с узлом-наблюдателем. Сведения о том, как скачать эти служебные программы, можно найти в разделе [Получение сертификатов для агентов, не присоединенных к домену, которые упрощают работу с мастером создания сертификатов](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).

### <a name="installing-the-operation-manager-agent-files"></a>Установка файлов агента Operation Manager

1. В установочном носителе System Center дважды щелкните **SetupOM.exe**.

2. В мастере настройки System Center Operations Manager выберите команду **установить агент Operations Manager**, из установки агента в разделе необязательные установки

3. В мастере настройки System Center на странице Добро пожаловать на страницу мастера установки System Center Operations Manager нажмите кнопку **Далее**.

4. На странице Конечная папка выберите папку, в которую будут установлены файлы агента Operations Manager, и нажмите кнопку **Далее**.

5. На странице "Конфигурация группы управления" выберите **Указать сведения о группе управления** и нажмите кнопку **Далее**.

6. На странице Конфигурация группы управления введите имя группы управления Operations Manager в поле **имя группы управления** , а затем введите имя узла сервера Operations Manager (например, ATL-SCOM-001) в поле **сервер управления** . Если номер порта, используемый программой Operations Manager, изменен, введите новый номер порта в поле **Порт сервера управления**. В противном случае оставьте для порта значение по умолчанию 5723, затем нажмите кнопку **Далее**.

7. На странице "Учетная запись действий агента" выберите **Локальная система** и нажмите кнопку **Далее**.

8. On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.

9. На странице "Все готово для установки" нажмите кнопку **Установить**.

10. На странице Завершение работы мастера установки System Center Operations Manager нажмите кнопку **Готово**.

11. Нажмите кнопку **Выход**.

Чтобы проверить, создан ли агент System Center 2012, нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **System Center Operations Manager 2012**, а затем — команду **Operations 2012 Manager Shell**. In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:
```PowerShell
Get-SCOMAgent
```

Отображается список всех агентов Operations Manager.
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a>Настройка компьютера Skype для бизнеса Server для участия в обнаружении System Center
<a name="watcher_node_outside"> </a>

Чтобы убедиться в том, что новый агент сервера Skype для бизнеса входит в процесс обнаружения для System Center Operations Manager, необходимо выполнить описанные ниже действия для каждого компьютера, на котором установлена консоль System Center Operations Manager.

1. На вкладке "Администрирование" щелкните **Управляемые агентом**.

2. Щелкните **мастер обнаружения** обнаружьте компьютер с помощью мастера.

3. Перезапустите службу агента работоспособности. При перезапуске службы принудительно выполняется обнаружение нового компьютера. Если вы не перезагрузите службу, система System Center Operations Manager может занять до 4 часов, пока новый компьютер не будет найден.

4. Проверьте отсутствие записей об ошибках в журнале событий Operations Manager.

5. Компьютер, на котором агент отправляется успешно, отображается в разделе "управляемый агентом список", а на компьютере, на котором установлен агент вручную, в разделе "ожидание управления" щелкните имя компьютера и подтвердите его.

6. 	Right-click the name of the computer, and then click **Properties**. In the Properties dialog box, on the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.


