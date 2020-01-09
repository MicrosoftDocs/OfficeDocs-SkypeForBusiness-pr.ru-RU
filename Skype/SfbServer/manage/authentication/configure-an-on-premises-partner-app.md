---
title: Настройка приложения для локального партнера в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Сводка: Настройка приложения для локального партнера в Skype для бизнеса Server.'
ms.openlocfilehash: 8f735de5c988dfea0da1adacdc4a77200d3a663d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992346"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>Настройка приложения для локального партнера в Skype для бизнеса Server
 
**Сводка:** Настройте локальное приложение партнера для Skype для бизнеса Server.
  
После назначения сертификата Оаустокениссуер вы должны настроить партнерские приложения Skype для бизнеса Server. (В соответствии с инструкциями, описанными в разделе Настройка сервера Microsoft Exchange Server 2013 и SharePoint для использования в качестве партнерских приложений, которые являются необязательными.) Чтобы настроить локальное приложение партнера, необходимо скопировать следующий сценарий Windows PowerShell и вставить его в Блокнот (или любой другой текстовый редактор).
  
```PowerShell
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
  
             New-CsPartnerApplication -Identity microsoft.sharepoint -MetadataUrl https://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 -ApplicationTrustLevel Full 
           }
        else
           {
             Set-CsPartnerApplication -Identity microsoft.sharepoint -ApplicationTrustLevel Full 
            }
   }

Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

После копирования кода сохраните скрипт с расширением .PS1 (например, C:\Scripts\ServerToServerAuth.ps1). Обратите внимание на то, что перед выполнением этого сценария необходимо заменить URL https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 - http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 адреса метаданных и URL-адреса метаданных, которые используются в сервере Exchange 2013 и SharePoint Server соответственно. Сведения о том, как определить URL-адрес метаданных соответствующего продукта, можно найти в документации по продукту Exchange 2013 и SharePoint.
  
Если посмотреть на последнюю строку скрипта, можно заметить, что командлет Set-CsOAuthConfiguration вызывается помощью следующего синтаксиса:
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Поскольку параметр Realm не использовался при вызове Set-CsOAuthConfiguration, область устанавливается автоматически как полное доменное имя организации (например, litwareinc.com). Если имя области отличается от имени организации, нужно указать имя области, например:
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

После внесения этих изменений вы можете выполнить сценарий и настроить оба сервера Exchange 2013 и SharePoint как партнерские приложения, запустив файл сценария в командной консоли Skype для бизнеса Server. Например:
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

Обратите внимание, что вы можете выполнить этот сценарий даже в том случае, если у вас не установлен сервер Exchange 2013 и SharePoint Server: Если вы, скажем, настроили SharePoint Server как партнерское приложение, не возникнут проблемы, даже если у вас не установлен SharePoint Server.
  
При выполнении этого скрипта может отображаться сообщение об ошибке, похожее на следующее:
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

Это сообщение об ошибке обычно означает одно из двух: 1) один из URL-адресов, указанных в скрипте, недействительный (то есть один из URL-адресов метаданных не является фактическим URL-адресом метаданных); 2) не удалось связаться с одним из URL-адресов метаданных. В этом случае убедитесь, что заданы правильные и доступные URL-адреса, и повторно выполните скрипт.
  
После создания приложения-партнера для Skype для бизнеса Server необходимо настроить Skype для Business Server как приложение-партнер для Exchange 2013. Вы можете настроить партнерские приложения для Exchange 2013, выполнив сценарий Конфигуре-ентерприсепартнераппликатион. ps1; все, что вам нужно, — это указать URL-адрес метаданных для сервера Skype для бизнеса Server и указать, что Skype для бизнеса Server является новым партнерским приложением. 
  
Чтобы настроить приложение Skype для бизнеса Server в качестве партнера для Exchange, откройте командную консоль Exchange и выполните команду, подобную следующей.
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


