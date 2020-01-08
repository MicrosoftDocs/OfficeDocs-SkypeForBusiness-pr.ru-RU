---
title: 'Lync Server 2013: настройка статического маршрута для дистанционного управления вызовами'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a11b24fc8d4be54f5645853c050891d3821945e4
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40971221"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="c80be-102">Настройка статического маршрута для дистанционного управления вызовами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c80be-102">Configure a static route for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c80be-103">_**Тема последнего изменения:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="c80be-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="c80be-104">Удаленное управление звонками требует, чтобы каждый пул серверов Lync Server настроился с помощью пути из этого пула на шлюз SIP/КСТА, который подключается к частной сети обмена филиалами (УАТС).</span><span class="sxs-lookup"><span data-stu-id="c80be-104">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="c80be-105">Этот путь требует, чтобы каждый пул выделил один статический маршрут для каждого шлюза, на который будет прокси-сервер, управляющие сообщениями, связанные с вызовами УАТС.</span><span class="sxs-lookup"><span data-stu-id="c80be-105">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="c80be-106">Если вы настроили глобальный статический маршрут для удаленного управления звонком, то каждый пул, для которого не настроен статический маршрут на уровне пула, будет использовать глобальный статический маршрут.</span><span class="sxs-lookup"><span data-stu-id="c80be-106">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="c80be-107">Настройка статического маршрута для удаленного управления звонками</span><span class="sxs-lookup"><span data-stu-id="c80be-107">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="c80be-108">Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или роль управления доступом на основе ролей (RBAC), для которой вы назначили командлет **New-ксстатикрауте** .</span><span class="sxs-lookup"><span data-stu-id="c80be-108">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="c80be-109">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="c80be-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c80be-110">Чтобы создать статический маршрут и вставить его в переменную $TLSRoute или $TCPRoute, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="c80be-110">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="c80be-111">Чтобы сопоставить дочерние домены домена, можно задать подстановочное значение в параметре Матчури.</span><span class="sxs-lookup"><span data-stu-id="c80be-111">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter.</span></span> <span data-ttu-id="c80be-112">Например, <STRONG>\*. contoso.NET</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c80be-112">For example, <STRONG>\*.contoso.net</STRONG>.</span></span> <span data-ttu-id="c80be-113">Это значение соответствует любому домену, который заканчивается на суффикс <STRONG>contoso.NET</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c80be-113">That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="c80be-114">Для подключения к протоколу TLS введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c80be-114">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        <span data-ttu-id="c80be-115">Например:</span><span class="sxs-lookup"><span data-stu-id="c80be-115">For example:</span></span>
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        <span data-ttu-id="c80be-116">Если для Уседефаултцертификате задано значение false, необходимо указать параметры Тлсцертиссуер и Тлсцертсериалнумбер.</span><span class="sxs-lookup"><span data-stu-id="c80be-116">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="c80be-117">Эти параметры указывают имя центра сертификации (ЦС), который выдал сертификат, используемый в статическом маршруте, и порядковый номер этого TLS-сертификата соответственно.</span><span class="sxs-lookup"><span data-stu-id="c80be-117">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="c80be-118">Подробнее об этих параметрах можно узнать в справке Lync Server Management Shell, введя следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="c80be-118">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - <span data-ttu-id="c80be-119">Для подключения по протоколу TCP введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c80be-119">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="c80be-120">Если вы указали полное доменное имя (FQDN), необходимо сначала настроить DNS A Record (доменное имя).</span><span class="sxs-lookup"><span data-stu-id="c80be-120">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        <span data-ttu-id="c80be-121">Например:</span><span class="sxs-lookup"><span data-stu-id="c80be-121">For example:</span></span>
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        <span data-ttu-id="c80be-122">Ниже указаны значения по умолчанию для статических маршрутов с необязательными параметрами.</span><span class="sxs-lookup"><span data-stu-id="c80be-122">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="c80be-123">Enabled = True</span><span class="sxs-lookup"><span data-stu-id="c80be-123">Enabled = True</span></span>
        
          - <span data-ttu-id="c80be-124">Матчонлифонеури = false</span><span class="sxs-lookup"><span data-stu-id="c80be-124">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="c80be-125">Реплацехостинрекуестури = false</span><span class="sxs-lookup"><span data-stu-id="c80be-125">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="c80be-126">Мы настоятельно рекомендуем не менять эти значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c80be-126">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="c80be-127">Однако если вы должны изменить любой из этих параметров, ознакомьтесь со справкой оболочки среды управления Lync Server, введя в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c80be-127">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  <span data-ttu-id="c80be-128">Чтобы сохранить созданный статический маршрут в хранилище Центрального управления, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="c80be-128">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c80be-129">См. также</span><span class="sxs-lookup"><span data-stu-id="c80be-129">See Also</span></span>


[<span data-ttu-id="c80be-130">Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c80be-130">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="c80be-131">Определение IP-адреса для шлюза SIP/CSTA в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c80be-131">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

