---
title: Настройка записи доверенного приложения для удаленного управления звонками
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trusted application entry for remote call control
ms:assetid: 37777f93-8b24-40cf-808e-7c6230eb2132
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558636(v=OCS.15)
ms:contentKeyID: 48183829
ms.date: 11/03/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0135d26f0483b10752c8a823fdbda15ab9ba37b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205225"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="89fcd-102">Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89fcd-102">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89fcd-103">_**Последнее изменение темы:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="89fcd-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="89fcd-104">Шлюз SIP/CSTA должен быть настроен как доверенное приложение, чтобы Lync Server мог применить статический маршрут для маршрутизации вызовов шлюза.</span><span class="sxs-lookup"><span data-stu-id="89fcd-104">The SIP/CSTA gateway must be configured as a trusted application in order for Lync Server to apply a static route to route calls to the gateway.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="89fcd-105">Если вы переносите пользователей из предыдущей версии развертывания Lync Server, убедитесь, что удалены все существующие записи доверенных приложений (ранее известные как авторизованные записи узла), созданные для шлюза SIP/CSTA, прежде чем выполнять процедуры, описанные в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="89fcd-105">If you're migrating users from a previous version of Lync Server deployment, be sure that you removed all existing trusted application entries (previously known as authorized host entries) you created for the SIP/CSTA gateway before following the procedures in this topic.</span></span> <span data-ttu-id="89fcd-106">Дополнительные сведения см. <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">в статье удаление устаревшего авторизованного узла в Lync Server 2013 (необязательно)</A>.</span><span class="sxs-lookup"><span data-stu-id="89fcd-106">For details, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span><BR><span data-ttu-id="89fcd-107">Если вы планируете развернуть новое удаленное управление звонками с помощью TCP-подключения, необходимо убедиться в том, что ограничения на <STRONG>Использование службы для выбранных IP-адресов</STRONG> должны быть установлены для существующих доверенных приложений и пулов, если вы хотите использовать один и тот же порт TCP для нового доверенного приложения.</span><span class="sxs-lookup"><span data-stu-id="89fcd-107">If you plan to deploy new remote call control by using a Transmission Control Protocol (TCP) connection, you need to verify that <STRONG>Limit service usage to selected IP addresses</STRONG> should be set on existing trusted applications and pools, if you want to use the same TCP port for the new trusted application.</span></span>



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a><span data-ttu-id="89fcd-108">Настройка записи доверенного приложения для шлюза SIP/CSTA</span><span class="sxs-lookup"><span data-stu-id="89fcd-108">To configure a trusted application entry for the SIP/CSTA gateway</span></span>

1.  <span data-ttu-id="89fcd-109">Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или роли управления доступом на основе ролей (RBAC), которой назначен командлет **New-кструстедаппликатионпул** .</span><span class="sxs-lookup"><span data-stu-id="89fcd-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsTrustedApplicationPool** cmdlet.</span></span>

2.  <span data-ttu-id="89fcd-110">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="89fcd-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="89fcd-111">Чтобы создать запись доверенного приложения, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="89fcd-111">To create a trusted application entry, do one of the following:</span></span>
    
      - <span data-ttu-id="89fcd-112">Для подключения по протоколу защиты транспортного уровня (TLS) введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89fcd-112">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="89fcd-113">Например:</span><span class="sxs-lookup"><span data-stu-id="89fcd-113">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - <span data-ttu-id="89fcd-114">Для подключения по протоколу управления передачей (TCP) введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89fcd-114">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="89fcd-115">Например:</span><span class="sxs-lookup"><span data-stu-id="89fcd-115">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  <span data-ttu-id="89fcd-116">Чтобы добавить доверенное приложение в пул, выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="89fcd-116">To add the trusted application to the pool, do one of the following:</span></span>
    
      - <span data-ttu-id="89fcd-117">Для подключения по протоколу TLS введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89fcd-117">For a TLS connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        <span data-ttu-id="89fcd-118">Например:</span><span class="sxs-lookup"><span data-stu-id="89fcd-118">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - <span data-ttu-id="89fcd-119">Для подключения по протоколу TCP введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89fcd-119">For a TCP connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        <span data-ttu-id="89fcd-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="89fcd-120">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  <span data-ttu-id="89fcd-121">Для реализации опубликованных изменений, внесенных в топологию, введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89fcd-121">To implement the published changes you have made to the topology, type the following at the command prompt:</span></span>
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="89fcd-122">См. также</span><span class="sxs-lookup"><span data-stu-id="89fcd-122">See Also</span></span>


[<span data-ttu-id="89fcd-123">Настройка статического маршрута для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89fcd-123">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="89fcd-124">Определение IP-адреса шлюза SIP/CSTA в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89fcd-124">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

