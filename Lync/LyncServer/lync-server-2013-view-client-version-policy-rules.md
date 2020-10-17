---
title: 'Lync Server 2013: Просмотр правил политики версий клиентов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View client version policy rules
ms:assetid: f3a0215f-f72f-4e9b-a07b-25858dc4203a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923060(v=OCS.15)
ms:contentKeyID: 50675350
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d6a269ff6a90f95d76ddc9c230a3ce8a769977dc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506556"
---
# <a name="view-client-version-policy-rules-in-lync-server-2013"></a>Просмотр правил политики версий клиентов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Политика версий клиентов состоит из набора правил политики версий клиентов. Эти правила определяют действия, которые следует предпринять при попытке пользователей выполнить вход с использованием определенных клиентов и их версий. Вы можете просматривать правила политики версий клиентов из панели управления Lync Server 2013 или командной консоли Lync Server 2013.

<div>

## <a name="to-view-client-version-policy-rules-by-using-lync-server-control-panel"></a>Просмотр правил политики версий клиентов с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Клиенты**, а затем нажмите кнопку навигации для **политики версий клиентов** .

4.  На странице **Политика версий клиентов** дважды щелкните политику версий клиентов, которую нужно просмотреть.

5.  Правила отображаются на странице **изменение политики версий клиентов** . Чтобы просмотреть сведения о правиле, выберите правило, а затем щелкните **Показать подробности**.

</div>

<div>

## <a name="viewing-client-version-policy-rules-by-using-windows-powershell-cmdlets"></a>Просмотр правил политики версий клиентов с помощью командлетов Windows PowerShell

Вы можете просматривать правила политики версий клиентов с помощью командной консоли Lync Server и командлета **Get – CsClientVersionPolicyRule** . Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-client-version-policy-rules"></a>Просмотр правил политики версий клиентов

  - Чтобы просмотреть правила политики версий клиентов, введите в командную консоль Lync Server следующую команду и нажмите клавишу ВВОД:
    
        Get-CsClientVersionPolicyRule
    
    Будут возвращены сведения, аналогичные приведенным ниже, для каждого настроенного правила:
    
        Identity          : Global/2336c611-a243-4c5d-994b-eea8a524d0e4
        Priority          : 0
        RuleId            : 2336c611-a243-4c5d-994b-eea8a524d0e4
        Description       :
        Action            : Block
        ActionUrl         :
        MajorVersion      : 1
        MinorVersion      : 3
        BuildNumber       :
        QfeNumber         :
        UserAgent         : RTC
        UserAgentFullName :
        Enabled           : True
        CompareOp         : LEQ

</div>

Дополнительные сведения см. в разделе справки по командлету [Get – CsClientVersionPolicyRule](https://docs.microsoft.com/powershell/module/skype/Get-CsClientVersionPolicyRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

