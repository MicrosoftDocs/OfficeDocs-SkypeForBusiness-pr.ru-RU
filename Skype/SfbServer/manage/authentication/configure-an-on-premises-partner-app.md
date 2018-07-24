---
title: Настройка локального приложения партнера для Скайп для Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 696f2b26-e5d0-42b5-9785-a26c2ce25bb7
description: 'Сводка: Настройка локального приложения партнера для Скайп для Business Server.'
ms.openlocfilehash: 1377957797108f3cbc8e290b7750e9fba489cbf8
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21009727"
---
# <a name="configure-an-on-premises-partner-application-for-skype-for-business-server"></a><span data-ttu-id="74436-103">Настройка локального приложения партнера для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="74436-103">Configure an on-premises partner application for Skype for Business Server</span></span>
 
<span data-ttu-id="74436-104">**Сводка:** Настройка локального приложения партнера для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="74436-104">**Summary:** Configure an on-premises partner application for Skype for Business Server.</span></span>
  
<span data-ttu-id="74436-105">После назначения сертификата OAuthTokenIssuer затем необходимо настроить вашей Скайп для приложений партнеров Business Server.</span><span class="sxs-lookup"><span data-stu-id="74436-105">After you have assigned the OAuthTokenIssuer certificate you must then configure your Skype for Business Server partner applications.</span></span> <span data-ttu-id="74436-106">(Процедура будет описан в настраивает Microsoft Exchange Server 2013 и SharePoint в качестве партнерских приложений, которые является необязательным.) Настройка локального приложения партнера, необходимо запустить путем копирования приведенный ниже сценарий Windows PowerShell и вставки кода в "Блокнот" (или любом другом текстовом редакторе):</span><span class="sxs-lookup"><span data-stu-id="74436-106">(The procedure about to be discussed configures both Microsoft Exchange Server 2013 and SharePoint to act as partner applications, which is optional.) To configure an on-premises partner application, you must start by copying the following Windows PowerShell script and pasting the code into Notepad (or any other text editor):</span></span>
  
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

<span data-ttu-id="74436-107">После копирования кода сохраните скрипт с расширением .PS1 (например, C:\Scripts\ServerToServerAuth.ps1).</span><span class="sxs-lookup"><span data-stu-id="74436-107">After copying the code, save the script using a .PS1 file extension (for example, C:\Scripts\ServerToServerAuth.ps1).</span></span> <span data-ttu-id="74436-108">Обратите внимание, что перед запуском этого сценария необходимо заменить URL-адреса метаданных https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 и http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 с метаданных URL-адресами, используемыми сервером Exchange 2013 и SharePoint, соответственно.</span><span class="sxs-lookup"><span data-stu-id="74436-108">Note that, before you run this script, you must replace the metadata URLs https://atl-exchange-001.litwareinc.com/autodiscover/metadata/json/1 and http://atl-sharepoint-001.litwareinc.com/_layouts/15/metadata/json/1 with the metadata URLs used by your Exchange 2013 and SharePoint servers, respectively.</span></span> <span data-ttu-id="74436-109">Обратитесь к документации для Exchange 2013 и SharePoint для получения сведений по определению URL-адрес метаданных соответствующих продуктов.</span><span class="sxs-lookup"><span data-stu-id="74436-109">See the product documentation for Exchange 2013 and SharePoint for information on how you can identify the respective product's metadata URL.</span></span>
  
<span data-ttu-id="74436-110">Если посмотреть на последнюю строку скрипта, можно заметить, что командлет Set-CsOAuthConfiguration вызывается помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="74436-110">If you look at the last line of the script you will notice that the Set-CsOAuthConfiguration cmdlet is called using this syntax:</span></span>
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="74436-p103">Поскольку параметр Realm не использовался при вызове Set-CsOAuthConfiguration, область устанавливается автоматически как полное доменное имя организации (например, litwareinc.com). Если имя области отличается от имени организации, нужно указать имя области, например:</span><span class="sxs-lookup"><span data-stu-id="74436-p103">Because the Realm parameter was not used when calling Set-CsOAuthConfiguration the realm will automatically be set to the fully qualified domain name (FQDN) of your organization (for example, litwareinc.com). If your realm name is different from your organization name then you should include the realm name, like this:</span></span>
  
```
Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000 -Realm "contoso.com"
```

<span data-ttu-id="74436-113">После выполнения этих изменений можно выполнить сценарий и настройка Exchange 2013 и SharePoint в качестве партнерских приложений, запустив файл скрипта из Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="74436-113">After making these changes you can then execute the script, and configure both Exchange 2013 and SharePoint as partner applications, by running the script file from within the Skype for Business Server Management Shell.</span></span> <span data-ttu-id="74436-114">Например:</span><span class="sxs-lookup"><span data-stu-id="74436-114">For example:</span></span>
  
```
C:\Scripts\ServerToServerAuth.ps1
```

<span data-ttu-id="74436-115">Обратите внимание на то, что даже в том случае, если у вас оба Exchange 2013 и SharePoint Server установлено, можно запустить этот скрипт:, не будет привести к возникновению проблем, скажем, несмотря на то, что у вас нет Настройка сервера SharePoint в качестве партнерского приложения установки SharePoint Server.</span><span class="sxs-lookup"><span data-stu-id="74436-115">Note that you can run this script even if you do not have both Exchange 2013 and SharePoint Server installed:, no problems will occur if you, say, configure SharePoint Server as a partner application even though you do not have SharePoint Server installed.</span></span>
  
<span data-ttu-id="74436-116">При выполнении этого скрипта может отображаться сообщение об ошибке, похожее на следующее:</span><span class="sxs-lookup"><span data-stu-id="74436-116">When you run this script you might receive an error message similar to the following:</span></span>
  
```
New-CsPartnerApplication : Cannot bind parameter 'MetadataUrl' to the target. Exception setting "MetadataUrl": "The metadata document could not be downloaded from the URL in the MetadataUrl parameter or downloaded data is not a valid metadata document."
```

<span data-ttu-id="74436-p105">Это сообщение об ошибке обычно означает одно из двух: 1) один из URL-адресов, указанных в скрипте, недействительный (то есть один из URL-адресов метаданных не является фактическим URL-адресом метаданных); 2) не удалось связаться с одним из URL-адресов метаданных. В этом случае убедитесь, что заданы правильные и доступные URL-адреса, и повторно выполните скрипт.</span><span class="sxs-lookup"><span data-stu-id="74436-p105">This error message typically means one of two things: 1) that one of the URLs specified in the script is not valid (that is, one of your metadata URLs is not an actual metadata URL); or, 2) one of the metadata URLs could not be contacted. If this happens, verify that the URLs are correct and are accessible, and the re-run the script.</span></span>
  
<span data-ttu-id="74436-119">После создания партнерского приложения для Скайп Business Server затем необходимо настроить Скайп для Business Server в качестве партнерского приложения для Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="74436-119">After creating the partner application for Skype for Business Server you must then configure Skype for Business Server to be a partner application for Exchange 2013.</span></span> <span data-ttu-id="74436-120">Можно настроить приложения партнеров для Exchange 2013, выполнив сценарий Configure-EnterprisePartnerApplication.ps1; все, что вам нужно сделать — укажите URL-адрес метаданных для Скайп для Business Server и указать, что Скайп для Business Server нового партнерского приложения.</span><span class="sxs-lookup"><span data-stu-id="74436-120">You can configure partner applications for Exchange 2013 by running the script Configure-EnterprisePartnerApplication.ps1; all you need to do is specify the metadata URL for Skype for Business Server and indicate that Skype for Business Server is the new partner application.</span></span> 
  
<span data-ttu-id="74436-121">Чтобы настроить Скайп для Business Server как партнерское приложение для Exchange, откройте командную консоль Exchange и выполните команду следующего вида</span><span class="sxs-lookup"><span data-stu-id="74436-121">To configure Skype for Business Server as a partner application for Exchange, open the Exchange Management Shell and run a command similar to this</span></span>
  
```
"c:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1" -AuthMetadataUrl "https://SkypePro.contoso.com/metadata/json/1" -ApplicationType "Lync"
```


