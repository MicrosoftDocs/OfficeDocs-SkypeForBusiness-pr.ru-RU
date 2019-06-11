---
title: 'Lync Server 2013: создание профилей политики пропускной способности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9464e83370690e018374c4ffb60e0b61c30fe300
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834854"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a>Создание профилей политики пропускной способности в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-19_

*Политики пропускной способности* определяют ограничения пропускной способности сети для режимов передачи звука и видеоизображения в реальном времени. Политики пропускной способности применяются к *профилям политики пропускной способности*, которые могут применяться к нескольким сетевым сайтам для контроля допуска звонков.

Рекомендации по выбору ограничений пропускной способности, которые следует настроить в развертывании CAC, описаны в разделе [Определение требований к управлению допуском звонков в Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) в документации по планированию.

Дополнительные сведения о работе с политиками пропускной способности и профилями политики можно найти в документации по оболочке Lync Server Management Shell для следующих командлетов:

  - [New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

Примеры политик, созданных в следующей процедуре, задают ограничения для общего трафика аудиоданных, отдельных аудиосеансов, общего трафика видеоданных и отдельных видеосеансов. Например, в профиле\_политики пропускной способности связи объемом 5 задаются указанные ниже ограничения.

  - Аудиоданные: 2 000 кбит/с

  - Аудиосеансы: 200 кбит/с

  - Видеоданные: 1 400 кбит/с

  - Видеосеансы: 700 кбит/с

<div class=" ">


> [!NOTE]  
> Минимальное значение для аудиосеанса 40 кбит/с. Минимальное значение для видеосеанса 100 кбит/с.



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a>Создание профилей политики пропускной способности с помощью командной консоли

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Выполните командлет New-CsNetworkBandwidthPolicyProfile для каждого создаваемого профиля политики пропускной способности. Пример:
    
       ```
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a>Создание профилей политики пропускной способности с помощью панели управления Lync Server

1.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой области навигации щелкните **Конфигурация сети**.

3.  Нажмите кнопку навигации **Профиль политики**.

4.  Выберите **Создать**.

5.  На странице **создания профиля политики** в поле щелкните **Имя**, затем введите имя профиля политики пропускной способности.

6.  Щелкните **Ограничение для звукового сеанса**, затем введите максимальную скорость в кбит/с, общую для всех сеансов звуковой связи.

7.  Щелкните **Ограничение для видео**, затем введите максимальную скорость в кбит/с для отдельного сеанса звуковой связи.

8.  Щелкните **Ограничение для видео**, затем введите максимальную скорость в кбит/с, общую для всех сеансов видеосвязи.

9.  Щелкните **Ограничение для видеосеанса**, затем введите максимальную скорость в кбит/с для отдельного сеанса видеосвязи.

10. Щелкните **Описание** и введите дополнительные сведения о профиле политики пропускной способности (не обязательно).

11. Нажмите **Исполнить**.

12. Чтобы завершить создание профилей политики пропускной способности для топологии, повторите шаги с 4 по 11 для остальных профилей политики пропускной способности.

</div>

</div>

<span> </span>

</div>

</div>

</div>

