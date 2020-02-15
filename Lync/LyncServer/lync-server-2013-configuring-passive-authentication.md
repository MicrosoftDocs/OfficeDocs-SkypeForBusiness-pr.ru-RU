---
title: 'Lync Server 2013: Настройка пассивной проверки подлинности'
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
ms.openlocfilehash: 1a50cb75bdf833468d6974b9ddce1b282c1872d3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-passive-authentication"></a><span data-ttu-id="d6c11-102">Настройка пассивной проверки подлинности Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d6c11-102">Configuring Lync Server 2013 passive authentication</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6c11-103">_**Последнее изменение темы:** 2013-07-11_</span><span class="sxs-lookup"><span data-stu-id="d6c11-103">_**Topic Last Modified:** 2013-07-11_</span></span>

<span data-ttu-id="d6c11-104">В следующем разделе описано, как настроить Lync Server 2013 с накопительными пакетами обновления: 2013 июля для поддержки пассивной проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d6c11-104">The following section describes how to configure Lync Server 2013 with Cumulative Updates: July 2013 to support passive authentication.</span></span> <span data-ttu-id="d6c11-105">После включения Пользователи Lync, для которых включена двухфакторная проверка подлинности, должны использовать физическую или виртуальную смарт-карту и действительный ПИН-код для входа в систему с помощью Lync 2013 с накопительными обновлениями для Lync с накопительными обновлениями: Июль 2013 клиент.</span><span class="sxs-lookup"><span data-stu-id="d6c11-105">Once enabled, Lync users who are enabled for two-factor authentication will be required to use a physical or virtual smart card and a valid PIN to sign in using the Lync 2013 with Cumulative Updates: July 2013 client.</span></span>

<div class="">


> [!NOTE]  
> <span data-ttu-id="d6c11-106">Пользователям настоятельно рекомендуется включить пассивную проверку подлинности для регистратора и веб-служб на уровне службы.</span><span class="sxs-lookup"><span data-stu-id="d6c11-106">It is strongly recommended that customers enable passive authentication for Registrar and Web Services at the service level.</span></span> <span data-ttu-id="d6c11-107">Если пассивная проверка подлинности включена для регистратора и веб-служб на глобальном уровне, это может привести к сбоям проверки подлинности на уровне Организации для пользователей, которые не входят в состав Lync 2013 с накопительными пакетами обновления 2013: обновление клиента клиентского рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="d6c11-107">If passive authentication is enabled for Registrar and Web Services at the global level, it will likely result in organization-wide authentication failures for users who are not signing in with the Lync 2013 with Cumulative Updates: July 2013 client desktop client.</span></span>



</div>

<div>

## <a name="web-service-configuration"></a><span data-ttu-id="d6c11-108">Конфигурация веб-службы</span><span class="sxs-lookup"><span data-stu-id="d6c11-108">Web Service Configuration</span></span>

<span data-ttu-id="d6c11-109">Ниже описано, как создать настраиваемую конфигурацию веб-службы для директоров, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="d6c11-109">The following steps describe how to create a custom web service configuration for Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="d6c11-110">**Создание настраиваемой конфигурации веб-службы**</span><span class="sxs-lookup"><span data-stu-id="d6c11-110">**To create a custom web service configuration**</span></span>

1.  <span data-ttu-id="d6c11-111">Выполните вход на сервер Lync Server 2013 с накопительными пакетами обновления для сервера переднего плана 2013 с использованием учетной записи администратора Lync.</span><span class="sxs-lookup"><span data-stu-id="d6c11-111">Log in to your Lync Server 2013 with Cumulative Updates: July 2013 Front End server using a Lync administrator account.</span></span>

2.  <span data-ttu-id="d6c11-112">Запустите командную консоль Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d6c11-112">Launch the Lync Server 2013 Management Shell.</span></span>

3.  <span data-ttu-id="d6c11-113">В командной строке командной консоли Lync Server создайте новую конфигурацию веб-службы для каждого директора, корпоративного пула и сервера Standard Edition, для которых будет включена пассивная проверка подлинности, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d6c11-113">From the Lync Server Management Shell command-line, create a new Web Service configuration for each Director, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following command:</span></span>
    ```powershell
    New-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
    ```

    <div class="">
    

    > [!WARNING]  
    > <span data-ttu-id="d6c11-114">Значение полного доменного имени WsFedPassiveMetadataUri — это имя службы федерации сервера AD FS 2,0.</span><span class="sxs-lookup"><span data-stu-id="d6c11-114">The value for the WsFedPassiveMetadataUri FQDN is the Federation Service Name of your AD FS 2.0 server.</span></span> <span data-ttu-id="d6c11-115">Значение имени службы федерации можно найти в консоли управления AD FS 2,0, щелкнув правой кнопкой мыши элемент <STRONG>Служба</STRONG> в области навигации, а затем выбрав <STRONG>изменить свойства службы федерации</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="d6c11-115">The Federation Service Name value can be found in the AD FS 2.0 Management Console by right-clicking on <STRONG>Service</STRONG> from the navigation pane and then selecting <STRONG>Edit Federation Service Properties</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="d6c11-116">Убедитесь, что значения Усевсфедпассивеаус и WsFedPassiveMetadataUri были заданы правильно, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d6c11-116">Verify that the UseWsFedPassiveAuth and WsFedPassiveMetadataUri values were set correctly by running the following command:</span></span>
     ```powershell
     Get-CsWebServiceConfiguration -identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseWsFedPassiveAuth, WsFedPassiveMetadataUri
     ```
5.  <span data-ttu-id="d6c11-117">Для клиентов пассивная проверка подлинности является наименее предпочтительным методом проверки подлинности для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d6c11-117">For clients, Passive Authentication is the least preferred authentication method for webticket authentication.</span></span> <span data-ttu-id="d6c11-118">Для всех директоров, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности, все остальные типы проверки подлинности необходимо отключить в веб-службах Lync, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d6c11-118">For all Directors, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication, all other authentication types must be disabled in Lync Web Services by running the following command:</span></span>
    ```powershell
    Set-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" -UseCertificateAuth $false -UsePinAuth $false -UseWindowsAuth NONE
     ```
6.  <span data-ttu-id="d6c11-119">Убедитесь, что все остальные типы проверки подлинности успешно отключены, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d6c11-119">Verify that all other authentication types have been successfully disabled by running the following command:</span></span>
    ```powershell
    Get-CsWebServiceConfiguration -Identity "Service:WebServer:LyncPool01.contoso.com" | format-list UseCertificateAuth, UsePinAuth, UseWindowsAuth
     ```
</div>

<div>

## <a name="proxy-configuration"></a><span data-ttu-id="d6c11-120">Настройка прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="d6c11-120">Proxy Configuration</span></span>

<span data-ttu-id="d6c11-121">Если проверка подлинности сертификатов отключена для веб-служб Lync, клиент Lync будет использовать менее предпочтительный тип проверки подлинности, например Kerberos или NTLM, для проверки подлинности в службе регистратора.</span><span class="sxs-lookup"><span data-stu-id="d6c11-121">When certificate authentication is disabled for Lync Web Services, the Lync client will use a less preferred authentication type, such as Kerberos or NTLM, to authenticate to the Registrar service.</span></span> <span data-ttu-id="d6c11-122">Проверка подлинности с помощью сертификата по-прежнему необходима для того, чтобы позволить клиенту Lync получить билет, однако для службы регистратора необходимо отключить Kerberos и NTLM.</span><span class="sxs-lookup"><span data-stu-id="d6c11-122">Certificate authentication is still needed to allow the Lync client to retrieve a webticket, however, Kerberos and NTLM must be disabled for the Registrar service.</span></span>

<span data-ttu-id="d6c11-123">Ниже описано, как создать конфигурацию настраиваемого прокси-сервера для пограничных пулов, корпоративных пулов и серверов Standard Edition, для которых будет включена пассивная проверка подлинности.</span><span class="sxs-lookup"><span data-stu-id="d6c11-123">The following steps describe how to create a custom proxy configuration for Edge Pools, Enterprise Pools, and Standard Edition servers that will be enabled for passive authentication.</span></span>

<span data-ttu-id="d6c11-124">**Создание настраиваемой конфигурации прокси-сервера**</span><span class="sxs-lookup"><span data-stu-id="d6c11-124">**To create a custom proxy configuration**</span></span>

1.  <span data-ttu-id="d6c11-125">В командной строке командной консоли Lync Server создайте новую конфигурацию прокси-сервера для каждого сервера Lync Server 2013 с накопительными пакетами обновления: пограничный пул 2013 июля, корпоративный пул и сервер Standard Edition, для которых будет включена пассивная проверка подлинности с помощью команды следующие команды:</span><span class="sxs-lookup"><span data-stu-id="d6c11-125">From the Lync Server Management Shell command-line, create a new proxy configuration for each Lync Server 2013 with Cumulative Updates: July 2013 Edge Pool, Enterprise Pool, and Standard Edition server that will be enabled for passive authentication by running the following commands:</span></span>
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:EdgeServer:EdgePool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```
    
       ```powershell
        New-CsProxyConfiguration -Identity "Service:Registrar:LyncPool01.contoso.com" 
        -UseKerberosForClientToProxyAuth $False -UseNtlmForClientToProxyAuth $False
       ```

2.  <span data-ttu-id="d6c11-126">Убедитесь, что все остальные типы проверки подлинности прокси-сервера успешно отключены, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d6c11-126">Verify that all other proxy authentication types have been successfully disabled by running the following command:</span></span>
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

