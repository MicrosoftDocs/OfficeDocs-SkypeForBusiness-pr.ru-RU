---
title: Управление конфигурацией пограничного сервера в организации
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: После развертывания одного или более серверов необходимо включить типы доступа внешних доменов или поставщиков, удаленный доступ пользователей и анонимный доступ пользователей к конференциям через серверы, которые будут поддерживаться в вашей организации.
ms.openlocfilehash: 63d33a5dd3459aef5f657d8ab5772515a16e7915
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817339"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="06e3d-103">Управление конфигурацией пограничного сервера в организации</span><span class="sxs-lookup"><span data-stu-id="06e3d-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="06e3d-104">После развертывания одного или более серверов необходимо включить типы доступа внешних доменов или поставщиков, удаленный доступ пользователей и анонимный доступ пользователей к конференциям через серверы, которые будут поддерживаться в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="06e3d-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="06e3d-105">Ниже перечислены типы доступа, которые можно настроить на странице **Настройка пограничного доступа**:</span><span class="sxs-lookup"><span data-stu-id="06e3d-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="06e3d-106">**Включить федерацию и подключение к общедоступным системам im**   В этом случае вы хотите поддерживать доступ пользователей к федератным доменам партнеров.</span><span class="sxs-lookup"><span data-stu-id="06e3d-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="06e3d-107">Этот параметр применяется к федерации SIP, настроенной для глобальных областей сайта или пользователей на странице "Политика **внешнего** доступа".</span><span class="sxs-lookup"><span data-stu-id="06e3d-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="06e3d-108">Для применения параметров федераций необходимо настроить поддержку федераций на обеих страницах.</span><span class="sxs-lookup"><span data-stu-id="06e3d-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="06e3d-109">Существуют два параметра, которые являются необязательными настройками для обнаружения федеративных партнеров и для передачи контактам уведомлений об отказе от архивации (уведомление федеративным контактам о том, что в развертывании включена архивная архива и архивированы ли сведения о связи):</span><span class="sxs-lookup"><span data-stu-id="06e3d-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="06e3d-110">**Включить обнаружение доменов партнеров**   Выбор этого параметра позволяет автоматически обнаруживать домены, с которые можно вести федератерию.</span><span class="sxs-lookup"><span data-stu-id="06e3d-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="06e3d-111">Skype для бизнеса Server использует записи системы доменных имен (DNS) для обнаружения доменов, не указанных в списке разрешенных доменов, автоматически оценивая входящий трафик от обнаруженных федераированных партнеров и ограничив или блокируя этот трафик на основе уровня доверия, объема трафика и параметров администратора.</span><span class="sxs-lookup"><span data-stu-id="06e3d-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="06e3d-112">Если этот параметр не выбран, доступ будет разрешен только для федеративных пользователей из доменов, включенных в список разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="06e3d-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="06e3d-113">Независимо от выбора этого параметра можно указать отдельные домены, которые будут заблокированы или разрешены, включая ограничение доступа к конкретным серверам пограничной службы доступа в федеративном домене.</span><span class="sxs-lookup"><span data-stu-id="06e3d-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="06e3d-114">Подробные сведения см. в подстройке "Настройка [поддержки разрешенных внешних доменов".](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="06e3d-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="06e3d-115">**Отправка федеративным партнерам**   заявление об отказе от архива   Выбор этого параметра позволяет отправлять федеративным партнерам сообщение об отказе от архива, которое сообщает им о записи сведений.</span><span class="sxs-lookup"><span data-stu-id="06e3d-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="06e3d-116">При архивировании внешних взаимодействий с доменами федеративных партнеров следует включить уведомление об архивации, чтобы предупредить партнеров о том, что их сообщения и сведения о взаимодействии с ними будут архивироваться в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="06e3d-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="06e3d-117">Дополнительные сведения об архивировании см. в подтипе ["Enable or disable sending an Archiving disclaimer to federated partner "Enable or disable sending an Archiving disclaimer to federated partner".](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md)</span><span class="sxs-lookup"><span data-stu-id="06e3d-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="06e3d-118">**Включить доступ удаленных пользователей**   Включении этого параметра необходимо, чтобы пользователи в вашей организации, которые находятся за пределами брандмауэра, такие как телекоммуникационные метры и пользователи, которые находятся в командировке, могли подключаться к Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="06e3d-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="06e3d-119">Подробные сведения см. в сведениях о [включаемом или отключаемом удаленном доступе пользователей.](enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="06e3d-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="06e3d-120">**Доступ анонимных пользователей к конференциям**   В этом случае внутренние пользователи будут приглашать внешних анонимных пользователей на конференции, которые они организовывают.</span><span class="sxs-lookup"><span data-stu-id="06e3d-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="06e3d-121">Включение этого параметра только разрешает анонимным пользователям участвовать в конференциях.</span><span class="sxs-lookup"><span data-stu-id="06e3d-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="06e3d-122">Кроме поддержки разрешения доступа внешних пользователей, прежде чем внешним пользователям станет доступен любой тип доступа, также нужно настроить политики управления.</span><span class="sxs-lookup"><span data-stu-id="06e3d-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="06e3d-123">Дополнительные сведения о создании, настройке и применении политик доступа внешних пользователей см. в политике управления внешним [доступом для организации.](../external-access-policies/manage-external-access-policy-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="06e3d-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="06e3d-124">**Просмотр сведений о конфигурации edge доступа с помощью Windows PowerShell управления**</span><span class="sxs-lookup"><span data-stu-id="06e3d-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="06e3d-125">Сведения о конфигурации edge доступа можно просмотреть с помощью Windows PowerShell и с помощью Windows PowerShell **Get-CsAccessEdgeConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="06e3d-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="06e3d-126">Этот cmdlet можно запустить либо из оболочки управления Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="06e3d-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="06e3d-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span><span class="sxs-lookup"><span data-stu-id="06e3d-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="06e3d-128">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="06e3d-128">That will return information similar to this:</span></span>
    
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

