---
title: Настройка локального приложения партнера для Skype для бизнеса Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Сводка: Настройка локального приложения партнера для Скайп для Business Server 2015.'
ms.openlocfilehash: 2f13196288fb7b609e5e3d39996c12eab04493dc
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569451"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server-2015"></a>Настройка локального приложения партнера для Skype для бизнеса Server 2015
 
**Сводка:** Настройка локального приложения партнера для Скайп для Business Server 2015.
  
После назначения сертификата OAuthTokenIssuer затем необходимо настроить вашей Скайп для приложений партнеров Business Server 2015. (Процедура будет описан в настраивает Microsoft Exchange Server 2013 и SharePoint в качестве партнерских приложений, которые является необязательным.) Настройка локального приложения партнера, необходимо запустить путем копирования приведенный ниже сценарий Windows PowerShell и вставки кода в "Блокнот" (или любом другом текстовом редакторе):
  
```
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

После копирования кода сохраните скрипт с расширением .PS1 (например, C:\Scripts\ServerToServerAuth.ps1). Обратите внимание, что перед запуском этого сценария необходимо заменить URL-адреса метаданных https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 и http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 с метаданных URL-адресами, используемыми сервером Exchange 2013 и SharePoint, соответственно. Обратитесь к документации для Exchange 2013 и SharePoint для получения сведений по определению URL-адрес метаданных соответствующих продуктов.
  
Если посмотреть на последнюю строку скрипта, можно заметить, что командлет Set-CsOAuthConfiguration вызывается помощью следующего синтаксиса:
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

Поскольку параметр Realm не использовался при вызове Set-CsOAuthConfiguration, область устанавливается автоматически как полное доменное имя организации (например, litwareinc.com). Если имя области отличается от имени организации, нужно указать имя области, например:
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

После выполнения этих изменений можно выполнить сценарий и настройка Exchange 2013 и SharePoint в качестве партнерских приложений, запустив файл скрипта из Скайп для консоли Business Server. Например:
  
```
C:\Scripts\ServerToServerAuth.ps1
```

Обратите внимание на то, что даже в том случае, если у вас оба Exchange 2013 и SharePoint Server установлено, можно запустить этот скрипт:, не будет привести к возникновению проблем, скажем, несмотря на то, что у вас нет Настройка сервера SharePoint в качестве партнерского приложения установки SharePoint Server.
  
При выполнении этого скрипта может отображаться сообщение об ошибке, похожее на следующее:
  
```
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

Это сообщение об ошибке обычно означает одно из двух: 1) один из URL-адресов, указанных в скрипте, недействительный (то есть один из URL-адресов метаданных не является фактическим URL-адресом метаданных); 2) не удалось связаться с одним из URL-адресов метаданных. В этом случае убедитесь, что заданы правильные и доступные URL-адреса, и повторно выполните скрипт.
  
После создания партнерского приложения для Скайп Business Server 2015 затем необходимо настроить Скайп для Business Server в качестве партнерского приложения для Exchange 2013. Можно настроить приложения партнеров для Exchange 2013, выполнив сценарий Configure-EnterprisePartnerApplication.ps1; все, что вам нужно сделать — укажите URL-адрес метаданных для Скайп для Business Server и указать, что Скайп для Business Server нового партнерского приложения. 
  
Чтобы настроить Скайп для Business Server как партнерское приложение для Exchange, откройте командную консоль Exchange и выполните команду следующего вида
  
```
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


