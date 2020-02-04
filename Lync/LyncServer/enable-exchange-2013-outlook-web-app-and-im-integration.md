---
title: Включение Exchange 2013 Outlook Web App и интеграции с помощью мгновенных сообщений
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
ms.openlocfilehash: 0bd9fb94dd0f068547819aa884b608ac6ddf7e39
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-exchange-2013-outlook-web-app-and-im-integration"></a>Включение Exchange 2013 Outlook Web App и интеграции с помощью мгновенных сообщений

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-19_

Для обеспечения интеграции Exchange 2013 Outlook Web Access (OWA) и обмена мгновенными сообщениями с Lync Server 2013 необходимо добавить сервер клиентского доступа Exchange 2013 в топологию Lync Server 2013 как доверенный сервер приложений.

<div>

## <a name="to-create-a-trusted-application-pool"></a>Создание надежного пула приложений

1.  Запустите консоль управления Lync Server 2013.

2.  Выполнить следующий командлет:
    
        Get-CsSite
    
    Возвращает идентификатор сайта для сайта, на котором создается пул. Дополнительные сведения можно найти в [статьях Get-кссите](https://docs.microsoft.com/powershell/module/skype/Get-CsSite) в документации по среде управления Lync Server 2013.

3.  Выполнить следующий командлет:
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    Подробные сведения можно найти в разделе [New-кструстедаппликатионпул](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplicationPool) в документации по среде управления Lync Server 2013.
    
    Полное доменное имя Exchange Server должно быть задано в качестве имени субъекта сертификата Exchange OWA (SN) или альтернативного имени субъекта (SAN).
    
    В Exchange OWA убедитесь, что полное доменное имя пула также является надежным.
    
    <div>
    

    > [!IMPORTANT]  
    > Если ваш сервер CAS <EM>не</EM> размещен на том же сервере, на котором работает единая система обмена сообщениями Exchange 2013 (UM), пропустите оставшиеся действия, описанные в этой процедуре, и выполните действия "создать доверенное приложение для сервера Exchange 2013 SharePoint", описанное ниже в этой статье. Если ваш сервер CAS размещен на том же сервере, на котором работает единая система обмена сообщениями Exchange 2013 (UM), выполните действия, описанные в этой процедуре, и не выполняйте процедуру "создать доверенное приложение для сервера Exchange 2013 SharePoint" ниже в этой статье.

    
    </div>

4.  Запустите **Enable-кстопологи**.

5.  Откройте построитель топологии и скачайте существующую топологию.

6.  В левой области разверните дерево, пока не дойдете до **доверенных серверов приложений**.

7.  Разверните узел **серверы доверенных приложений** .

8.  Появится сервер Exchange 2013 CAS, указанный как доверенный сервер приложений.

</div>

<div>

## <a name="to-create-a-trusted-application-for-the-exchange-2013-cas-server"></a>Создание надежного приложения для сервера Exchange 2013 CAS

1.  Запустите консоль управления Lync Server 2013.

2.  Если ваш сервер CAS *не* размещен на том же сервере, на котором работает единая система обмена сообщениями Exchange 2013 (UM), запустите следующий командлет:
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    Подробные сведения можно найти в разделе [New-кструстедаппликатион](https://docs.microsoft.com/powershell/module/skype/New-CsTrustedApplication) в документации по среде управления Lync Server 2013.

3.  Запустите **Enable-кстопологи**.

4.  В области слева построитель топологии разверните дерево, пока вы не дойдете до **доверенных серверов приложений**.

5.  Разверните узел **серверы доверенных приложений** .

6.  Появится сервер Exchange 2013 CAS, указанный как доверенный сервер приложений.

</div>

</div>

<span> </span>

</div>

</div>

</div>

