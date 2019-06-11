---
title: 'Lync Server 2013: Настройка сервера Lync Server в нескольких локальных средах'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44a47dc3bf3c832819fe431cb0177bfc1a03f330
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a>Настройка Microsoft Lync Server 2013 в нескольких локальных средах

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2017-02-21_

В многолокальных конфигурациях некоторые пользователи находятся в локальной установке Microsoft Lync Server 2013, а другие пользователи находятся в версии Office 365 на Lync Server. Чтобы настроить проверку подлинности "сервер-сервер" в нескольких локальных средах, необходимо сначала настроить локальную установку Lync Server 2013, чтобы доверять серверу авторизации Office 365. Чтобы выполнить этот процесс, запустите следующий сценарий оболочки управления Lync Server.

    $TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
    
    $sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue
            
       if ($sts -eq $null)
          {
             New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
          }
       else
          {
             if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
                {
                   Remove-CsOAuthServer microsoft.sts
                   New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
                }
            }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
                 New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
              }
           else
              {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
              }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Помните о том, что имя области для клиента обычно отличается от имени организации; на деле имя области почти всегда совпадает с идентификатором клиента. Поэтому первая строка скрипта используется для получения значения свойства TenantId для заданного клиента (в данном случае это fabrikam.com) и последующего назначения этого имени переменной $TenantId:

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

После завершения работы сценария необходимо настроить отношение доверия между Lync Server 2013 и сервером авторизации, а также вторым отношением доверия между Exchange 2013 и сервером авторизации. Это возможно только с помощью командлетов Microsoft Online Services.

<div>


> [!NOTE]  
> Если вы не установили командлеты Microsoft Online Services, перед продолжением вам потребуется выполнить два действия. Во-первых, скачайте и установите 64-разрядную версию помощника по входу в Microsoft Online Services. После завершения установки Скачайте и установите 64-разрядную версию модуля Microsoft Online Services для Windows PowerShell. Подробные сведения об установке и использовании модуля Microsoft Online Services можно найти на веб-сайте Office 365. В этих инструкциях также рассказывается о том, как настроить единый вход, Федерацию и синхронизацию между Office 365 и Active Directory.<BR>Если вы не выполнили установку этих командлетов, то произойдет сбой вашего сценария, так как командлет Get-CsTenant будет недоступен.



</div>

После того как вы настроили Office 365, и после создания участников служб Office 365 для Lync Server 2013 и Exchange 2013, вам потребуется зарегистрировать ваши учетные данные для этих субъектов-служб. Для этого необходимо сначала получить X.509 Base64 в виде файла CER. Этот сертификат будет затем применен к участникам службы Office 365.

После получения сертификата X. 509 запустите модуль Microsoft Online Services (нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **веб-службы Майкрософт**, а затем — **модуль Microsoft Online Services для Windows. PowerShell**). После открытия модуля "службы" введите следующую команду для импорта модуля Microsoft Online Windows PowerShell, содержащего командлеты, которые можно использовать для управления субъектами-службами.

    Import-Module MSOnlineExtended

После импорта модуля введите указанную ниже команду и нажмите клавишу ВВОД, чтобы подключиться к Office 365:

    Connect-MsolService

При нажатии клавиши Enter отображается диалоговое окно учетных данных. В диалоговом окне введите имя пользователя и пароль Office 365 и нажмите кнопку ОК.

После подключения к Office 365 вы можете выполнить следующую команду, чтобы получить сведения об участниках служб.

    Get-MsolServicePrincipal

Команда возвращает для всех субъектов-служб сведения, похожие на следующие:

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

На следующем шаге выполняется импорт, кодирование и назначение сертификата X.509. Для импорта и кодирования сертификата используйте указанные ниже команды Windows PowerShell, чтобы указать полный путь к файлу. CER при вызове метода Import:

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

После того как сертификат будет импортирован и закодирован, вы можете назначить сертификат участникам службы Office 365. Для этого сначала используйте Get-МсолсервицепринЦипал для получения значения свойства АпппринЦипалид как для сервера Lync, так и для участников службы Microsoft Exchange. значение свойства АпппринЦипалид будет использоваться для идентификации субъекта-службы, которому назначается сертификат. С помощью значения свойства АпппринЦипалид для Lync Server 2013 можно назначить сертификат версии Office 365 для Lync Server (свойства StartDate и EndDate должны соответствовать сроку действия сертификата).

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

Затем следует повторить команду, на этот раз используя значение свойства АпппринЦипалид для Exchange 2013.

Если позднее вам потребуется удалить этот сертификат, сначала вам потребуется получить для него значение KeyId:

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

Эта команда возвращает следующие данные:

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

После этого вы можете удалить сертификат с помощью следующей команды:

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

Помимо назначения сертификата необходимо также настроить субъект-службу Office 365 для Exchange Online, добавив имя участника сервера для локальной версии Lync Server 2013. Это можно сделать, выполнив следующие четыре строки в сеансе PowerShell Microsoft Online Services.

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

