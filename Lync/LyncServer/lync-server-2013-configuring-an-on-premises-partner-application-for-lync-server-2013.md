---
title: Настройка приложения для локального партнера для Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring an on-premises partner application for Lync Server 2013
ms:assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204975(v=OCS.15)
ms:contentKeyID: 48184412
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c396415dd6bd3bda99254f30b0223f1ff672a01f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841292"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-an-on-premises-partner-application-for-microsoft-lync-server-2013"></a>Настройка приложения для локального партнера для Microsoft Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-04_

После назначения сертификата Оаустокениссуер необходимо настроить партнерские приложения Microsoft Lync Server 2013. (В соответствии с инструкциями, изложенными в разделе Настройка сервера Microsoft Exchange Server 2013 и Microsoft SharePoint для использования в качестве партнерских приложений.) Чтобы настроить локальное приложение партнера, необходимо скопировать следующий сценарий Windows PowerShell и вставить его в Блокнот (или любой другой текстовый редактор).

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

После копирования кода сохраните его с помощью. Расширение файла PS1 (например, C:\\Scripts\\сервертосервераус. ps1). Обратите внимание на то, что перед выполнением этого сценария необходимо заменить URL https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 - http://atl-sharepoint-001.litwareinc.com/jsonmetadata.ashx адреса метаданных и URL-адреса метаданных, которые используются в сервере Exchange 2013 и SharePoint Server соответственно. Сведения о том, как определить URL-адрес метаданных соответствующего продукта, можно найти в документации по продукту Exchange 2013 и SharePoint.

Если посмотреть на последнюю строку скрипта, можно заметить, что командлет Set-CsOAuthConfiguration вызывается помощью следующего синтаксиса:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Поскольку параметр Realm не использовался при вызове Set-CsOAuthConfiguration, область устанавливается автоматически как полное доменное имя организации (например, litwareinc.com). Если имя области отличается от имени организации, нужно указать имя области, например:

    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"

После внесения этих изменений вы можете выполнить сценарий и настроить оба сервера Exchange 2013 и SharePoint как партнерские приложения, запустив файл сценария в командной консоли Lync Server 2013. Например:

    C:\Scripts\ServerToServerAuth.ps1

Обратите внимание, что вы можете выполнить этот сценарий даже в том случае, если у вас не установлен сервер Exchange 2013 и SharePoint Server: Если вы, скажем, настроили SharePoint Server как партнерское приложение, не возникнут проблемы, даже если у вас не установлен SharePoint Server.

При выполнении этого скрипта может отображаться сообщение об ошибке, похожее на следующее:

    New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."

Это сообщение об ошибке обычно означает одно из двух: 1) один из URL-адресов, указанных в скрипте, недействительный (то есть один из URL-адресов метаданных не является фактическим URL-адресом метаданных); 2) не удалось связаться с одним из URL-адресов метаданных. В этом случае убедитесь, что заданы правильные и доступные URL-адреса, и повторно выполните скрипт.

После создания приложения-партнера для Lync Server 2013 необходимо настроить Lync Server, чтобы он был партнерским приложением для Exchange 2013. Вы можете настроить партнерские приложения для Exchange 2013, выполнив сценарий Конфигуре-ентерприсепартнераппликатион. ps1; все, что вам нужно, — это указать URL-адрес метаданных для сервера Lync Server и указать, что Lync Server — это новое приложение-партнер.

Чтобы настроить Lync Server в качестве партнерского приложения Exchange, откройте командную консоль Exchange и выполните команду, подобную следующей.

    "c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://lync.contoso.com/metadata/json/1" -ApplicationType "Lync"

</div>

<span> </span>

</div>

</div>

</div>

