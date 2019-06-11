---
title: 'Lync Server 2013: создание устройства для проверки функциональных возможностей обновления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad2fa5283561e1096cfe7e3053db59c3cd2e40e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a>Создание устройства для проверки функциональных возможностей обновления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Вы можете добавить устройство проверки на страницу **Устройство проверки** и затем использовать его для проверки функциональных возможностей новых обновлений перед их развертыванием на производственных устройствах. Вы можете протестировать устройство глобально (во всей среде Lync Server) или на одном сайте. Устройство проверки указывается по MAC-адресу или серийному номеру. При добавлении устройства оно отображается в списке на странице " **тестирование устройства** " на панели управления Lync Server.

<div>

## <a name="to-add-a-test-device"></a>Добавление тестового устройства

1.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  На панели навигации слева выберите пункт **Клиенты**, а затем — пункт **Проверка устройства**.

3.  Нажмите кнопку **создать**, а затем щелкните либо **глобальное тестовое** устройство, либо тестовое **устройство сайта**.

4.  Выполните одно из следующих действий:
    
      - Если вы щелкните **глобальное тестовое устройство**, перейдите к следующему шагу.
    
      - Если выбрано **тестовое устройство сайта**, выберите сайт из списка доступных сайтов и нажмите кнопку **ОК**.

5.  В окне **нового тестового устройства**введите имя устройства в поле **имя устройства**.

6.  В поле **тип идентификатора**выберите один из **компьютеров: Mac-адрес** или **серийный номер**.

7.  В поле **уникальный идентификатор** введите MAC-адрес или серийный номер устройства.

8.  Нажмите **Исполнить**.

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a>Создание тестовых устройств с помощью командлетов Windows PowerShell

Тестовые устройства можно создавать с помощью Windows PowerShell и командлета New-Кстестдевице. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

При создании тестовых устройств с помощью этого командлета необходимо выполнить два действия:

  - Укажите значение MACAddress или SerialNumber в качестве Идентифиертипе.

  - Включите область при указании удостоверения устройства. Для создания нового устройства в глобальной области используйте синтаксис, подобный приведенному ниже.
    
        -Identity "global/WindowsPhone"
    
    Для создания тестового устройства в области сайта используйте синтаксис, подобный приведенному ниже.
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a>Создание тестового устройства с помощью MAC-адреса

  - Эта команда создает тестовое устройство в глобальной области и использует MAC-адрес в качестве Идентифиертипе:
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a>Создание тестового устройства с использованием серийного номера

  - Эта команда создает новое тестовое устройство в области сайта (для сайта Redmond) и использует серийный номер в качестве Идентифиертипе:
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

Дополнительные сведения можно найти в разделе справки по командлету [New-кстестдевице](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

