---
title: 'Lync Server 2013: Просмотр номеров доступа для конференц-связи с телефонным подключением'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View dial-in conferencing access numbers
ms:assetid: 41a7dfb4-0c89-4650-b61b-0e1bf875c62b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688037(v=OCS.15)
ms:contentKeyID: 49733628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6794eee3015aca9a7f0d5281be5db10d87d833ab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506446"
---
# <a name="view-dial-in-conferencing-access-numbers-in-lync-server-2013"></a>Просмотр номеров доступа для конференц-связи с телефонным подключением в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

В панели управления Lync Server 2013 вы можете предоставить пользователям номера доступа для телефонного подключения, чтобы они могли присоединяться к собранию извне.

<div>

## <a name="to-view-dial-in-access-numbers"></a>Чтобы просмотреть номера для телефонного подключения

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Конференция**, а затем выберите **Номер для телефонного подключения**.

4.  На странице **Номер для телефонного подключения** щелкните номер доступа, который следует просмотреть.

5.  В разделе **Изменить** установите флажок **Подробнее…**.

</div>

<div>

## <a name="viewing-dial-in-conferencing-access-numbers-by-using-windows-powershell-cmdlets"></a>Просмотр номеров доступа для конференц-связи с телефонным подключением с помощью командлетов Windows PowerShell

Номера доступа к конференц-связи с телефонным подключением можно просмотреть с помощью Windows PowerShell и командлета Get-CsDialInConferencingAccessNumber. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-dial-in-conferencing-access-numbers"></a>Просмотр номеров доступа к конференц-связи с телефонным подключением

  - Чтобы просмотреть сведения обо всех номерах доступа к конференц-связи с телефонным подключением, введите в командной консоли Lync Server следующую команду и нажмите клавишу ВВОД:
    
        Get-CsDialInConferencingAccessNumber
    
    Это приведет к возврату приблизительно такой информации:
    
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

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Get – CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingAccessNumber) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

