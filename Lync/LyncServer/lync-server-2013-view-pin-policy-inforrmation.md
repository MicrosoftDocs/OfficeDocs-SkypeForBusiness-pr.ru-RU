---
title: 'Lync Server 2013: Просмотр политики ПИН-кода сведений о'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PIN policy inforrmation
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49733575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 855fa6afe5cd0d302fbd999675d18e2bf5535074
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a>Просмотр политики ПИН-кода сведений о в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Вы можете использовать вкладку **политика ПИН-кода** для просмотра персонального идентификационного номера (ПИН-кода) пользователей, подключающихся к Lync 2013 с IP-телефонами. Чтобы использовать проверку подлинности на основе ПИН-кодов, необходимо установить флажок **Enable PIN Authentication (Включить проверку подлинности на основе ПИН-кодов)** в параметрах веб-службы. Дополнительные сведения: [изменение параметров конфигурации существующей веб-службы в Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md).

Чтобы изменить политику ПИН-кода на уровне пользователя или сайта, выполните следующие действия.

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a>Просмотр сведений о политике ПИН-кодов в панели управления Lync Server

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите **Безопасность** и нажмите **Политика ПИН-кода**.

4.  На странице **Политика ПИН-кода** щелкните политику, выберите **Изменить** и нажмите **Показать подробности**.

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Просмотр политик ПИН-кода с помощью командлетов Windows PowerShell

Вы также можете просматривать политики ПИН-кодов с помощью Windows PowerShell и командлета Get-CsPinPolicy. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

<div>

## <a name="to-view-pin-policies"></a>Просмотр политик ПИН-кода

  - Чтобы просмотреть сведения обо всех политиках ПИН-кодов, введите следующую команду в командной консоли Lync Server и нажмите клавишу ВВОД:
    
        Get-CsPinPolicy
    
    Это приведет к возврату приблизительно такой информации:
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Get – CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) .

</div>

<div>

## <a name="see-also"></a>См. также


[Изменение параметров конфигурации существующей веб-службы в Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[Создание новой политики ПИН-кодов в Lync Server 2013](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

