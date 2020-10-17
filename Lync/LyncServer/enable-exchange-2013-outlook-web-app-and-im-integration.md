---
title: Включение Exchange 2013 Outlook Web App и интеграция обмена мгновенными сообщениями
description: Включите Exchange 2013 Outlook Web App и интеграция с IM.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Exchange 2013 Outlook Web App and IM integration
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48184027
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a7fd6e8600f255d6ac4dde52487776cdb5fe1a51
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551125"
---
# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Включение Exchange 2013 Outlook Web App и интеграция обмена мгновенными сообщениями

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-19_

Чтобы включить интеграцию с Exchange 2013 Outlook Web Access (OWA) и службу обмена мгновенными сообщениями с Lync Server 2013, необходимо добавить сервер сервера клиентского доступа Exchange 2013 в топологию Lync Server 2013 в качестве доверенного сервера приложений.

<div>

## <a name="to-create-a-trusted-application-pool"></a>Чтобы создать пул доверенных приложений

1.  Запустите командную консоль Lync Server 2013.

2.  Выполните следующий командлет:
    
        Get-CsSite
    
    Это вернет siteID для siteName, имени сайта, в котором следует создать пул. Дополнительные сведения см. в статье [Get – CsSite](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) в документации по консоли управления Lync Server 2013.

3.  Запустите следующий командлет:
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    Дополнительные сведения см. в статье [New – кструстедаппликатионпул](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) в документации по среде управления Lync Server 2013.
    
    Полное доменное имя Exchange Server должно быть настроено в сертификате Exchange OWA как имя субъекта или альтернативное имя субъекта (SAN).
    
    Убедитесь, что в Exchange OWA полное доменное имя пула также является доверенным.
    
    <div>
    

    > [!IMPORTANT]  
    > Если сервер CAS <EM>не</EM> размещен на том же сервере, на котором работает единая система обмена сообщениями Exchange 2013, пропустите оставшиеся действия, описанные в этой процедуре, и выполните процедуру "создание доверенного приложения для сервера клиентского доступа Exchange 2013" Далее в этой статье. Если сервер CAS размещен на том же сервере, на котором работает единая система обмена сообщениями Exchange 2013, выполните действия, описанные в этой процедуре, и не выполняйте процедуру "создание доверенного приложения для сервера клиентского доступа Exchange 2013" Далее в этой статье.

    
    </div>

4.  Запустите **Enable-CsTopology**.

5.  Откройте построитель топологий и загрузите текущую топологию.

6.  На левой панели разверните дерево, пока не достигните узла **Серверы доверенных приложений**.

7.  Разверните узел **Серверы доверенных приложений**.

8.  Теперь сервер клиентского доступа Exchange 2013, указанный в качестве доверенного сервера приложений, должен отображаться как доверенный.

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>Создание доверенного приложения для сервера клиентского доступа Exchange 2013

1.  Запустите командную консоль Lync Server 2013.

2.  Если сервер CAS *не* размещен на том же сервере, на котором работает единая система обмена сообщениями Exchange 2013, выполните следующий командлет:
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    Для получения дополнительных сведений обратитесь к разделу [New – кструстедаппликатион](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) в документации по консоли управления Lync Server 2013.

3.  Запустите **Enable-CsTopology**.

4.  В построителе решений на левой панели разверните дерево, пока не достигните узла **Серверы доверенных приложений**.

5.  Разверните узел **Серверы доверенных приложений**.

6.  Теперь сервер клиентского доступа Exchange 2013, указанный в качестве доверенного сервера приложений, должен отображаться как доверенный.

</div>

</div>

<span> </span>

</div>

</div>

</div>

