---
title: Настройка локального партнерского приложения для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: Сводка. Настройка локального партнерского приложения для Skype для бизнеса Server.
ms.openlocfilehash: d0907d73d6a23c0a5b9a1f1725503b72c5bce993
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012623"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a>Настройка локального партнерского приложения для Skype для бизнеса Server
 
**Сводка:** Настройка локального партнерского приложения для Skype для бизнеса Server.
  
После присвоения сертификата OAuthTokenIssuer необходимо настроить Skype для бизнеса Server партнеров. (Процедура, которая будет обсуждаться, настраивает Microsoft Exchange Server 2013 и SharePoint в качестве партнерских приложений, что необязательно.) Чтобы настроить локальное партнерского приложения, необходимо скопировать следующий сценарий Windows PowerShell и вклеить код в Блокнот (или любой другой текстовый редактор):
  
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

После копирования кода сохраните скрипт с расширением .PS1 (например, C:\Scripts\ServerToServerAuth.ps1). Обратите внимание, что перед запуском этого скрипта необходимо заменить URL-адреса метаданных и URL-адреса метаданных, используемые вашими серверами Exchange `https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1` `http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1` 2013 и SharePoint соответственно. Сведения о том, как определить URL-адрес метаданных соответствующего продукта, Exchange 2013 и SharePoint 2013 г. см. в документации по продуктам.
  
Если посмотреть на последнюю строку скрипта, можно заметить, что командлет Set-CsOAuthConfiguration вызывается помощью следующего синтаксиса:
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Поскольку параметр Realm не использовался при вызове Set-CsOAuthConfiguration, область устанавливается автоматически как полное доменное имя организации (например, litwareinc.com). Если имя области отличается от имени организации, нужно указать имя области, например:
  
```PowerShell
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

После внесения этих изменений можно выполнить сценарий и настроить Exchange 2013 и SharePoint как партнерские приложения, запуская файл скрипта из Skype для бизнеса Server оболочки управления. Например.
  
```PowerShell
C:\Scripts\ServerToServerAuth.ps1
```

Обратите внимание, что этот сценарий можно запустить, даже если у вас нет установки Exchange 2013 и SharePoint Server: никаких проблем не будет, если, скажем, настроить SharePoint Server в качестве партнерского приложения, даже если у вас нет SharePoint Server.
  
При выполнении этого скрипта может отображаться сообщение об ошибке, похожее на следующее:
  
```PowerShell
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

Это сообщение об ошибке обычно означает одно из двух: 1) один из URL-адресов, указанных в скрипте, недействительный (то есть один из URL-адресов метаданных не является фактическим URL-адресом метаданных); 2) не удалось связаться с одним из URL-адресов метаданных. В этом случае убедитесь, что заданы правильные и доступные URL-адреса, и повторно выполните скрипт.
  
После создания партнерского приложения для Skype для бизнеса Server необходимо настроить Skype для бизнеса Server, чтобы быть партнером приложения для Exchange 2013. Вы можете настроить партнерские приложения для Exchange 2013 г., запуская Configure-EnterprisePartnerApplication.ps1; Все, что вам нужно сделать, это указать URL-адрес метаданных для Skype для бизнеса Server и указать, что Skype для бизнеса Server является новым приложением-партнером. 
  
Чтобы настроить Skype для бизнеса Server в качестве партнерского приложения для Exchange, откройте Exchange командную оболочку и запустите команду, аналогичную этой
  
```PowerShell
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


