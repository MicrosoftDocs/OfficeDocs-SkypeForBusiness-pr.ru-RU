---
title: 'Lync Server 2013: создание устройства для проверки функциональных возможностей обновления'
description: 'Lync Server 2013: создание устройства для проверки функциональных возможностей обновления.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d45d8970dc72abc8ea6095c879272394e34c54d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542175"
---
# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>Создание устройства для проверки функциональных возможностей обновления в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Вы можете добавить устройство проверки на страницу **Устройство проверки** и затем использовать его для проверки функциональных возможностей новых обновлений перед их развертыванием на производственных устройствах. Вы можете протестировать устройство глобально (во всей среде Lync Server) или на одном сайте. Устройство проверки указывается по MAC-адресу или серийному номеру. При добавлении устройства оно отображается в списке на странице " **устройство тестирования** " в панели управления Lync Server.

<div>

## <a name="to-add-a-test-device"></a>Добавление тестового устройства

1.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

2.  В левой панели навигации щелкните **Клиенты**, а затем щелкните **проверить устройство**.

3.  Нажмите кнопку **создать**, а затем выберите либо **глобальное тестовое** устройство, либо **тестическое устройство сайта**.

4.  Выполните одно из указанных ниже действий.
    
      - Если выбрано **глобальное тестовое устройство**, перейдите к следующему шагу.
    
      - Если выбрано **тестовое устройство сайта**, выберите сайт в списке доступных сайтов, а затем нажмите кнопку **ОК**.

5.  В поле **новое устройство проверки**введите имя устройства в поле **имя устройства**.

6.  В разделе **тип идентификатора**выберите **MAC-адрес** или **серийный номер**.

7.  В поле **уникальный идентификатор** введите MAC-адрес или серийный номер устройства.

8.  Щелкните **Исполнить**.

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>Создание тестовых устройств с помощью командлетов Windows PowerShell

Тестовые устройства можно создавать с помощью Windows PowerShell и командлета New-CsTestDevice. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

При создании тестовых устройств с помощью этого командлета необходимо выполнить два действия:

  - Укажите значение MACAddress или SerialNumber в качестве IdentifierType.

  - Включите область при указании удостоверения устройства. Для создания нового устройства в глобальной области используется синтаксис, аналогичный следующему:
    
        -Identity "global/WindowsPhone"
    
    Чтобы создать тестовое устройство на уровне сайта, используйте следующий синтаксис:
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>Создание тестового устройства с использованием MAC-адреса

  - Эта команда создает тестовое устройство в глобальной области и использует MAC-адрес в качестве IdentifierType:
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>Создание тестового устройства с использованием серийного номера

  - Эта команда создает новое тестовое устройство на уровне сайта (для сайта Redmond) и использует серийный номер в качестве IdentifierType:
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [New – CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

