---
title: 'Lync Server 2013: Просмотр номеров доступа для конференц-связи с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View dial-in conferencing access numbers
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49733628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b9d9e6ca8d4f388edf6f04f4012726f6abee9e9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Просмотр номеров доступа для конференц-связи с телефонным подключением в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

В панели управления Lync Server 2013 вы можете предоставить пользователям номера доступа для телефонного подключения, чтобы они могли присоединиться к собранию извне.

<div>

## <a name="to-view-dial-in-access-numbers"></a>Просмотр номеров доступа для телефонного подключения

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Конференция**, а затем выберите **Номер для телефонного подключения**.

4.  На странице **Номер для телефонного подключения** щелкните номер доступа, который следует просмотреть.

5.  В окне " **Правка**" нажмите кнопку **Показать подробности...** флажок.

</div>

<div>

## <a name="viewing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Просмотр номеров доступа для конференц-связи с телефонным подключением с помощью командлетов Windows PowerShell

Номера доступа для конференц-связи с телефонным подключением можно просмотреть с помощью Windows PowerShell и командлета Get-КсдиалинконференЦингакцесснумбер. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-view-dial-in-conferencing-access-numbers"></a>Просмотр номеров доступа для конференц-связи с телефонным подключением

  - Чтобы просмотреть сведения обо всех номерах доступа к конференц-связи с телефонным подключением, введите следующую команду в командной консоли Lync Server Management Shell и нажмите клавишу ВВОД.
    
        Get-CsDialInConferencingAccessNumber
    
    Команда возвращает примерно следующую информацию:
    
        Identity           : CN={20ca8dc8-5ff8-41f4-b5bb-22ba9972ae2e},
                             CN=Application Contacts,CN=RTCService=Services,
                             CN=Configuration,DC=litwareinc,DC=com
        PrimaryUri         : sip:testnumber@litwareinc.com
        DisplayName        : Test
        DisplayNumber      : 1-425-555-1019
        LineUri            : tel:+14255551019
        PrimaryLanguage    : en-US
        SecondaryLanguages : {}
        Pool               : atl-cs-001.litwareinc.com
        HostingProvider    :
        Regions            : {US}

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Get-ксдиалинконференЦингакцесснумбер](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

