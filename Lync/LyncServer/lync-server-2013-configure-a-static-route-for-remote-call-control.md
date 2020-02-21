---
title: 'Lync Server 2013: Настройка статического маршрута для удаленного управления звонками'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a static route for remote call control
ms:assetid: f7003023-443d-48ee-989b-71e8b0b0abbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615051(v=OCS.15)
ms:contentKeyID: 48185855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41e871e3023449123af76530659397e1faa6b51d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-static-route-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="fd85b-102">Настройка статического маршрута для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd85b-102">Configure a static route for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd85b-103">_**Последнее изменение темы:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="fd85b-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="fd85b-104">Для удаленного управления вызовами необходимо, чтобы каждый пул Lync Server был настроен с использованием пути из этого пула к шлюзу SIP/CSTA, который подключается к УАТС.</span><span class="sxs-lookup"><span data-stu-id="fd85b-104">Remote call control requires that every Lync Server pool is configured with a path from that pool to the SIP/CSTA gateway that connects to the private branch exchange (PBX).</span></span> <span data-ttu-id="fd85b-105">Этот путь требует, чтобы каждому пулу был назначен один статический маршрут на каждый шлюз, на который пул будет передавать сообщения управления вызовами SIP, связанные с вызовами в УАТС.</span><span class="sxs-lookup"><span data-stu-id="fd85b-105">This path requires that each pool has one static route for each gateway to which the pool will proxy SIP call control messages associated with calls to the PBX.</span></span> <span data-ttu-id="fd85b-106">Если настроить глобальный статический маршрут для удаленного управления вызовами, каждый пул, для которого не задан статический маршрут на уровне пула, будет использовать этот глобальный маршрут.</span><span class="sxs-lookup"><span data-stu-id="fd85b-106">If you configure a global static route for remote call control, each pool that is not configured with a static route at the pool level will use the global static route.</span></span>

<div>

## <a name="to-configure-a-static-route-for-remote-call-control"></a><span data-ttu-id="fd85b-107">Настройка статического маршрута для удаленного управления вызовами</span><span class="sxs-lookup"><span data-stu-id="fd85b-107">To configure a static route for remote call control</span></span>

1.  <span data-ttu-id="fd85b-108">Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или роли управления доступом на основе ролей (RBAC), которой назначен командлет **New-CsStaticRoute** .</span><span class="sxs-lookup"><span data-stu-id="fd85b-108">Log on to a computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsStaticRoute** cmdlet.</span></span>

2.  <span data-ttu-id="fd85b-109">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="fd85b-109">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="fd85b-110">Чтобы настроить статический маршрут и поместить его в переменную $TLSRoute или $TCPRoute, выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="fd85b-110">To create a static route and put it in the variable $TLSRoute or $TCPRoute, do one of the following:</span></span>
    
    <div class="">
    

    > [!TIP]  
    > <span data-ttu-id="fd85b-p102">Для сопоставления дочерних доменов домена можно указать подстановочное значение параметра MatchUri. Например, <STRONG>\*.contoso.net</STRONG>. Это значение соответствует любому домену, который заканчивается суффиксом <STRONG>contoso.net</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="fd85b-p102">To match child domains of a domain, you can specify a wildcard value in the MatchUri parameter. For example, <STRONG>\*.contoso.net</STRONG>. That value matches any domain that ends with the suffix <STRONG>contoso.net</STRONG>.</span></span>

    
    </div>
    
      - <span data-ttu-id="fd85b-114">Для подключения по протоколу TLS введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fd85b-114">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination <gateway FQDN> -Port <gateway SIP listening port> -UseDefaultCertificate $true -MatchUri <destination domain>
        ```
        <span data-ttu-id="fd85b-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="fd85b-115">For example:</span></span>
        ```powershell
        $TLSRoute = New-CsStaticRoute -TLSRoute -Destination rccgateway.contoso.net -Port 5065 -UseDefaultCertificate $true -MatchUri *.contoso.net
        ```
        <span data-ttu-id="fd85b-116">Если для Уседефаултцертификате задано значение false, необходимо указать параметры TLSCertIssuer и TLSCertSerialNumber.</span><span class="sxs-lookup"><span data-stu-id="fd85b-116">If UseDefaultCertificate is set to False, you must specify TLSCertIssuer and TLSCertSerialNumber parameters.</span></span> <span data-ttu-id="fd85b-117">Эти параметры указывают имя центра сертификации (ЦС), который выдал сертификат, используемый в статическом маршруте, и серийный номер этого сертификата TLS соответственно.</span><span class="sxs-lookup"><span data-stu-id="fd85b-117">These parameters indicate the name of the certification authority (CA) that issued the certificate used in the static route, and the serial number of that TLS certificate, respectively.</span></span> <span data-ttu-id="fd85b-118">Для получения дополнительных сведений об этих параметрах ознакомьтесь со статьей Справка по консоли управления Lync Server, введя следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="fd85b-118">For details about these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
      - <span data-ttu-id="fd85b-119">Для подключения по протоколу TCP введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="fd85b-119">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
        <div class="">
        

        > [!NOTE]  
        > <span data-ttu-id="fd85b-120">Если указывается полное доменное имя, сначала необходимо настроить запись DNS.</span><span class="sxs-lookup"><span data-stu-id="fd85b-120">If you specify a fully qualified domain name (FQDN), you must configure a Domain Name System (DNS) A record first.</span></span>

        
        </div>
        
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination <gateway IP address or FQDN> -Port <gateway SIP listening port> -MatchUri <destination domain>
        ```
        <span data-ttu-id="fd85b-121">Например:</span><span class="sxs-lookup"><span data-stu-id="fd85b-121">For example:</span></span>
        ```powershell
        $TCPRoute = New-CsStaticRoute -TCPRoute -Destination 192.168.0.240 -Port 5065 -MatchUri *.contoso.net
        ```
        <span data-ttu-id="fd85b-122">Ниже приведены значения по умолчанию для необязательных параметров статических маршрутов.</span><span class="sxs-lookup"><span data-stu-id="fd85b-122">The following are default values for optional parameters for static routes:</span></span>
        
          - <span data-ttu-id="fd85b-123">Enabled = True</span><span class="sxs-lookup"><span data-stu-id="fd85b-123">Enabled = True</span></span>
        
          - <span data-ttu-id="fd85b-124">MatchOnlyPhoneUri = False</span><span class="sxs-lookup"><span data-stu-id="fd85b-124">MatchOnlyPhoneUri = False</span></span>
        
          - <span data-ttu-id="fd85b-125">ReplaceHostInRequestUri = False</span><span class="sxs-lookup"><span data-stu-id="fd85b-125">ReplaceHostInRequestUri = False</span></span>
        
        <span data-ttu-id="fd85b-126">Настоятельно рекомендуем не изменять эти значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="fd85b-126">We strongly recommend that you do not change these default values.</span></span> <span data-ttu-id="fd85b-127">Тем не менее, если необходимо изменить любой из этих параметров, ознакомьтесь со статьей Справка по консоли управления Lync Server, введя следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="fd85b-127">However, if you must change any of these parameters, see Lync Server Management Shell Help by typing the following at the command prompt:</span></span>
        ```powershell
        Get-Help New-CsStaticRoute -Full
        ```
4.  <span data-ttu-id="fd85b-128">Чтобы сохранить только что созданный статический маршрут в центральном хранилище управления, выполните одно из следующих действий (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="fd85b-128">To persist a newly created static route in the Central Management store, run one of the following, as appropriate:</span></span>
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TLSRoute}
       ```
    
       ```powershell
        Set-CsStaticRoutingConfiguration -Route @{Add=$TCPRoute}
       ```

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fd85b-129">См. также</span><span class="sxs-lookup"><span data-stu-id="fd85b-129">See Also</span></span>


[<span data-ttu-id="fd85b-130">Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd85b-130">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-trusted-application-entry-for-remote-call-control.md)  
[<span data-ttu-id="fd85b-131">Определение IP-адреса шлюза SIP/CSTA в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fd85b-131">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

