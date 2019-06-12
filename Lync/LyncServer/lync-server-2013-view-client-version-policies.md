---
title: 'Lync Server 2013: Просмотр политик версии клиента'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View client version policies
ms:assetid: 6cd9a897-c694-4d6a-8259-2d3c01fce275
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898479(v=OCS.15)
ms:contentKeyID: 50873759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d90b3a40b03ce44201963b1276ee18a2fd9ac3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849166"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-client-version-policies-in-lync-server-2013"></a>Просмотр политик версии клиента в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Политики версий клиента используются для глобального применения набора правил для клиентских версий или для определенного сайта, пула или группы пользователей. Вы можете просматривать политики версий клиентов, которые настроены в среде Lync Server 2013 с помощью панели управления Lync Server 2013 или оболочки управления Lync Server 2013.

<div>

## <a name="to-view-client-version-policies-by-using-lync-server-control-panel"></a>Просмотр политик версии клиента с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Клиенты**и нажмите кнопку Переход на **политику версии клиента** .

4.  Если вы хотите просмотреть правила для политики версии клиента, на странице **политики Client Version** дважды щелкните политику, которую вы хотите просмотреть.

</div>

<div>

## <a name="viewing-client-version-policies-by-using-windows-powershell-cmdlets"></a>Просмотр политик версии клиента с помощью командлетов Windows PowerShell

Вы можете просматривать политики версии клиента с помощью командлета **Get-ксклиентверсионполици** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-view-client-version-policies"></a>Чтобы просмотреть политики версии клиента

  - Чтобы просмотреть сведения обо всех политиках версии клиента, введите следующую команду в командной консоли Lync Server Management Shell и нажмите клавишу ВВОД.
    
        Get-CsClientVersionPolicy
    
    Команда возвращает примерно следующую информацию:
    
        Identity    : Global
        Rules       : {RuleId=2336c611-a243-4c5d-994b-eea8a524d0e4;
                      Description=;Action=Block;ActionUrl=;MajorVersion=1;
                      MinorVersion=3;BuildNumber=;QfeNumber=;
                      UserAgent=RTC;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ, RuleId=342c9b90-4cef-483a-a73a-
                      4fe75c88711d;Description=;Action=Block;ActionUrl=;
                      MajorVersion=5;MinorVersion=;BuildNumber=;QfeNumber=;
                      UserAgent=WM;UserAgentFullName=;Enabled=True;
                      CompareOp=LEQ,RuleId=ea03af61-9db5-4bf9-af3f-042
                      ab8dd9994;Description=;Action=Block;ActionUrl=;
                      MajorVersion=3;MinorVersion=5;BuildNumber=6907;
                      QfeNumber=83;UserAgent=OC;UserAgentFullName=;
                      Enabled=True;CompareOp=LEQ, RuleId=831edb68-
                      e482-4431-a10e-add365ba8099;Description=;
                      Action=Block;ActionUrl=;MajorVersion=2;MinorVersion=0;
                      BuildNumber=5999;QfeNumber=;UserAgent=UCCP;
                      UserAgentFullName=;Enabled=True;CompareOp=LEQ...}
        Description :

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Get-ксклиентверсионполици](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

