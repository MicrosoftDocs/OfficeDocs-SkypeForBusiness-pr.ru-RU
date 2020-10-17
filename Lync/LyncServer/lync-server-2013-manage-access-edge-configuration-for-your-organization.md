---
title: 'Lync Server 2013: Управление конфигурацией пограничного сервера для Организации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c62e5b03057f09d7489a413456e432e8e08799b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534556"
---
# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="a1e59-102">Управление конфигурацией пограничного сервера доступа для Организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e59-102">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1e59-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a1e59-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a1e59-104">Это Предварительная документация, которая может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="a1e59-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="a1e59-105">Пустые разделы включены в качестве заполнителей.</span><span class="sxs-lookup"><span data-stu-id="a1e59-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="a1e59-106">После развертывания одного или нескольких пограничных серверов необходимо включить типы доступа к внешним доменам или поставщикам, удаленный доступ пользователей и анонимный доступ пользователей к конференциям через пограничные серверы, которые будут поддерживаться в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a1e59-106">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="a1e59-107">Ниже перечислены типы доступа, которые можно настроить на странице **Настройка пограничного доступа**:</span><span class="sxs-lookup"><span data-stu-id="a1e59-107">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="a1e59-108">**Включение Федерации и общедоступной службы**     обмена мгновенными сообщениями Включите этот параметр, если требуется поддержка доступа пользователей к доменам федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="a1e59-108">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="a1e59-109">Это значение применяется и к федерациям SIP, и к федерациям XMPP, настроенным на глобальном уровне, уровне площадки или пользовательском уровне на странице**Политика внешнего доступа**.</span><span class="sxs-lookup"><span data-stu-id="a1e59-109">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="a1e59-110">Для применения параметров федераций необходимо настроить поддержку федераций на обеих страницах.</span><span class="sxs-lookup"><span data-stu-id="a1e59-110">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="a1e59-111">Следующие два необязательных параметра позволят определить способ обнаружения федеративных партнеров и то, будут ли отправляться контактам уведомления об архивации (уведомление федеративных контактов о том, что во время взаимодействия с вашей стороны включена архивация и ход взаимодействия будет архивироваться).</span><span class="sxs-lookup"><span data-stu-id="a1e59-111">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="a1e59-112">**Включение обнаружения**     доменных партнеров При выборе этого параметра включается автоматическое обнаружение доменов, с которыми вы можете создать федерацию.</span><span class="sxs-lookup"><span data-stu-id="a1e59-112">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="a1e59-113">Lync Server 2013 использует записи службы доменных имен (DNS) для обнаружения доменов, не указанных в списке разрешенных доменов, автоматически оценивая входящий трафик от обнаруженных федеративных партнеров и ограничивая или блокирующая трафик на основе уровня доверия, объема трафика и параметров администратора.</span><span class="sxs-lookup"><span data-stu-id="a1e59-113">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="a1e59-114">Если этот параметр не выбран, доступ будет разрешен только для федеративных пользователей из доменов, включенных в список разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="a1e59-114">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="a1e59-115">Независимо от выбора этого параметра можно указать отдельные домены, которые будут заблокированы или разрешены, включая ограничение доступа к конкретным серверам пограничной службы доступа в федеративном домене.</span><span class="sxs-lookup"><span data-stu-id="a1e59-115">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="a1e59-116">Подробнее: [Настройка поддержки для разрешенных внешних доменов в Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="a1e59-116">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="a1e59-117">**Отправка заявления об отказе от архивации федеративным партнерам**     При выборе этого параметра включается Отправка сообщения об отказе от архивации федеративным партнерам, которые сообщают им о том, что сведения о связи записываются.</span><span class="sxs-lookup"><span data-stu-id="a1e59-117">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="a1e59-118">При архивировании внешних взаимодействий с доменами федеративных партнеров следует включить уведомление об архивации, чтобы предупредить партнеров о том, что их сообщения и сведения о взаимодействии с ними будут архивироваться в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="a1e59-118">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="a1e59-119">Подробные сведения о архивации можно найти [в статье Определение требований к архивации в Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="a1e59-119">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="a1e59-120">**Включение удаленного доступа пользователей**     Включите этот параметр, если вы хотите, чтобы пользователи из вашей организации, находящиеся за преправителями, например для пользователей, которые находятся в дороге, могли подключиться к Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a1e59-120">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="a1e59-121">Дополнительные сведения см. [в статье Включение или отключение удаленного доступа пользователей в Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="a1e59-121">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="a1e59-122">**Разрешение доступа анонимных пользователей к конференциям**     Включите этот параметр, если вы хотите, чтобы внутренние пользователи пригласили внешних анонимных пользователей на Конференции, которые они упорядочивают.</span><span class="sxs-lookup"><span data-stu-id="a1e59-122">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="a1e59-123">Включение этого параметра только разрешает анонимным пользователям участвовать в конференциях.</span><span class="sxs-lookup"><span data-stu-id="a1e59-123">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="a1e59-124">Чтобы настроить интерфейс и параметры конференц-связи, которые определяют, как и как пользователи могут выполнять конференции, а также для включения анонимных пользователей, ознакомьтесь со статьей сведения о [создании или изменении интерфейса Конференц-](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) связи для сайтов, пользователей и [параметров политики конференц-связи для Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="a1e59-124">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a1e59-125">Кроме поддержки разрешения доступа внешних пользователей, прежде чем внешним пользователям станет доступен любой тип доступа, также нужно настроить политики управления.</span><span class="sxs-lookup"><span data-stu-id="a1e59-125">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="a1e59-126">Сведения о создании, настройке и применении политик для доступа внешних пользователей приведены <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">в статье Manage External Access Policy in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="a1e59-126">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="a1e59-127">**Просмотр сведений о конфигурации пограничного доступа с помощью командлетов Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="a1e59-127">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="a1e59-128">Сведения о конфигурации пограничного сервера доступа можно просмотреть с помощью Windows PowerShell и командлета **Get – CsAccessEdgeConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="a1e59-128">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="a1e59-129">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a1e59-129">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="a1e59-130">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="a1e59-130">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="a1e59-131">Чтобы просмотреть сведения обо всех параметрах конфигурации пограничного сервера доступа, введите следующую команду в командной консоли Lync Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="a1e59-131">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="a1e59-132">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="a1e59-132">That will return information similar to this:</span></span>
    
        Identity                               : Global
        AllowAnonymousUsers                    : False
        AllowFederatedUsers                    : False
        AllowOutsideUsers                      : True
        BeClearingHouse                        : False
        EnablePartnerDiscovery                 : False
        EnableArchivingDisclaimer              : False
        EnableUserReplicator                   : True
        KeepCrlsUpToDateForPeers               : True
        MarkSourceVerifiableOnOutgoingMessages : True
        OutgoingTlsCountForFederatedPartners   : 4
        DiscoveredPartnerStandardRate          : 20
        EnableDiscoveredPartnerContactsLimit   : True
        MaxContactsPerDiscoveredPartner        : 1000
        DiscoveredPartnerReportPeriodMinutes   : 60
        MaxAcceptedCertificatesStored          : 1000
        MaxRejectedCertificatesStored          : 500
        CertificatesDeletedPercentage          : 20
        RoutingMethod                          : UseDnsSrvRouting

<div>

## <a name="in-this-section"></a><span data-ttu-id="a1e59-133">Содержание</span><span class="sxs-lookup"><span data-stu-id="a1e59-133">In This Section</span></span>

  - [<span data-ttu-id="a1e59-134">Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e59-134">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="a1e59-135">Включение и отключение обнаружения партнеров Федерации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e59-135">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="a1e59-136">Включение или отключение отправки заявления об отказе от архивации федеративным партнерам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e59-136">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="a1e59-137">Включение или отключение доступа удаленных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e59-137">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="a1e59-138">Включение или отключение анонимного доступа пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e59-138">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="a1e59-139">Назначение политик конференц-связи для поддержки анонимных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a1e59-139">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

