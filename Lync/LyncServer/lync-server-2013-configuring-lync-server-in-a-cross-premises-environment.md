---
title: 'Lync Server 2013: Настройка Lync Server в распределенной среде'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44d1f06fcbdbbba7400bf45857dad9ed57971363
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43779725"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a>Настройка Microsoft Lync Server 2013 в распределенной среде

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2017-02-21_

В конфигурации с несколькими локальными пользователями некоторые пользователи размещаются в локальной установке Microsoft Lync Server 2013, в то время как другие пользователи размещены в версии Lync Server для Office 365. Чтобы настроить межсерверную проверку подлинности в распределенной среде, необходимо сначала настроить локальную установку Lync Server 2013, чтобы доверять серверу авторизации Office 365. Для выполнения этого процесса можно выполнить следующий сценарий консоли управления Lync Server:

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

После выполнения сценария необходимо настроить отношение доверия между Lync Server 2013 и сервером авторизации, а также второе отношение доверия между Exchange 2013 и сервером авторизации. Это можно выполнить только с помощью командлетов Microsoft Online Services.

<div>


> [!NOTE]  
> Если вы еще не установили командлеты Microsoft Online Services, то для продолжения вам потребуется выполнить две операции. Во-первых, загрузите и установите 64-разрядную версию помощника по входу в Microsoft Online Services. После завершения установки Скачайте и установите 64-разрядную версию модуля Microsoft Online Services для Windows PowerShell. Подробные сведения об установке и использовании модуля Microsoft Online Services см. на веб-сайте, посвященном Office 365. Данные инструкции также помогут вам настроить единый вход, федерацию и синхронизацию между Office 365 и Active Directory.<BR>Если вы не установили эти командлеты, сценарий завершится с ошибками, так как командлет Get-CsTenant будет недоступен.



</div>

После настройки Office 365 и создания субъектов службы Office 365 для Lync Server 2013 и Exchange 2013 необходимо зарегистрировать учетные данные этих субъектов службы. Для этого вам следует сначала получить X.509 Base64 в виде файла CER. После этого данный сертификат применяется к субъектам-службам Office 365.

После получения сертификата X. 509 запустите модуль Microsoft Online Services (нажмите кнопку **Пуск**, выберите **все программы**, затем **Microsoft Online Services**, а затем выберите **модуль Microsoft Online Services для Windows PowerShell**). После открытия модуля "службы" введите следующую команду, чтобы импортировать модуль Microsoft Online Windows PowerShell, содержащий командлеты, которые можно использовать для управления субъектами-службами:

    Import-Module MSOnlineExtended

После завершения импорта модуля введите следующую команду и нажмите клавишу ВВОД для подключения к Office 365:

    Connect-MsolService

После нажатия клавиши ВВОД отображается диалоговое окно. Введите в диалоговом окне имя пользователя и пароль Microsoft 365 или Office 365, а затем нажмите кнопку ОК.

После подключения к Office 365 вы можете запустить следующую команду для получения информации о субъектах-службах:

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

Следующий этап состоит из импорта, кодирования и назначения сертификата X.509. Чтобы импортировать и закодировать сертификат, используйте следующие команды Windows PowerShell, чтобы указать полный путь к файлу. CER-файл при вызове метода Import:

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

После завершения импорта и кодирования сертификата вы можете назначить его своим субъектам-службам Office 365. Для этого сначала воспользуйтесь командлетом Get-MsolServicePrincipal, чтобы извлечь значение свойства AppPrincipalId для субъектов-служб Lync Server и Microsoft Exchange; это значение свойства AppPrincipalId будет использоваться для идентификации субъекта-службы, которому назначается сертификат. С помощью значения свойства AppPrincipalId для Lync Server 2013 в наличии выполните следующую команду, чтобы назначить сертификат версии Office 365 для Lync Server (свойства StartDate и EndDate должны соответствовать сроку действия сертификата):

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

Затем необходимо повторить команду, на этот раз используя значение свойства AppPrincipalId для Exchange 2013.

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

В дополнение к назначению сертификата необходимо также настроить субъект-службу Office 365 для Exchange Online, добавив имя участника сервера для локальной версии Lync Server 2013. Это можно сделать, выполнив следующие четыре строки в сеансе PowerShell Microsoft Online Services:

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

