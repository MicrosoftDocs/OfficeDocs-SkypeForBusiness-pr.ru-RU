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
ms.openlocfilehash: bfaec78b0c7d64308b5899a6e7dc5fa95c1f53fb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757873"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trusted-application-entry-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="994a9-102">Настройка записи доверенного приложения для удаленного управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="994a9-102">Configure a trusted application entry for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="994a9-103">_**Тема последнего изменения:** 2015-11-02_</span><span class="sxs-lookup"><span data-stu-id="994a9-103">_**Topic Last Modified:** 2015-11-02_</span></span>

<span data-ttu-id="994a9-104">Шлюз SIP/КСТА должен быть настроен как доверенное приложение, чтобы Lync Server может применять статический маршрут для маршрутизации звонков на шлюз.</span><span class="sxs-lookup"><span data-stu-id="994a9-104">The SIP/CSTA gateway must be configured as a trusted application in order for Lync Server to apply a static route to route calls to the gateway.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="994a9-105">Если вы переносите пользователей из предыдущей версии развертывания Lync Server, убедитесь, что вы удалили все существующие записи надежного приложения (ранее известные как авторизованные записи узла), созданные для шлюза SIP/КСТА, прежде чем выполнять действия, описанные в этой статье.</span><span class="sxs-lookup"><span data-stu-id="994a9-105">If you're migrating users from a previous version of Lync Server deployment, be sure that you removed all existing trusted application entries (previously known as authorized host entries) you created for the SIP/CSTA gateway before following the procedures in this topic.</span></span> <span data-ttu-id="994a9-106">Подробности можно найти <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">в разделе Удаление устаревшего авторизованного узла в Lync Server 2013 (необязательно)</A>.</span><span class="sxs-lookup"><span data-stu-id="994a9-106">For details, see <A href="lync-server-2013-remove-a-legacy-authorized-host-optional.md">Remove a legacy authorized host in Lync Server 2013 (optional)</A>.</span></span><BR><span data-ttu-id="994a9-107">Если вы планируете развертывать новое удаленное управление звонками с помощью протокола TCP, вам нужно подтвердить, что для существующих доверенных приложений и пулов нужно задать <STRONG>ограничение использования службы, чтобы</STRONG> использовать один и тот же порт TCP для нового надежного приложения.</span><span class="sxs-lookup"><span data-stu-id="994a9-107">If you plan to deploy new remote call control by using a Transmission Control Protocol (TCP) connection, you need to verify that <STRONG>Limit service usage to selected IP addresses</STRONG> should be set on existing trusted applications and pools, if you want to use the same TCP port for the new trusted application.</span></span>



</div>

<div>

## <a name="to-configure-a-trusted-application-entry-for-the-sipcsta-gateway"></a><span data-ttu-id="994a9-108">Настройка записи надежного приложения для шлюза SIP/КСТА</span><span class="sxs-lookup"><span data-stu-id="994a9-108">To configure a trusted application entry for the SIP/CSTA gateway</span></span>

1.  <span data-ttu-id="994a9-109">Войдите на компьютер, на котором установлена командная консоль Lync Server Management Shell, в группу Рткуниверсалсерверадминс или роль управления доступом на основе ролей (RBAC), для которой вы назначили командлет **New-кструстедаппликатионпул** .</span><span class="sxs-lookup"><span data-stu-id="994a9-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or a role-based access control (RBAC) role to which you have assigned the **New-CsTrustedApplicationPool** cmdlet.</span></span>

2.  <span data-ttu-id="994a9-110">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="994a9-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="994a9-111">Чтобы создать запись надежного приложения, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="994a9-111">To create a trusted application entry, do one of the following:</span></span>
    
      - <span data-ttu-id="994a9-112">Для подключения к протоколу TLS введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="994a9-112">For a Transport Layer Security (TLS) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="994a9-113">Например:</span><span class="sxs-lookup"><span data-stu-id="994a9-113">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity rccgateway.contoso.net -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true
    
      - <span data-ttu-id="994a9-114">Для подключения по протоколу TCP введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="994a9-114">For a Transmission Control Protocol (TCP) connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplicationPool -Identity <IP address or FQDN of the SIP/CSTA gateway> [-Registrar <Service ID or FQDN of the Registrar service>] -Site <Site ID for the site where you want to create the trusted application pool>
        
        <span data-ttu-id="994a9-115">Например:</span><span class="sxs-lookup"><span data-stu-id="994a9-115">For example:</span></span>
        
            New-CsTrustedApplicationPool -Identity 192.168.0.240 -Registrar registrar1.contoso.net -Site co1 -TreatAsAuthenticated $true -ThrottleAsServer $true

4.  <span data-ttu-id="994a9-116">Чтобы добавить в пул доверенное приложение, выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="994a9-116">To add the trusted application to the pool, do one of the following:</span></span>
    
      - <span data-ttu-id="994a9-117">Для подключения TLS введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="994a9-117">For a TLS connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway>
        
        <span data-ttu-id="994a9-118">Например:</span><span class="sxs-lookup"><span data-stu-id="994a9-118">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn rccgateway.contoso.net -Port 5065
    
      - <span data-ttu-id="994a9-119">Для подключения по протоколу TCP введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="994a9-119">For a TCP connection, type the following at the command prompt:</span></span>
        
            New-CsTrustedApplication -ApplicationID <application name> -TrustedApplicationPoolFqdn <IP address or FQDN of the SIP/CSTA gateway> -Port <SIP listening port on the gateway> -EnableTcp
        
        <span data-ttu-id="994a9-120">Например:</span><span class="sxs-lookup"><span data-stu-id="994a9-120">For example:</span></span>
        
            New-CsTrustedApplication -ApplicationID RccGateway-1 -TrustedApplicationPoolFqdn 192.169.0.240 -Port 5065 -EnableTcp

5.  <span data-ttu-id="994a9-121">Чтобы применить опубликованные изменения, внесенные в топологию, введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="994a9-121">To implement the published changes you have made to the topology, type the following at the command prompt:</span></span>
    
        Enable-CsTopology

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="994a9-122">См. также</span><span class="sxs-lookup"><span data-stu-id="994a9-122">See Also</span></span>


[<span data-ttu-id="994a9-123">Настройка статического маршрута для дистанционного управления вызовами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="994a9-123">Configure a static route for remote call control in Lync Server 2013</span></span>](lync-server-2013-configure-a-static-route-for-remote-call-control.md)  
[<span data-ttu-id="994a9-124">Определение IP-адреса для шлюза SIP/CSTA в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="994a9-124">Define a SIP/CSTA gateway IP address in Lync Server 2013</span></span>](lync-server-2013-define-a-sip-csta-gateway-ip-address.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

