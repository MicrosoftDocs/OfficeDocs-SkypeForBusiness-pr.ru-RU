---
title: Управление конфигурацией пограничного сервера в организации
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После развертывания одного или нескольких пограничных серверов, необходимо включить типы внешнего домена или поставщик доступа, удаленного доступа пользователей и анонимный доступ пользователей к конференциям через пограничных серверов, который будет поддерживаться для вашей организации.
ms.openlocfilehash: 8428815a0f3d89124d1b5e681b79924171916f6d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896919"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="27bea-103">Управление конфигурацией пограничного сервера в организации</span><span class="sxs-lookup"><span data-stu-id="27bea-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="27bea-104">После развертывания одного или нескольких пограничных серверов, необходимо включить типы внешнего домена или поставщик доступа, удаленного доступа пользователей и анонимный доступ пользователей к конференциям через пограничных серверов, который будет поддерживаться для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="27bea-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="27bea-105">Эти параметры включают следующие типы доступа, которые можно настроить на странице **Настройка пограничного доступа** :</span><span class="sxs-lookup"><span data-stu-id="27bea-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="27bea-106">**Включить федерацию и общедоступные службы обмена Мгновенными сообщениями**   этого, если вы хотите обеспечить поддержку доступа пользователей к доменам федеративного партнера.</span><span class="sxs-lookup"><span data-stu-id="27bea-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="27bea-107">Этот параметр применяется к SIP федерации, настроенных для глобальной, сайта или пользователя областей действия на странице **Политика внешнего доступа** .</span><span class="sxs-lookup"><span data-stu-id="27bea-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="27bea-108">Для применения параметров федерации необходимо настроить поддержку федерации на обеих страницах.</span><span class="sxs-lookup"><span data-stu-id="27bea-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="27bea-109">Существует два варианта, которые являются необязательные параметры, как обнаружение федеративных партнеров и архивации заявления об отказе (уведомлений федеративным контактам, что вы общаетесь, развертывание имеет архивации включен и связи Подробные сведения, будут подвергаться архивации) будут отправляться контактам:</span><span class="sxs-lookup"><span data-stu-id="27bea-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="27bea-110">**Включить обнаружение доменов партнеров**   при выборе этого параметра включает автоматическое обнаружение доменов, с которыми возможна Федерация.</span><span class="sxs-lookup"><span data-stu-id="27bea-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="27bea-111">Скайп для Business Server использует записи доменных имен (DNS) в попытке обнаружение доменов, не указанные в списке разрешенных доменов автоматически оценка входящий трафик от обнаруженных федеративных партнеров и ограничения или блокировки, трафик на основании доверия уровень, объем трафика и параметры администрирования.</span><span class="sxs-lookup"><span data-stu-id="27bea-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="27bea-112">Если этот параметр не выбран, доступ федеративных пользователей будет доступна только для пользователей в доменах, которые можно включить в список разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="27bea-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="27bea-113">Ли этот параметр, можно указать, он доменов, заблокированных или разрешенных, включая ограничения доступа для конкретных серверах под управлением службы пограничного сервера доступа в федеративного домена.</span><span class="sxs-lookup"><span data-stu-id="27bea-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="27bea-114">Дополнительные сведения в статье [Configure поддержки для разрешенных внешних доменов](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="27bea-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="27bea-115">**Отправить от архивирования федеративным партнерам**   при выборе этого параметра включает отправку сообщения заявление об отказе для архивации федеративным партнерам, которые рекомендует, записываются, что сведения о связи.</span><span class="sxs-lookup"><span data-stu-id="27bea-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="27bea-116">Если архивировать внешние коммуникации с доменами федеративного партнера, следует включить архивации уведомлений заявление об отказе для предупреждения партнеров архивируются, что сведения о них сообщений и коммуникации с развертывания.</span><span class="sxs-lookup"><span data-stu-id="27bea-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="27bea-117">Для получения дополнительных сведений о сохранении видеть [Включение и отключение отправки заявления об отказе архивации для федеративного партнера](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="27bea-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="27bea-118">**Включение удаленного доступа пользователей**   включить этот параметр, если пользователи в вашей организации, находящихся за пределами брандмауэра, например путешествующих пользователей и пользователей, во время поездки, должны иметь возможность подключения к Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="27bea-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="27bea-119">Дополнительные сведения см [включения или отключения удаленного доступа пользователей](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="27bea-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="27bea-120">**Разрешить анонимным пользователям доступ к конференции**   включить этот параметр, внутренние пользователи приглашать внешних анонимных пользователей к конференциям, которые они организации.</span><span class="sxs-lookup"><span data-stu-id="27bea-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="27bea-121">Включение этого параметра разрешает только анонимных пользователей конференций.</span><span class="sxs-lookup"><span data-stu-id="27bea-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="27bea-122">Дополнение к разрешению доступа внешних пользователей поддержки, также конфигурация политик для управления использование удаленного доступа пользователей в вашей организации, перед любой тип доступа внешних пользователей доступен пользователям.</span><span class="sxs-lookup"><span data-stu-id="27bea-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="27bea-123">Для получения дополнительных сведений о создании, настройке и применение политик доступа внешних пользователей видеть [Управление политики внешнего доступа для вашей организации](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="27bea-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="27bea-124">**Просмотр сведений о конфигурации пограничного сервера доступа с помощью командлетов Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="27bea-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="27bea-125">Сведения о конфигурации пограничного доступа можно просматривать с помощью командлета **Get-CsAccessEdgeConfiguration** и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27bea-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="27bea-126">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="27bea-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="27bea-127">Чтобы просмотреть сведения обо всех параметрах конфигурации пограничного сервера доступа, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="27bea-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="27bea-128">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="27bea-128">That will return information similar to this:</span></span>
    
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

