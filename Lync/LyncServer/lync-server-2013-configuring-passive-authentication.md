---
title: 'Lync Server 2013: Настройка пассивной проверки подлинности'
description: 'Lync Server 2013: Настройка пассивной проверки подлинности.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52a83c1413dcac18fb37ff0fe308266a3d7aeab4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548295"
---
# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="6573c-103">Настройка пассивной проверки подлинности Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6573c-103">Configuring Lync Server 2013 passive authentication</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6573c-104">_**Последнее изменение темы:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="6573c-104">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="6573c-105">В следующем разделе описано, как настроить Lync Server 2013 с накопительными пакетами обновления: 2013 июля для поддержки пассивной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="6573c-105">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="6573c-106">После включения Пользователи Lync, для которых включена двухфакторная проверка подлинности, должны использовать физическую или виртуальную смарт-карту и действительный ПИН-код для входа в систему с помощью Lync 2013 с накопительными обновлениями для Lync с накопительными обновлениями: Июль 2013 клиент.</span><span class="sxs-lookup"><span data-stu-id="6573c-106">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="6573c-107">Пользователям настоятельно рекомендуется включить пассивную проверку подлинности для регистратора и веб-служб на уровне службы.</span><span class="sxs-lookup"><span data-stu-id="6573c-107">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="6573c-108">Если пассивная проверка подлинности включена для регистратора и веб-служб на глобальном уровне, это может привести к сбоям проверки подлинности на уровне Организации для пользователей, которые не входят в состав Lync 2013 с накопительными пакетами обновления 2013: обновление клиента клиентского рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="6573c-108">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="6573c-109">Конфигурация веб-службы</span><span class="sxs-lookup"><span data-stu-id="6573c-109">Web Service Configuration</span></span>

<span data-ttu-id="6573c-110">Ниже описано, как создать настраиваемую конфигурацию веб-службы для директоров, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="6573c-110">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="6573c-111">**Создание настраиваемой конфигурации веб-службы**</span><span class="sxs-lookup"><span data-stu-id="6573c-111">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="6573c-112">Выполните вход на сервер Lync Server 2013 с накопительными пакетами обновления для сервера переднего плана 2013 с использованием учетной записи администратора Lync.</span><span class="sxs-lookup"><span data-stu-id="6573c-112">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="6573c-113">Запустите командную консоль Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6573c-113">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="6573c-114">В командной строке командной консоли Lync Server создайте новую конфигурацию веб-службы для каждого директора, корпоративного пула и сервера Standard Edition, для которых будет включена пассивная проверка подлинности, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6573c-114">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="6573c-115">Значение полного доменного имени WsFedPassiveMetadataUri — это имя службы федерации сервера AD FS 2,0.</span><span class="sxs-lookup"><span data-stu-id="6573c-115">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="6573c-116">Значение имени службы федерации можно найти в консоли управления AD FS 2,0, щелкнув правой кнопкой мыши элемент <STRONG>Служба</STRONG> в области навигации, а затем выбрав <STRONG>изменить свойства службы федерации</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="6573c-116">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="6573c-117">Убедитесь, что значения Усевсфедпассивеаус и WsFedPassiveMetadataUri были заданы правильно, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6573c-117">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="6573c-118">Для клиентов пассивная проверка подлинности является наименее предпочтительным методом проверки подлинности для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="6573c-118">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="6573c-119">Для всех директоров, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности, все остальные типы проверки подлинности необходимо отключить в веб-службах Lync, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6573c-119">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="6573c-120">Убедитесь, что все остальные типы проверки подлинности успешно отключены, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6573c-120">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="6573c-121">Настройка прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="6573c-121">Proxy Configuration</span></span>

<span data-ttu-id="6573c-122">Если проверка подлинности сертификатов отключена для веб-служб Lync, клиент Lync будет использовать менее предпочтительный тип проверки подлинности, например Kerberos или NTLM, для проверки подлинности в службе регистратора.</span><span class="sxs-lookup"><span data-stu-id="6573c-122">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="6573c-123">Проверка подлинности с помощью сертификата по-прежнему необходима для того, чтобы позволить клиенту Lync получить билет, однако для службы регистратора необходимо отключить Kerberos и NTLM.</span><span class="sxs-lookup"><span data-stu-id="6573c-123">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="6573c-124">Ниже описано, как создать конфигурацию настраиваемого прокси-сервера для пограничных пулов, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="6573c-124">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="6573c-125">**Создание настраиваемой конфигурации прокси-сервера**</span><span class="sxs-lookup"><span data-stu-id="6573c-125">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="6573c-126">В командной строке командной консоли Lync Server создайте новую конфигурацию прокси-сервера для каждого сервера Lync Server 2013 с накопительными пакетами обновления 2013: пограничный пул, корпоративный пул и сервер Standard Edition, для которых будет включена пассивная проверка подлинности, выполнив следующие команды:</span><span class="sxs-lookup"><span data-stu-id="6573c-126">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="6573c-127">Убедитесь, что все остальные типы проверки подлинности прокси-сервера успешно отключены, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6573c-127">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth
     ```
</div>

</div>

<span> </span>

</div>

</div>

</div>

