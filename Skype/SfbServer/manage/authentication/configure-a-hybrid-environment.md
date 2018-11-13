---
title: Настройка проверки подлинности сервер сервер для Скайп для гибридной среды Business Server
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 700639ec-5264-4449-a8a6-d7386fad8719
description: 'Сводка: Настройка проверки подлинности сервер сервер для Скайп для гибридной среды Business Server.'
ms.openlocfilehash: 02412c152e017da95c82ff6f8ad6f08db1a105ef
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295236"
---
# <a name="configure-server-to-server-authentication-for-a-skype-for-business-server-hybrid-environment"></a><span data-ttu-id="89071-103">Настройка проверки подлинности сервер сервер для Скайп для гибридной среды Business Server.</span><span class="sxs-lookup"><span data-stu-id="89071-103">Configure server-to-server authentication for a Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="89071-104">**Сводка:** Настройка проверки подлинности сервер сервер для Скайп для гибридной среды Business Server.</span><span class="sxs-lookup"><span data-stu-id="89071-104">**Summary:** Configure server-to-server authentication for Skype for Business Server hybrid environment.</span></span>

<span data-ttu-id="89071-105">В гибридной конфигурации некоторые пользователи размещаются в локальной установки Скайп для Business Server в то время как другие пользователи размещаются в версии Office 365 Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="89071-105">In a hybrid configuration, some of your users are homed on an on-premises installation of Skype for Business Server while other users are homed on the Office 365 version of Skype for Business Server.</span></span> <span data-ttu-id="89071-106">Чтобы настроить проверку подлинности сервер сервер в гибридной среде, необходимо настроить своей локальной установки Скайп для Business Server для доверия серверу авторизации Office 365.</span><span class="sxs-lookup"><span data-stu-id="89071-106">In order to configure server-to-server authentication in a hybrid environment, you must first configure your on-premises installation of Skype for Business Server to trust the Office 365 authorization server.</span></span> <span data-ttu-id="89071-107">Первым шагом этот процесс может быть выполнено, выполнив следующие Скайп для скрипта консоли Business Server:</span><span class="sxs-lookup"><span data-stu-id="89071-107">The initial step in this process can be carried out by running the following Skype for Business Server Management Shell script:</span></span>

```
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
```

<span data-ttu-id="89071-p102">Помните о том, что имя области для клиента обычно отличается от имени организации; на деле имя области почти всегда совпадает с идентификатором клиента. Поэтому первая строка скрипта используется для получения значения свойства TenantId для заданного клиента (в данном случае это fabrikam.com) и последующего назначения этого имени переменной $TenantId:</span><span class="sxs-lookup"><span data-stu-id="89071-p102">Keep in mind that the realm name for a tenant is typically different than the organization name; in fact, the realm name is almost always the same as the tenant ID. Because of that, the first line in the script is used to return the value of the TenantId property for the specified tenant (in this case, fabrikam.com) and then assign that name to the variable $TenantId:</span></span>

```
$TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId
```

<span data-ttu-id="89071-110">После выполнения скрипта необходимо настроить отношения доверия между Скайп для Business Server и сервера авторизации и второй отношения доверия между Exchange 2013 и сервера авторизации.</span><span class="sxs-lookup"><span data-stu-id="89071-110">After the script completes, you must then configure a trust relationship between Skype for Business Server and the authorization server, and a second trust relationship between Exchange 2013 and the authorization server.</span></span> <span data-ttu-id="89071-111">Это возможно только с помощью командлетов Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="89071-111">This can only be done by using the Microsoft Online Services cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="89071-112">Если командлеты Microsoft Online Services не установлены, потребуется выполнить две операции перед тем, как продолжить.</span><span class="sxs-lookup"><span data-stu-id="89071-112">If you have not installed the Microsoft Online Services cmdlets, you will need to do two things before proceeding.</span></span> <span data-ttu-id="89071-113">Во-первых, скачайте и установите 64-разрядную версию помощника по входу в Microsoft Online Services.</span><span class="sxs-lookup"><span data-stu-id="89071-113">First, download and install the 64-bit version of the Microsoft Online Services Sign-in Assistant.</span></span> <span data-ttu-id="89071-114">После завершения установки, загрузите и установите 64-разрядная версия Microsoft Online Services модуль для Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89071-114">After installation is complete, download and install the 64-bit version of the Microsoft Online Services Module for Windows PowerShell.</span></span> <span data-ttu-id="89071-115">Подробные сведения по установке и использованию модуль Microsoft Online Services можно найти на веб-сайте Office 365.</span><span class="sxs-lookup"><span data-stu-id="89071-115">Detailed information for installing and using the Microsoft Online Services Module can be found on the Office 365 web site.</span></span> <span data-ttu-id="89071-116">Эти инструкции также можно узнать, как настроить единый вход, федерации и синхронизации между Office 365 и Active Directory.</span><span class="sxs-lookup"><span data-stu-id="89071-116">These instructions will also tell you how to configure single sign-on, federation, and synchronization between Office 365 and Active Directory.</span></span> 

<span data-ttu-id="89071-117">Если вы не выполнили установку этих командлетов, то произойдет сбой вашего сценария, так как командлет Get-CsTenant будет недоступен.</span><span class="sxs-lookup"><span data-stu-id="89071-117">If you have not installed these cmdlets your script will fail because the Get-CsTenant cmdlet will not be available.</span></span>

<span data-ttu-id="89071-118">После настройки Office 365, и после создания Office 365 субъектов-служб для Скайп для Business Server и Exchange 2013, затем нужно зарегистрировать свои учетные данные в этих субъектов-служб.</span><span class="sxs-lookup"><span data-stu-id="89071-118">After you have configured Office 365, and after you have created Office 365 service principals for Skype for Business Server and Exchange 2013, you will then need to register your credentials with these service principals.</span></span> <span data-ttu-id="89071-119">Для этого необходимо сначала получить X.509 Base64 в виде файла CER.</span><span class="sxs-lookup"><span data-stu-id="89071-119">In order to do this, you must first obtain an X.509 Base64 saved as a .CER file.</span></span> <span data-ttu-id="89071-120">Этот сертификат затем будет применяться к участников службы Office 365.</span><span class="sxs-lookup"><span data-stu-id="89071-120">This certificate will then be applied to the Office 365 service principals.</span></span>

<span data-ttu-id="89071-121">После получения сертификата X.509, начать модуль Microsoft Online Services (нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Microsoft Online Services**и нажмите кнопку **Microsoft Online Services модуль для Windows PowerShell**).</span><span class="sxs-lookup"><span data-stu-id="89071-121">When you have obtained the X.509 certificate, start the Microsoft Online Services Module (click **Start**, click **All Programs**, click **Microsoft Online Services**, and then click **Microsoft Online Services Module for Windows PowerShell**).</span></span> <span data-ttu-id="89071-122">После открытия модуля службы, введите следующие действия, чтобы импортировать модуль Microsoft Online Windows PowerShell, содержащий командлетов, которые можно использовать для управления субъектов-служб:</span><span class="sxs-lookup"><span data-stu-id="89071-122">After the Services Module opens, type the following to import the Microsoft Online Windows PowerShell module containing the cmdlets that can be used to manage service principals:</span></span>

```
Import-Module MSOnlineExtended
```

<span data-ttu-id="89071-123">По завершении импорта модуля введите следующую команду и нажмите клавишу ВВОД для подключения к Office 365:</span><span class="sxs-lookup"><span data-stu-id="89071-123">When the module has been imported, type the following command and then press ENTER in order to connect to Office 365:</span></span>

```
Connect-MsolService
```

<span data-ttu-id="89071-124">При нажатии клавиши Enter отображается диалоговое окно учетных данных.</span><span class="sxs-lookup"><span data-stu-id="89071-124">After you press ENTER, a credentials dialog box will appear.</span></span> <span data-ttu-id="89071-125">В диалоговом окне введите имя пользователя Office 365 и пароль и нажмите кнопку ОК.</span><span class="sxs-lookup"><span data-stu-id="89071-125">Enter your Office 365 user name and password in the dialog box, and then click OK.</span></span>

<span data-ttu-id="89071-126">Как только вы подключены к Office 365, можно затем выполните следующую команду для получения информации о субъектах:</span><span class="sxs-lookup"><span data-stu-id="89071-126">As soon as you are connected to Office 365, you can then run the following command in order to return information about your service principals:</span></span>

```
Get-MsolServicePrincipal
```

<span data-ttu-id="89071-127">Команда возвращает для всех субъектов-служб сведения, похожие на следующие:</span><span class="sxs-lookup"><span data-stu-id="89071-127">You should get back information similar to this for all your service principals:</span></span>

<pre>
ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
AccountEnabled       : True
Addresses            : {}
AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
DisplayName          : Skype for Business Server
ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
ServicePrincipalName : SkypeForBusinessServer/litwareinc.com
TrustedForDelegation : True
</pre>

<span data-ttu-id="89071-128">На следующем шаге выполняется импорт, кодирование и назначение сертификата X.509.</span><span class="sxs-lookup"><span data-stu-id="89071-128">The next step is to import, encode, and assign the X.509 certificate.</span></span> <span data-ttu-id="89071-129">Импорт и кодирования сертификат, используйте следующие команды Windows PowerShell, убедитесь указать полный путь к вашей. Файл CER при вызове метода импорта:</span><span class="sxs-lookup"><span data-stu-id="89071-129">To import and encode the certificate, use the following Windows PowerShell commands, being sure to specify the complete file path to your .CER file when you call the Import method:</span></span>

```
$certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
$certificate.Import("C:\Certificates\Office365.cer")
$binaryValue = $certificate.GetRawCertData()
$credentialsValue = [System.Convert]::ToBase64String($binaryValue)
```

<span data-ttu-id="89071-130">После того как сертификат был импортирован и кодировке, затем можно назначить сертификат для субъектов-служб Office 365.</span><span class="sxs-lookup"><span data-stu-id="89071-130">After the certificate has been imported and encoded, you can then assign the certificate to your Office 365 service principals.</span></span> <span data-ttu-id="89071-131">Для этого сначала командлет Get-MsolServicePrincipal для получения значение свойства AppPrincipalId для Скайп для Business Server и участников службы Microsoft Exchange; значение свойства AppPrincipalId будет использоваться для идентификации участников-служб, назначаемое сертификат.</span><span class="sxs-lookup"><span data-stu-id="89071-131">To do that, first use the Get-MsolServicePrincipal to retrieve the value of the AppPrincipalId property for both the Skype for Business Server and the Microsoft Exchange service principals; the value of the AppPrincipalId property will be used to identify the service principal being assigned the certificate.</span></span> <span data-ttu-id="89071-132">С помощью AppPrincipalId свойство руку значение для Скайп Business Server, выполните следующую команду назначение сертификата до версии Office 365 Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="89071-132">With the AppPrincipalId property value for Skype for Business Server in hand, use the following command to assign the certificate to the Office 365 version of Skype for Business Server:</span></span>

```
New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue 
```

<span data-ttu-id="89071-133">Необходимо повторно выполнить команду, это время с помощью значение свойства AppPrincipalId для Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="89071-133">You should then repeat the command, this time using the AppPrincipalId property value for Exchange 2013.</span></span>

<span data-ttu-id="89071-134">Если позднее вам потребуется удалить этот сертификат, сначала вам потребуется получить для него значение KeyId:</span><span class="sxs-lookup"><span data-stu-id="89071-134">If you later need to delete that certificate, you can do so by first retrieving the KeyId for the certificate:</span></span>

```
Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
```

<span data-ttu-id="89071-135">Эта команда возвращает следующие данные:</span><span class="sxs-lookup"><span data-stu-id="89071-135">That command will return data like this one:</span></span>

<pre>
Type      : Asymmetric
Value     : 
KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
StartDate : 6/1/2012 8:00:00 AM
EndDate   : 5/31/2013 8:00:00 AM
Usage     : Verify
</pre>

<span data-ttu-id="89071-136">После этого вы можете удалить сертификат с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="89071-136">You can then delete the certificate by using a command similar to this:</span></span>

```
Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0
```

<span data-ttu-id="89071-137">В дополнение к назначения сертификата, который необходимо настроить Exchange Online участников-служб и настройка локальной версии Скайп для Business Server внешние Web services URL-адреса в качестве участника-службы Office 365.</span><span class="sxs-lookup"><span data-stu-id="89071-137">In addition to assigning a certificate, you must also configure the Exchange Online Service Principal and configure your on-premises version of Skype for Business Server external Web services URLs as an Office 365 service principal.</span></span> <span data-ttu-id="89071-138">Для этого можно выполнить две следующие команды:</span><span class="sxs-lookup"><span data-stu-id="89071-138">That can be done by carrying out the following two commands.</span></span> 

<span data-ttu-id="89071-139">В следующем примере lync.contoso.com является внешним Web services URL-адрес Скайп для пула Business Server.</span><span class="sxs-lookup"><span data-stu-id="89071-139">In the following example, lync.contoso.com is the external Web services URL for the Skype for Business Server pool.</span></span> <span data-ttu-id="89071-140">Следует повторите эти действия, чтобы добавить всех внешних Web services URL-адреса в развертывании.</span><span class="sxs-lookup"><span data-stu-id="89071-140">You should repeat these steps to add all the external Web services URLs in the deployment.</span></span>

```
Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
$lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
$lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames
```