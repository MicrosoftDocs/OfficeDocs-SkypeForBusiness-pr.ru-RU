---
title: Управление конфигурацией пограничного сервера в организации
ms.reviewer: ''
ms:assetid: 0145eb08-984f-4ecd-bf9c-364817619c2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552443(v=OCS.15)
ms:contentKeyID: 48679555
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: После развертывания одного или нескольких пограничных серверов необходимо разрешить типы доступа к внешнему домену или поставщику, получить доступ к удаленному пользователю, а также анонимный доступ пользователей к конференциям с помощью пограничных серверов, которые будут поддерживаться в вашей организации.
ms.openlocfilehash: b79560d2cb0e570ab2b4fcf061a5b91c6a74a8bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280196"
---
# <a name="manage-access-edge-configuration-for-your-organization"></a><span data-ttu-id="dc598-103">Управление конфигурацией пограничного сервера в организации</span><span class="sxs-lookup"><span data-stu-id="dc598-103">Manage Access Edge Configuration for your organization</span></span>

<span data-ttu-id="dc598-104">После развертывания одного или нескольких пограничных серверов необходимо разрешить типы доступа к внешнему домену или поставщику, получить доступ к удаленному пользователю, а также анонимный доступ пользователей к конференциям с помощью пограничных серверов, которые будут поддерживаться в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="dc598-104">After deploying one or more Edge Servers, you must enable the types of external domain or provider access, remote user access, and anonymous user access to conferences through the Edge Servers that will be supported for your organization.</span></span>

<span data-ttu-id="dc598-105">Эти параметры включают следующие типы доступа, которые можно настроить на странице **конфигурации пограничного доступа** .</span><span class="sxs-lookup"><span data-stu-id="dc598-105">These options include the following types of access that can be configured through the **Access Edge Configuration** page:</span></span>

  - <span data-ttu-id="dc598-106">**Включите возможность подключения**   к службам федерации и общедоступного обмена мгновенными сообщениями, если вы хотите поддерживать доступ пользователей к доменам федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="dc598-106">**Enable federation and public IM connectivity**   Enable this if you want to support user access to federated partner domains.</span></span> <span data-ttu-id="dc598-107">Этот параметр применяется к Федерации SIP, настроенному для глобальных областей, сайтов или пользователей на странице **политики внешней доступа** .</span><span class="sxs-lookup"><span data-stu-id="dc598-107">This setting applies to SIP federation configured for global, site, or user scopes on the **External Access Policy** page.</span></span> <span data-ttu-id="dc598-108">Для применения параметров Федерации необходимо настроить поддержку Федерации на обеих страницах.</span><span class="sxs-lookup"><span data-stu-id="dc598-108">For federation settings to apply, you must configure federation support on both pages.</span></span>
    
    <span data-ttu-id="dc598-109">Существует два варианта, которые являются необязательными параметрами, определяющими способ обнаружения федеративных партнеров, и необходимость архивации (уведомление для федеративных контактов, с которыми вы обмениваетесь данными), для которых включена Архивация и связь данные будут заархивированы) будут отправлены в список контактов:</span><span class="sxs-lookup"><span data-stu-id="dc598-109">Two options exist that are optional settings for how federated partners are discovered, and whether archiving disclaimers (notification to federated contacts that you communicate with that your deployment has archiving enabled and that the communications details will be archived) will be sent to contacts:</span></span>
    
      - <span data-ttu-id="dc598-110">**Включить функцию обнаружения**   доменных партнеров. Выбор этого параметра позволяет автоматически обнаруживать домены, с которыми вы можете выполнять Федерацию.</span><span class="sxs-lookup"><span data-stu-id="dc598-110">**Enable partner domain discovery**   Selecting this option enables the automatic discovery of domains that you can federate with.</span></span> <span data-ttu-id="dc598-111">Skype для бизнеса Server использует записи DNS для обнаружения доменов, не указанных в списке разрешенные домены, автоматически оценивает входящий трафик от обнаруженных федеративных партнеров и ограничивает или блокирует трафик на основе доверительных отношений. уровень, объем трафика и параметры администратора.</span><span class="sxs-lookup"><span data-stu-id="dc598-111">Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="dc598-112">Если этот флажок не установлен, для пользователей из доменов, включенных в список разрешенных доменов, будет разрешен доступ федеративного пользователя.</span><span class="sxs-lookup"><span data-stu-id="dc598-112">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="dc598-113">Если вы выберете этот параметр, вы можете указать, что отдельные домены должны быть заблокированы или разрешены, включая ограничение доступа к определенным серверам, на которых запущена служба EDGE в федеративных доменах.</span><span class="sxs-lookup"><span data-stu-id="dc598-113">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="dc598-114">Подробности можно найти в разделе [Настройка поддержки для разрешенных внешних доменов](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span><span class="sxs-lookup"><span data-stu-id="dc598-114">For details, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>
    
      - <span data-ttu-id="dc598-115">**Отправить заявление**   об отказе от работы федеративным партнерам если выбрать этот параметр, вы можете отправлять сообщения об отказе на архивацию федеративным партнерам, которые сообщают им о том, что данные о связи записываются.</span><span class="sxs-lookup"><span data-stu-id="dc598-115">**Send archiving disclaimer to federated partners**   Selecting this option enables the sending of an archiving disclaimer message to federated partners that advises them that communications details are recorded.</span></span> <span data-ttu-id="dc598-116">При архивации внешней связи с доменами федеративных партнеров следует включить уведомление об отказе в архивации, чтобы предупредить партнеров о том, что их сообщения и сведения о общении заархивированы вашим развертыванием.</span><span class="sxs-lookup"><span data-stu-id="dc598-116">If you archive external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages and communications details are being archived by your deployment.</span></span> <span data-ttu-id="dc598-117">Подробнее об архивации можно найти в разделе [Включение и отключение отправки сообщений об отказе в архивы для федеративного партнера](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span><span class="sxs-lookup"><span data-stu-id="dc598-117">For details on archiving, see [Enable or disable sending an Archiving disclaimer to federated partner](enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners.md).</span></span>

  - <span data-ttu-id="dc598-118">**Разрешите удаленным пользователям**   предоставлять этот параметр, если вы хотите, чтобы пользователи в вашей организации, которые находятся за пределами брандмауэра, такие как удаленные пользователи и проходящие абоненты, смогли подключиться к Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="dc598-118">**Enable remote user access**   Enable this option if you want users in your organization who are outside your firewall, such as telecommuters and users who are traveling, to be able to connect to Skype for Business Server.</span></span> <span data-ttu-id="dc598-119">Подробности можно найти в разделе [Включение и отключение удаленного доступа пользователей](enable-or-disable-remote-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="dc598-119">For details, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

  - <span data-ttu-id="dc598-120">**Включение доступа анонимных пользователей**   к конференциям включите этот параметр, если вы хотите, чтобы внутренние пользователи могли пригласить внешних анонимных пользователей на Конференции, которые они упорядочивают.</span><span class="sxs-lookup"><span data-stu-id="dc598-120">**Enable anonymous users to access conferences**   Enable this option if you want internal users to invite external anonymous users to conferences that they organize.</span></span> <span data-ttu-id="dc598-121">Если этот параметр включен, анонимные пользователи не могут быть подключены к Конференции.</span><span class="sxs-lookup"><span data-stu-id="dc598-121">Enabling this setting only allows anonymous users for conferences.</span></span>

> [!NOTE]  
> <span data-ttu-id="dc598-122">Помимо включения поддержки внешних пользователей, вы также можете настроить политики для управления использованием удаленного доступа пользователей в Организации, прежде чем пользователи смогут получить доступ к любому типу внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="dc598-122">In addition to enabling external user access support, you also configure policies to control the use of remote user access in your organization before any type of external user access is available to users.</span></span> <span data-ttu-id="dc598-123">Дополнительные сведения о создании и настройке политик доступа внешних пользователей см. в разделе [Управление политикой внешнего доступа для вашей организации](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="dc598-123">For details about creating, configuring, and applying policies for external user access, see [Manage external access policy for your organization](../external-access-policies/manage-external-access-policy-for-your-organization.md).</span></span>

<span data-ttu-id="dc598-124">**Просмотр сведений о конфигурации Edge для Access с помощью командлетов Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="dc598-124">**Viewing Access Edge configuration information by using Windows PowerShell cmdlets**</span></span>

  - <span data-ttu-id="dc598-125">Сведения о конфигурации Edge Access можно просмотреть с помощью Windows PowerShell и командлета **Get-ксакцесседжеконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="dc598-125">Access Edge configuration information can be viewed by using Windows PowerShell and the **Get-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="dc598-126">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dc598-126">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 
    
    <span data-ttu-id="dc598-127">Чтобы просмотреть сведения о всех параметрах конфигурации пограничного доступа, введите в командной консоли Skype для Business Server следующую команду и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="dc598-127">To view information about all your Access Edge configuration settings, type the following command in the Skype for Business Server Management Shell and then press ENTER:</span></span>
    
     `Get-CsAccessEdgeConfiguration`
    
    <span data-ttu-id="dc598-128">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="dc598-128">That will return information similar to this:</span></span>
    
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

