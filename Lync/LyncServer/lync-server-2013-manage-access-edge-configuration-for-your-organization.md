---
title: 'Lync Server 2013: управление конфигурацией пограничного сервера в организации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage Access Edge Configuration for your organization
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05d2bcca7836bd451b2535fb02c350facd7fc1bf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-access-edge-configuration-for-your-organization-in-lync-server-2013"></a><span data-ttu-id="85a0c-102">Управление конфигурацией пограничного сервера в организации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85a0c-102">Manage Access Edge Configuration for your organization in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="85a0c-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="85a0c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="85a0c-104">Это предварительная редакция документации и она может меняться.</span><span class="sxs-lookup"><span data-stu-id="85a0c-104">This is preliminary documentation and is subject to change.</span></span> <span data-ttu-id="85a0c-105">Пустые разделы добавлены в качестве заполнителей.</span><span class="sxs-lookup"><span data-stu-id="85a0c-105">Blank topics are included as placeholders.</span></span>

<span data-ttu-id="85a0c-106">После развертывания одного или нескольких пограничных серверов необходимо разрешить типы доступа к внешнему домену или поставщику, получить доступ к удаленному пользователю, а также анонимный доступ пользователей к конференциям с помощью пограничных серверов, которые будут поддерживаться в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="85a0c-106">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="85a0c-107">Эти параметры включают следующие типы доступа, которые можно настроить на странице **конфигурации пограничного доступа** .</span><span class="sxs-lookup"><span data-stu-id="85a0c-107">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="85a0c-108">**Включите возможность подключения**   к службам федерации и общедоступного обмена мгновенными сообщениями, если вы хотите поддерживать доступ пользователей к доменам федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="85a0c-108">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="85a0c-109">Этот параметр применяется к обеим федерациям SIP и КСМПП Федерации, настроенным для глобальных областей, сайтов или пользователей на странице **политики внешней доступа** .</span><span class="sxs-lookup"><span data-stu-id="85a0c-109">This setting applies to both SIP federation and XMPP federation that are configured for global, site or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="85a0c-110">Для применения параметров Федерации необходимо настроить поддержку Федерации на обеих страницах.</span><span class="sxs-lookup"><span data-stu-id="85a0c-110">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="85a0c-111">Существует два варианта, которые являются необязательными параметрами, определяющими способ обнаружения федеративных партнеров, и необходимость архивации (уведомление для федеративных контактов, с которыми вы обмениваетесь данными), для которых включена Архивация и связь данные будут заархивированы) будут отправлены в контакты</span><span class="sxs-lookup"><span data-stu-id="85a0c-111">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts</span></span>
    
      - <span data-ttu-id="85a0c-112">**Включить функцию обнаружения**   доменных партнеров. Выбор этого параметра позволяет автоматически обнаруживать домены, с которыми вы можете выполнять Федерацию.</span><span class="sxs-lookup"><span data-stu-id="85a0c-112">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="85a0c-113">Lync Server 2013 использует записи DNS для обнаружения доменов, не указанных в списке разрешенных доменов, автоматически оценивает входящий трафик от обнаруженных федеративных партнеров и ограничивает или блокирует трафик на основе уровня доверия. объем трафика и параметры администратора.</span><span class="sxs-lookup"><span data-stu-id="85a0c-113">Lync Server 2013 uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="85a0c-114">Если этот флажок не установлен, для пользователей из доменов, включенных в список разрешенных доменов, будет разрешен доступ федеративного пользователя.</span><span class="sxs-lookup"><span data-stu-id="85a0c-114">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="85a0c-115">Если вы выберете этот параметр, вы можете указать, что отдельные домены должны быть заблокированы или разрешены, включая ограничение доступа к определенным серверам, на которых запущена служба EDGE в федеративных доменах.</span><span class="sxs-lookup"><span data-stu-id="85a0c-115">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="85a0c-116">Подробности можно найти [в разделе Настройка поддержки разрешенных внешних доменов в Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span><span class="sxs-lookup"><span data-stu-id="85a0c-116">For details, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).</span></span>
    
      - <span data-ttu-id="85a0c-117">**Отправить заявление**   об отказе от работы федеративным партнерам если выбрать этот параметр, вы можете отправлять сообщения об отказе на архивацию федеративным партнерам, которые сообщают им о том, что данные о связи записываются.</span><span class="sxs-lookup"><span data-stu-id="85a0c-117">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="85a0c-118">При архивации внешней связи с доменами федеративных партнеров следует включить уведомление об отказе в архивации, чтобы предупредить партнеров о том, что их сообщения и сведения о общении заархивированы вашим развертыванием.</span><span class="sxs-lookup"><span data-stu-id="85a0c-118">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="85a0c-119">Подробнее об архивации можно найти [в разделе Определение требований для архивации в Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span><span class="sxs-lookup"><span data-stu-id="85a0c-119">For details on archiving, see [Defining your requirements for Archiving in Lync Server 2013](lync-server-2013-defining-your-requirements-for-archiving.md).</span></span>

  - <span data-ttu-id="85a0c-120">**Разрешите удаленным пользователям**   предоставлять этот параметр, если вы хотите, чтобы пользователи в вашей организации, которые находятся за пределами вашего брандмауэра, например абоненты удаленного доступа, и пользователи, которые находятся в дороге, смогли подключиться к серверу Lync Server.</span><span class="sxs-lookup"><span data-stu-id="85a0c-120">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Lync Server.</span></span> <span data-ttu-id="85a0c-121">Дополнительные сведения можно найти [в разделе Включение и отключение удаленного доступа пользователей в Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="85a0c-121">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="85a0c-122">**Включение доступа анонимных пользователей**   к конференциям включите этот параметр, если вы хотите, чтобы внутренние пользователи могли пригласить внешних анонимных пользователей на Конференции, которые они упорядочивают.</span><span class="sxs-lookup"><span data-stu-id="85a0c-122">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="85a0c-123">Если этот параметр включен, анонимные пользователи не могут быть подключены к Конференции.</span><span class="sxs-lookup"><span data-stu-id="85a0c-123">Enabling this setting only allows anonymous users for conferences.</span></span> <span data-ttu-id="85a0c-124">Чтобы настроить возможности конференц-связи и параметры, определяющие способ и возможности пользователей с конференциями и включение анонимных пользователей, ознакомьтесь со сведениями по [созданию и изменению взаимодействия с пользователями для сайтов и пользователей](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\)) и [ Справочник по параметрам политики конференций в Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span><span class="sxs-lookup"><span data-stu-id="85a0c-124">To configure the conferencing experience and options that will define how and what your users can do with conferences and for the inclusion of anonymous users, see details at [Create or Modify Conferencing User Experience for a Site or Users](https://technet.microsoft.com/en-us/library/gg429715\(v=ocs.15\)) and [Conferencing policy settings reference for Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="85a0c-125">Помимо включения поддержки внешних пользователей, вы также можете настроить политики для управления использованием удаленного доступа пользователей в Организации, прежде чем пользователи смогут получить доступ к любому типу внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="85a0c-125">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="85a0c-126">Дополнительные сведения о создании и настройке политик доступа внешних пользователей см. <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">в разделе Управление политикой внешнего доступа в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="85a0c-126">For details about creating, configuring, and applying policies for external user access, see <A href="lync-server-2013-manage-external-access-policy-for-your-organization.md">Manage external access policy in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="85a0c-127">**Просмотр сведений о конфигурации Edge для Access с помощью командлетов Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="85a0c-127">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="85a0c-128">Сведения о конфигурации Edge Access можно просмотреть с помощью Windows PowerShell и командлета **Get-ксакцесседжеконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="85a0c-128">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="85a0c-129">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85a0c-129">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="85a0c-130">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="85a0c-130">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="85a0c-131">Чтобы просмотреть сведения о всех параметрах конфигурации Edge Access, введите в командной консоли Lync Server указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="85a0c-131">To view information about all your Access Edge configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsAccessEdgeConfiguration
    
    <span data-ttu-id="85a0c-132">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="85a0c-132">That will return information similar to this:</span></span>
    
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

## <a name="in-this-section"></a><span data-ttu-id="85a0c-133">Содержание</span><span class="sxs-lookup"><span data-stu-id="85a0c-133">In This Section</span></span>

  - [<span data-ttu-id="85a0c-134">Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85a0c-134">Enable or disable federation and public IM connectivity in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)

  - [<span data-ttu-id="85a0c-135">Включение или отключение обнаружения федеративных партнеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85a0c-135">Enable or disable discovery of federation partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md)

  - [<span data-ttu-id="85a0c-136">Включение и отключение отправки отказа от архивирования федеративным партнерам в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85a0c-136">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)

  - [<span data-ttu-id="85a0c-137">Включение или отключения удаленного доступа пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85a0c-137">Enable or disable remote user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-remote-user-access.md)

  - [<span data-ttu-id="85a0c-138">Включение или отключение анонимного доступа пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85a0c-138">Enable or disable anonymous user access in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-anonymous-user-access.md)

  - [<span data-ttu-id="85a0c-139">Назначение политик конференции для поддержки анонимных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="85a0c-139">Assign conferencing policies to support anonymous users in Lync Server 2013</span></span>](lync-server-2013-assign-conferencing-policies-to-support-anonymous-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

