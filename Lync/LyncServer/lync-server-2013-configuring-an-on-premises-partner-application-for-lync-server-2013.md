---
title: Настройка локального партнерского приложения для Lync Server 2013
description: Настройка локального партнерского приложения для Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0401634c6cb7afc451652ffbaf55cdc01a7ca89
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570925"
---
# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a>Настройка локального приложения партнера для Microsoft Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-04_

После назначения сертификата OAuthTokenIssuer необходимо настроить партнерские приложения Microsoft Lync Server 2013. (В описанной процедуре описывается настройка Microsoft Exchange Server 2013 и Microsoft SharePoint для работы в качестве партнерских приложений.) Чтобы настроить локальное партнерское приложение, необходимо сначала скопировать приведенный ниже сценарий Windows PowerShell и вставить код в Блокнот (или любой другой текстовый редактор):

    if ((Get-CsPartnerApplication -ErrorAction SilentlyContinue) -ne $Null)
       {
           Remove-CsPartnerApplication app
       }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
    New-CsPartnerApplication -Identity microsoft.exchange -MetadataUrl https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full 
               }
         }
    
    $shp = Get-CsPartnerApplication microsoft.sharepoint -ErrorAction SilentlyContinue
            
    if ($shp -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
        }
    else
        {
           if ($shp.ApplicationIdentifier -ne "00000003-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.sharepoint
      
                 New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx -ApplicationTrustLevel Full 
               }
            else
               {
                 Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
                }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

После копирования кода сохраните скрипт с помощью. Расширение файла PS1 (например, C: \\ scripts \\ServerToServerAuth.ps1). Обратите внимание, что перед выполнением этого сценария необходимо заменить URL-адреса метаданных https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 и http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx URL-адреса метаданных, используемые серверами Exchange 2013 и SharePoint соответственно. Сведения о том, как определить URL-адрес метаданных соответствующего продукта, можно найти в документации по продукту Exchange 2013 и SharePoint.

Если посмотреть на последнюю строку скрипта, можно заметить, что командлет Set-CsOAuthConfiguration вызывается помощью следующего синтаксиса:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Поскольку параметр Realm не использовался при вызове Set-CsOAuthConfiguration, область устанавливается автоматически как полное доменное имя организации (например, litwareinc.com). Если имя области отличается от имени организации, нужно указать имя области, например:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

После внесения этих изменений можно выполнить скрипт и настроить для них как Exchange 2013, так и SharePoint как партнерские приложения, запустив файл скрипта из командной консоли Lync Server 2013. Например:

    C:\Scripts\ServerToServerAuth.ps1

Обратите внимание, что вы можете запустить этот сценарий, даже если у вас нет серверов Exchange 2013 и SharePoint Server:, если вы, скажем, настроили SharePoint Server как партнерское приложение, несмотря на то что у вас не установлен SharePoint Server.

При выполнении этого скрипта может отображаться сообщение об ошибке, похожее на следующее:

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

Это сообщение об ошибке обычно означает одно из двух: 1) один из URL-адресов, указанных в скрипте, недействительный (то есть один из URL-адресов метаданных не является фактическим URL-адресом метаданных); 2) не удалось связаться с одним из URL-адресов метаданных. В этом случае убедитесь, что заданы правильные и доступные URL-адреса, и повторно выполните скрипт.

После создания партнерского приложения для Lync Server 2013 необходимо настроить Lync Server в качестве партнерского приложения для Exchange 2013. Вы можете настроить партнерские приложения для Exchange 2013, выполнив Configure-EnterprisePartnerApplication.ps1 сценариев; все, что вам нужно сделать, — указать URL-адрес метаданных для Lync Server и указать, что Lync Server является новым партнерским приложением.

Чтобы настроить Lync Server в качестве партнерского приложения для Exchange, откройте командную консоль Exchange и выполните команду, подобную следующей.

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

