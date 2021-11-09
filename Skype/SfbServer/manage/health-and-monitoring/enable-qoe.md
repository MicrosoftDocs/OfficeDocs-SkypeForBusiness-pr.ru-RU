---
title: Включить качество работы в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: Сводка. Узнайте, как включить качество работы (QoE) в Skype для бизнеса Server.
ms.openlocfilehash: 89c6a41a356355ea5ac717a10e2848aa16d94249
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863576"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>Включить качество работы в Skype для бизнеса Server

**Сводка.** Узнайте, как включить качество работы (QoE) в Skype для бизнеса Server.

Служба качества взаимодействия (QoE) записывает числовые данные, которые показывают качество мультимедиа-данных, и сведения об участниках, именах устройств, драйверах, IP-адресах и типах конечных точек, использованных во время звонка или сеанса. Подробные сведения см. в разделе [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) документации по планированию.

Используйте следующую процедуру для включения службы качества взаимодействия для всей организации или для отдельных сайтов в организации.

> [!NOTE]
> Чтобы включить службу качества взаимодействия, сначала необходимо настроить мониторинг и внутреннюю базу данных мониторинга. Дополнительные сведения см. в разделе [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>Включить QoE с помощью панели Skype для бизнеса Server управления

1.  С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в которой вы развернули Skype для бизнеса Server.

2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления.

3. В левой навигационной панели щелкните элемент **Мониторинг и архивация** и выберите пункт **Quality of Experience Data** (Данные качества взаимодействия).

4. На странице **данных качества взаимодействия** щелкните соответствующую коллекцию в таблице и последовательно выберите пункты **Action** (Действие) и **Enable QoE** (Включить QoE).

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Включение QoE с помощью Windows PowerShell cmdlets

Вы можете включить QoE с помощью Windows PowerShell и **комлета Set-CsQoEConfiguration.** Этот комлет можно выполнить либо из Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в [материале Microsoft Lync Remote PowerShell Administration](https://blog.insideo365.com/2011/08/remote-lync-powershell-administration/). Этот процесс в Skype для бизнеса Server.

### <a name="to-enable-qoe-for-a-single-location"></a>Включение службы качества взаимодействия для одного расположения

 Чтобы включить службу качества взаимодействия, установите параметр EnableQoE в значение True ($True).

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>Отключение службы качества взаимодействия для одного расположения

 Чтобы отключить службу качества взаимодействия, установите параметр EnableQoE в значение False ($False). При этом мониторинг не будет удален. Он приостановит сбор и хранение данных качества взаимодействия.

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>Использование одной команды для включения службы качества взаимодействия в нескольких расположениях

 Следующая команда включает службу качества взаимодействия для всех параметров конфигурации качества взаимодействия, используемых в текущий момент в организации.

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

Подробные сведения [см. в материале Set-CsQoEConfiguration.](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)

## <a name="see-also"></a>См. также

[Планирование мониторинга](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[Мониторинг развертывания](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)