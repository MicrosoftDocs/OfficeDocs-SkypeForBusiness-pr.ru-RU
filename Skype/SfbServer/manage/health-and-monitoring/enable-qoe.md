---
title: Обеспечение качества взаимодействия в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Сводка: сведения о том, как включить качество взаимодействия (QoE) в Skype для бизнеса Server.'
ms.openlocfilehash: 90110c5664e80ac1d4f9d382c20e0fd58d9ce134
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34305712"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a>Обеспечение качества взаимодействия в Skype для бизнеса Server

**Сводка:** сведения о том, как включить качество взаимодействия (QoE) в Skype для бизнеса Server.

Служба отслеживания качества взаимодействия (QoE) записывает числовые данные, которые показывают качество мультимедиа-данных, и сведения об участниках, именах устройств, драйверах, IP-адресах и типах конечных точек, использованных во время звонка или сеанса. Подробные сведения см. в разделе [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) документации по планированию.

Используйте следующую процедуру для включения службы качества взаимодействия для всей организации или для отдельных сайтов в организации.

> [!NOTE]
> Чтобы включить службу качества взаимодействия, сначала необходимо настроить мониторинг и внутреннюю базу данных мониторинга. Дополнительные сведения см. в разделе [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a>Включение QoE с помощью панели управления Skype для бизнеса Server

1.  Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .

2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.

3. На панели навигации слева нажмите **Мониторинг и архивация**, затем выберите **Данные о качестве взаимодействия**.

4. На странице **данных качества взаимодействия** выберите соответствующую коллекцию в таблице и последовательно выберите пункты **Действие** и **Включить отслеживание качества взаимодействия**.

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Включение QoE с помощью командлетов Windows PowerShell

Вы можете включить QoE с помощью Windows PowerShell и командлета **Set-кскоеконфигуратион** . Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876). Этот процесс одинаков в Skype для бизнеса Server.

### <a name="to-enable-qoe-for-a-single-location"></a>Включение службы качества взаимодействия для одного расположения

 Чтобы включить службу качества взаимодействия, установите параметр EnableQoE в значение True ($True).

  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a>Отключение службы качества взаимодействия для одного расположения

 Чтобы отключить службу качества взаимодействия, установите параметр EnableQoE в значение False ($False). При этом мониторинг не будет удален. Он приостановит сбор и хранение данных качества взаимодействия.

  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>Использование одной команды для включения службы качества взаимодействия в нескольких расположениях

 Следующая команда включает службу качества взаимодействия для всех параметров конфигурации качества взаимодействия, используемых в текущий момент в организации.

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

Подробности можно найти в разделе [Set-кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).

## <a name="see-also"></a>См. также

[Планирование мониторинга](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

