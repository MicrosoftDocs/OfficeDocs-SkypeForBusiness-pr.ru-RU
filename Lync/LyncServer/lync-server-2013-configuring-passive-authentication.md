---
title: 'Lync Server 2013: Настройка пассивной проверки подлинности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server passive authentication
ms:assetid: 9a904b8d-9fce-4abf-be73-5c8e48cfb53a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308569(v=OCS.15)
ms:contentKeyID: 54973690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c85bd20222a5fa70d052b21f62d0c19c76eea46
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841195"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="bb6b2-102">Настройка пассивной проверки подлинности Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb6b2-102">Configuring Lync Server 2013 passive authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb6b2-103">_**Тема последнего изменения:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="bb6b2-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="bb6b2-104">В следующем разделе описано, как настроить Lync Server 2013 с накопительными обновлениями: Июль 2013 для поддержки пассивной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="bb6b2-104">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="bb6b2-105">После включения Пользователи Lync, на которых включена двухфакторная проверка подлинности, должны использовать физическую или виртуальную смарт-карту и допустимый ПИН-код, чтобы войти в систему с помощью Lync 2013 с накопительными обновлениями: Июль 2013 (клиент).</span><span class="sxs-lookup"><span data-stu-id="bb6b2-105">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="bb6b2-106">Заказчикам настоятельно рекомендуется включить пассивную проверку подлинности для регистратора и веб-служб на уровне служб.</span><span class="sxs-lookup"><span data-stu-id="bb6b2-106">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="bb6b2-107">Если для регистраторов и веб-служб на глобальном уровне включена пассивная проверка подлинности, это может привести к сбоям проверки подлинности в масштабах Организации для пользователей, которые не входят в состав Lync 2013 с накопительными обновлениями: Июль 2013 клиентские компьютеры.</span><span class="sxs-lookup"><span data-stu-id="bb6b2-107">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="bb6b2-108">Конфигурация веб-служб</span><span class="sxs-lookup"><span data-stu-id="bb6b2-108">Web Service Configuration</span></span>

<span data-ttu-id="bb6b2-109">Ниже описана процедура создания настраиваемой конфигурации веб-служб для директоров, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="bb6b2-109">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="bb6b2-110">**Порядок создания настраиваемой конфигурации веб-служб**</span><span class="sxs-lookup"><span data-stu-id="bb6b2-110">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="bb6b2-111">Войдите на сервер Lync Server 2013 с накопительными обновлениями: сервер Июль 2013 на сервере переднего плана с помощью учетной записи администратора Lync.</span><span class="sxs-lookup"><span data-stu-id="bb6b2-111">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="bb6b2-112">Запустите командную консоль Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bb6b2-112">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="bb6b2-113">В командной строке оболочки Lync Server Management Shell создайте новую конфигурацию веб-службы для каждого директора, корпоративного пула и сервера Standard Edition, для которых будет включена пассивная проверка подлинности, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb6b2-113">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    
        New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    
    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="bb6b2-p103">Значением полного доменного имени WsFedPassiveMetadataUri является имя службы федерации сервера AD FS 2.0. Значение имени службы федерации можно найти в консоли управления AD FS 2.0, щелкнув <STRONG>Служба</STRONG> в области навигации правой кнопкой мыши и затем выбрав <STRONG>Изменить свойства службы федерации</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="bb6b2-p103">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server. The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="bb6b2-116">Проверьте правильность значений UseWsFedPassiveAuth и WsFedPassiveMetadataUri, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb6b2-116">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
    
        Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri

5.  <span data-ttu-id="bb6b2-117">Для клиентов пассивная проверка подлинности является наименее предпочтительным способом проверки подлинности WebTicket.</span><span class="sxs-lookup"><span data-stu-id="bb6b2-117">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="bb6b2-118">Для всех режиссеров, корпоративных пулов и серверов Standard Edition, для которых будет разрешена пассивная проверка подлинности, в веб-службах Lync должны быть отключены все другие типы проверки подлинности, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb6b2-118">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    
        Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE

6.  <span data-ttu-id="bb6b2-119">Убедитесь, что все другие типы проверки подлинности успешно отключены, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb6b2-119">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    
        Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth

</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="bb6b2-120">Конфигурация прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="bb6b2-120">Proxy Configuration</span></span>

<span data-ttu-id="bb6b2-121">Если для веб-служб Lync отключена проверка подлинности сертификата, клиент Lync будет использовать менее предпочтительный тип проверки подлинности, например Kerberos или NTLM, для проверки подлинности в службе регистратора.</span><span class="sxs-lookup"><span data-stu-id="bb6b2-121">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="bb6b2-122">Проверка подлинности сертификата по-прежнему необходима для того, чтобы клиент Lync мог получить веб-билет, но для службы регистратора необходимо отключить Kerberos и NTLM.</span><span class="sxs-lookup"><span data-stu-id="bb6b2-122">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="bb6b2-123">Ниже описана процедура создания настраиваемой конфигурации прокси-сервера для пограничных пулов, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="bb6b2-123">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="bb6b2-124">**Порядок создания настраиваемой конфигурации прокси-сервера**</span><span class="sxs-lookup"><span data-stu-id="bb6b2-124">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="bb6b2-125">В командной строке оболочки Lync Server Management Shell создайте новую конфигурацию прокси-сервера для каждого сервера Lync Server 2013 с накопительными обновлениями для каждого из выпусков: Июль 2013 EDGE, корпоративный пул и сервер Standard Edition, для которых будет включена пассивная проверка подлинности. следующие команды:</span><span class="sxs-lookup"><span data-stu-id="bb6b2-125">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="bb6b2-126">Убедитесь, что все остальные типы проверки подлинности прокси-сервера успешно отключены, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="bb6b2-126">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
    
        Get-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com"
         | format-list UseKerberosForClientToProxyAuth, UseNtlmForClientToProxyAuth, UseCertifcateForClientToProxyAuth

</div>

</div>

<span> </span>

</div>

</div>

</div>

