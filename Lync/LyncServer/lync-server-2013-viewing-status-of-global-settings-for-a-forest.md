---
title: 'Lync Server 2013: Просмотр состояния глобальных параметров для леса'
description: 'Lync Server 2013: Просмотр состояния глобальных параметров для леса.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9f722ea66f6c54c816703bd1af1d3def57bbd84
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567595"
---
# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="d3108-103">Просмотр состояния глобальных параметров для леса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d3108-103">View status of global settings for a forest in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d3108-104">_**Последнее изменение темы:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="d3108-104">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="d3108-105">Администраторам ежемесячно просматривайте глобальные параметры развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3108-105">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="d3108-106">Цель — рассмотреть реализацию параметров для набора известных конфигураций — базовой конфигурации, чтобы гарантировать допустимость параметров и определить, следует ли обновлять базовую документацию.</span><span class="sxs-lookup"><span data-stu-id="d3108-106">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="d3108-107">Изменения в глобальном параметре должны быть реализованы с помощью процесса контроля изменений, который должен включать документирование новых параметров.</span><span class="sxs-lookup"><span data-stu-id="d3108-107">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="d3108-108">Глобальные параметры, которые следует проверить, описаны в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="d3108-108">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="d3108-109">Проверка общих параметров</span><span class="sxs-lookup"><span data-stu-id="d3108-109">Check general settings</span></span>

<span data-ttu-id="d3108-110">Проверьте общие параметры, в том числе поддерживаемые домены протокола SIP для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d3108-110">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="d3108-111">Сведения о домене SIP можно возвратить с помощью Windows PowerShell и командлета **Get – CsSipDomain** .</span><span class="sxs-lookup"><span data-stu-id="d3108-111">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="d3108-112">Чтобы получить эти сведения, выполните `Get-CsSipDomain` команду Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3108-112">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="d3108-113">Get-CsSipDomain будет возвращать сведения, аналогичные приведенным ниже, для всех авторизованных доменов SIP:</span><span class="sxs-lookup"><span data-stu-id="d3108-113">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="d3108-114">Имя удостоверения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="d3108-114">Identity Name IsDefault</span></span>

<span data-ttu-id="d3108-115">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="d3108-115">\-------- ---- ---------</span></span>

<span data-ttu-id="d3108-116">fabrikam.com fabrikam.com true</span><span class="sxs-lookup"><span data-stu-id="d3108-116">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="d3108-117">na.fabrikam.com na.fabrikam.com false</span><span class="sxs-lookup"><span data-stu-id="d3108-117">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="d3108-118">Если для свойства IsDefault задано значение true, соответствующий домен является доменом SIP по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d3108-118">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="d3108-119">Вы можете использовать командлет Set-CsSipDomain, чтобы изменить домен SIP по умолчанию для Организации.</span><span class="sxs-lookup"><span data-stu-id="d3108-119">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="d3108-120">Однако вы не можете просто удалить домен SIP по умолчанию, так как это приведет к тому, что вы не покинете домен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d3108-120">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="d3108-121">Если вы хотите удалить домен fabrikam.com (как показано в предыдущем примере), необходимо сначала настроить na.fabrikam.com в качестве домена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d3108-121">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="d3108-122">Проверка параметров собрания</span><span class="sxs-lookup"><span data-stu-id="d3108-122">Check meeting settings</span></span>

<span data-ttu-id="d3108-123">Параметры собраний включают определения политик собраний и поддержку для участия анонимных пользователей в собраниях.</span><span class="sxs-lookup"><span data-stu-id="d3108-123">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="d3108-124">Параметры конфигурации собраний можно получить с помощью Windows PowerShell и командлета **Get – CsMeetingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="d3108-124">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="d3108-125">Например, эта команда возвращает сведения о глобальных параметрах конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="d3108-125">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="d3108-126">Get-CsMeetingConfiguration — параметры конфигурации собрания "глобальные" также можно настроить на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="d3108-126">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="d3108-127">Поэтому можно использовать следующую команду, которая возвращает сведения обо всех параметрах конфигурации собраний:</span><span class="sxs-lookup"><span data-stu-id="d3108-127">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="d3108-128">Командлет **Get – CsMeetingConfiguration** возвращает сведения, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="d3108-128">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="d3108-129">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="d3108-129">Identity : Global</span></span>

<span data-ttu-id="d3108-130">Пстнкаллерсбипасслобби: true</span><span class="sxs-lookup"><span data-stu-id="d3108-130">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="d3108-131">Енаблеассигнедконференцетипе: true</span><span class="sxs-lookup"><span data-stu-id="d3108-131">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="d3108-132">Десигнатеаспресентер: Организация</span><span class="sxs-lookup"><span data-stu-id="d3108-132">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="d3108-133">Ассигнедконференцетипебидефаулт: true</span><span class="sxs-lookup"><span data-stu-id="d3108-133">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="d3108-134">Адмитанонимаусусерсбидефаулт: true</span><span class="sxs-lookup"><span data-stu-id="d3108-134">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="d3108-135">Опять же, конечный элемент в списке, **адмитанонимаусусерсбидефаулт**, включает или отключает возможность анонимным пользователям участвовать в собраниях.</span><span class="sxs-lookup"><span data-stu-id="d3108-135">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="d3108-136">При проверке параметров конфигурации собраний может оказаться целесообразным сравнить текущие параметры с эквивалентами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d3108-136">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="d3108-137">Параметры конфигурации собраний по умолчанию можно просмотреть, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d3108-137">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="d3108-138">Предыдущая команда создает в памяти экземпляр глобальных параметров конфигурации собраний, экземпляр которого использует значение по умолчанию для каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="d3108-138">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="d3108-139">При выполнении команды не создаются фактические параметры конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="d3108-139">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="d3108-140">Однако все значения свойств по умолчанию будут отображаться на экране.</span><span class="sxs-lookup"><span data-stu-id="d3108-140">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="d3108-141">Проверка пограничных серверов и их параметров</span><span class="sxs-lookup"><span data-stu-id="d3108-141">Check Edge Servers and their settings</span></span>

<span data-ttu-id="d3108-142">Сведения о пограничных серверах можно получить с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3108-142">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="d3108-143">Эта команда возвращает сведения о всех пограничных серверах, настроенных для использования в Организации.</span><span class="sxs-lookup"><span data-stu-id="d3108-143">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="d3108-144">Возвращаемые сведения включают все параметры полного доменного имени и порта для каждого пограничного сервера:</span><span class="sxs-lookup"><span data-stu-id="d3108-144">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="d3108-145">Identity: EdgeServer: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d3108-145">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="d3108-146">Регистратор: регистратор: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d3108-146">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="d3108-147">Акцесседжеинтерналсиппорт: 5061</span><span class="sxs-lookup"><span data-stu-id="d3108-147">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="d3108-148">Акцесседжеекстерналсиппорт: 5061</span><span class="sxs-lookup"><span data-stu-id="d3108-148">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="d3108-149">Акцесседжеклиентпорт: 443</span><span class="sxs-lookup"><span data-stu-id="d3108-149">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="d3108-150">Датапсомсерверпорт: 8057</span><span class="sxs-lookup"><span data-stu-id="d3108-150">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="d3108-151">Датапсомклиентпорт: 444</span><span class="sxs-lookup"><span data-stu-id="d3108-151">DataPsomClientPort : 444</span></span>

<span data-ttu-id="d3108-152">Медиарелайауседжепорт: 5062</span><span class="sxs-lookup"><span data-stu-id="d3108-152">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="d3108-153">Медиарелайаусинтерналтурнткппорт: 443</span><span class="sxs-lookup"><span data-stu-id="d3108-153">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="d3108-154">Медиарелайаусекстерналтурнткппорт: 445</span><span class="sxs-lookup"><span data-stu-id="d3108-154">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="d3108-155">Медиарелайаусинтерналтурнудппорт: 3478</span><span class="sxs-lookup"><span data-stu-id="d3108-155">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="d3108-156">Медиарелайаусекстерналтурнудппорт: 3478</span><span class="sxs-lookup"><span data-stu-id="d3108-156">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="d3108-157">Медиакоммуникатионпортстарт: 50000</span><span class="sxs-lookup"><span data-stu-id="d3108-157">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="d3108-158">Медиакомуникатионпорткаунт: 10000</span><span class="sxs-lookup"><span data-stu-id="d3108-158">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="d3108-159">Акцесседжеекстерналфкдн: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d3108-159">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="d3108-160">Датаеджеекстерналфкдн: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d3108-160">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="d3108-161">Аведжеекстерналфкдн:</span><span class="sxs-lookup"><span data-stu-id="d3108-161">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="d3108-162">Интерналинтерфацефкдн:</span><span class="sxs-lookup"><span data-stu-id="d3108-162">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="d3108-163">Екстерналмрасфкдн: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d3108-163">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="d3108-164">Депендентсервицелист: {регистратор: LYNC — SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="d3108-164">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="d3108-165">КонференЦингсервер: LYNC – SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="d3108-165">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="d3108-166">com, MediationServer: LYNC-SE.</span><span class="sxs-lookup"><span data-stu-id="d3108-166">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="d3108-167">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="d3108-167">fabrikam.com}</span></span>

<span data-ttu-id="d3108-168">ServiceId: fabrikam.com — EdgeServer – 2</span><span class="sxs-lookup"><span data-stu-id="d3108-168">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="d3108-169">Идентификатор сайта: site:фабрикам. com</span><span class="sxs-lookup"><span data-stu-id="d3108-169">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="d3108-170">PoolFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="d3108-170">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="d3108-171">Версия: 5</span><span class="sxs-lookup"><span data-stu-id="d3108-171">Version : 5</span></span>

<span data-ttu-id="d3108-172">Роль: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="d3108-172">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="d3108-173">Проверка параметров Федерации</span><span class="sxs-lookup"><span data-stu-id="d3108-173">Check federation settings</span></span>

<span data-ttu-id="d3108-174">Проверьте параметры Федерации, например, настроены ли они, и, если ответ имеет значение "Да", полное доменное имя и порт.</span><span class="sxs-lookup"><span data-stu-id="d3108-174">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="d3108-175">Федерация включена и отключена с помощью глобальной коллекции параметров конфигурации пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="d3108-175">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="d3108-176">Помимо прочего, это означает, что Федерация настраивается на уровне "все или ничего": Любая Федерация включена для всей организации или Федерация отключена для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="d3108-176">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="d3108-177">Параметры конфигурации пограничного сервера доступа можно вернуть с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3108-177">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="d3108-178">Для этого выполните следующую команду Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d3108-178">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="d3108-179">В свою очередь эта команда возвратит данные, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="d3108-179">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="d3108-180">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="d3108-180">Identity : Global</span></span>

<span data-ttu-id="d3108-181">AllowAnonymousUsers: false</span><span class="sxs-lookup"><span data-stu-id="d3108-181">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="d3108-182">AllowFederatedUsers: false</span><span class="sxs-lookup"><span data-stu-id="d3108-182">AllowFederatedUsers : False</span></span>

<span data-ttu-id="d3108-183">AllowOutsideUsers: false</span><span class="sxs-lookup"><span data-stu-id="d3108-183">AllowOutsideUsers : False</span></span>

<span data-ttu-id="d3108-184">Беклеарингхаусе: false</span><span class="sxs-lookup"><span data-stu-id="d3108-184">BeClearingHouse : False</span></span>

<span data-ttu-id="d3108-185">EnablePartnerDiscovery: false</span><span class="sxs-lookup"><span data-stu-id="d3108-185">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="d3108-186">EnableArchivingDisclaimer: false</span><span class="sxs-lookup"><span data-stu-id="d3108-186">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="d3108-187">Кипкрлсуптодатефорпирс: true</span><span class="sxs-lookup"><span data-stu-id="d3108-187">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="d3108-188">Марксаурцеверифиаблеонаутгоингмессажес: true</span><span class="sxs-lookup"><span data-stu-id="d3108-188">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="d3108-189">Аутгоингтлскаунтфорфедератедпартнерс: 4</span><span class="sxs-lookup"><span data-stu-id="d3108-189">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="d3108-190">Раутингмесод: UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="d3108-190">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="d3108-191">Если для свойства **AllowFederatedUsers** задано значение true, это означает, что для организации включена Федерация.</span><span class="sxs-lookup"><span data-stu-id="d3108-191">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="d3108-192">(Установка **AllowFederatedUsers** в true также означает, что в случае с разделенным доменом ваши локальные пользователи смогут легко общаться с пользователями в облаке.)</span><span class="sxs-lookup"><span data-stu-id="d3108-192">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="d3108-193">Чтобы получить полное доменное имя и параметры порта для пограничного сервера, просмотрите предыдущую задачу (пограничные серверы и их параметры).</span><span class="sxs-lookup"><span data-stu-id="d3108-193">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="d3108-194">Включение Федерации в глобальной области означает, что пользователи потенциально могут общаться с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="d3108-194">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="d3108-195">Чтобы определить, могут ли какие либо отдельные пользователи в действительности общаться с федеративными пользователями, необходимо проверить политику доступа внешних пользователей, назначенную этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="d3108-195">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="d3108-196">Сведения о доступе внешних пользователей можно вернуть с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3108-196">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="d3108-197">Например, эта команда возвращает сведения о глобальной политике доступа внешних пользователей:</span><span class="sxs-lookup"><span data-stu-id="d3108-197">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="d3108-198">Эта команда возвращает сведения обо всех политиках доступа внешних пользователей:</span><span class="sxs-lookup"><span data-stu-id="d3108-198">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="d3108-199">Возвращаемые сведения будут выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d3108-199">The returned information will resemble this:</span></span>

<span data-ttu-id="d3108-200">Identity: false</span><span class="sxs-lookup"><span data-stu-id="d3108-200">Identity : False</span></span>

<span data-ttu-id="d3108-201">Обзор</span><span class="sxs-lookup"><span data-stu-id="d3108-201">Description :</span></span>

<span data-ttu-id="d3108-202">EnableFederationAccess: false</span><span class="sxs-lookup"><span data-stu-id="d3108-202">EnableFederationAccess : False</span></span>

<span data-ttu-id="d3108-203">Свойство enablepubliccloudaccess: false</span><span class="sxs-lookup"><span data-stu-id="d3108-203">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="d3108-204">Енаблепубликклаудакцессаудиовидеоакцесс: false</span><span class="sxs-lookup"><span data-stu-id="d3108-204">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="d3108-205">Енаблеаутсидеакцесс: false</span><span class="sxs-lookup"><span data-stu-id="d3108-205">EnableOutsideAccess : False</span></span>

<span data-ttu-id="d3108-206">Если для **EnableFederationAccess** задано значение true, пользователи, управляемые заданной политикой, могут общаться с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="d3108-206">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="d3108-207">Проверка параметров архивации</span><span class="sxs-lookup"><span data-stu-id="d3108-207">Check archiving settings</span></span>

<span data-ttu-id="d3108-208">Проверьте параметры архивации для внутренних и Федеративных коммуникаций. Перед проверкой параметров для внутреннего и внешнего архивации необходимо убедиться, что функция архивации включена.</span><span class="sxs-lookup"><span data-stu-id="d3108-208">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="d3108-209">Параметры конфигурации архивации можно проверить с помощью Windows PowerShell и командлета Get-CsArchivingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="d3108-209">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="d3108-210">Обратите внимание, что параметры архивации можно также настроить в области сайта.</span><span class="sxs-lookup"><span data-stu-id="d3108-210">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="d3108-211">Чтобы получить сведения о всех параметрах архивации, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d3108-211">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="d3108-212">Командлет Get-CsArchivingConfiguration возвращает данные, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="d3108-212">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="d3108-213">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="d3108-213">Identity : Global</span></span>

<span data-ttu-id="d3108-214">Енаблеарчивинг: false</span><span class="sxs-lookup"><span data-stu-id="d3108-214">EnableArchiving : False</span></span>

<span data-ttu-id="d3108-215">EnablePurging: false</span><span class="sxs-lookup"><span data-stu-id="d3108-215">EnablePurging : False</span></span>

<span data-ttu-id="d3108-216">Пуржеекспортедарчивесонли: false</span><span class="sxs-lookup"><span data-stu-id="d3108-216">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="d3108-217">Блокконарчивефаилуре: false</span><span class="sxs-lookup"><span data-stu-id="d3108-217">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="d3108-218">KeepArchivingDataForDays: 14</span><span class="sxs-lookup"><span data-stu-id="d3108-218">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="d3108-219">Пуржехаурофдай: 2</span><span class="sxs-lookup"><span data-stu-id="d3108-219">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="d3108-220">Арчиведупликатемессажес: true</span><span class="sxs-lookup"><span data-stu-id="d3108-220">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="d3108-221">Качепургингинтервал: 24</span><span class="sxs-lookup"><span data-stu-id="d3108-221">CachePurgingInterval : 24</span></span>

<span data-ttu-id="d3108-222">Если для свойства Енаблеарчивинг задано значение false, сеансы связи не будут архивироваться.</span><span class="sxs-lookup"><span data-stu-id="d3108-222">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="d3108-223">Если вы хотите архивировать только сеансы обмена мгновенными сообщениями, используйте команду, аналогичную приведенной ниже, чтобы включить архивацию сеансов обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="d3108-223">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="d3108-224">Чтобы архивировать сеансы конференц-связи и сеансы обмена мгновенными сообщениями, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d3108-224">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="d3108-225">Если вы хотите сравнить текущие параметры архивации с параметрами по умолчанию, выполните следующую команду Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d3108-225">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="d3108-226">Эта команда создает в памяти экземпляр глобальных параметров конфигурации архивации.</span><span class="sxs-lookup"><span data-stu-id="d3108-226">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="d3108-227">Это не реальный набор параметров, используемых Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3108-227">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="d3108-228">Однако в нем отображаются значения по умолчанию для всех свойств конфигурации архивации.</span><span class="sxs-lookup"><span data-stu-id="d3108-228">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="d3108-229">Кроме того, с помощью этой команды можно получить полное доменное имя серверов архивации:</span><span class="sxs-lookup"><span data-stu-id="d3108-229">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="d3108-230">После проверки того, включена ли архивация, вы можете просмотреть политики архивации, чтобы определить, архивируются ли внутренние и внешние сеансы связи.</span><span class="sxs-lookup"><span data-stu-id="d3108-230">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="d3108-231">Сведения о политике архивации можно получить с помощью командлета Get-CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="d3108-231">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="d3108-232">Например, эта команда возвращает сведения о глобальной политике архивации:</span><span class="sxs-lookup"><span data-stu-id="d3108-232">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="d3108-233">Так как политики архивации также можно настроить на уровне сайта и на уровне пользователя, можно использовать эту команду, которая возвращает сведения обо всех политиках архивации:</span><span class="sxs-lookup"><span data-stu-id="d3108-233">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="d3108-234">Информация, получаемая из Get-CsArchivingPolicy, будет выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="d3108-234">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="d3108-235">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="d3108-235">Identity : Global</span></span>

<span data-ttu-id="d3108-236">Обзор</span><span class="sxs-lookup"><span data-stu-id="d3108-236">Description :</span></span>

<span data-ttu-id="d3108-237">Присвойте параметрам archiveinternal: false</span><span class="sxs-lookup"><span data-stu-id="d3108-237">ArchiveInternal : False</span></span>

<span data-ttu-id="d3108-238">ArchiveExternal: false</span><span class="sxs-lookup"><span data-stu-id="d3108-238">ArchiveExternal : False</span></span>

<span data-ttu-id="d3108-239">Обратите внимание, что по умолчанию внутренняя и внешняя Архивация отключены в политике архивирования.</span><span class="sxs-lookup"><span data-stu-id="d3108-239">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="d3108-240">Проверка параметров CDR</span><span class="sxs-lookup"><span data-stu-id="d3108-240">Check CDR settings</span></span>

<span data-ttu-id="d3108-241">Проверьте параметры записи сведений о вызовах (CDR) для записи одноранговой сети, конференц-связи и записи сведений о голосовых вызовах.</span><span class="sxs-lookup"><span data-stu-id="d3108-241">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="d3108-242">Подробные сведения о параметрах CDR можно возвратить с помощью командлета **Get – CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="d3108-242">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="d3108-243">Например, эта команда возвращает сведения о глобальной коллекции параметров конфигурации CDR:</span><span class="sxs-lookup"><span data-stu-id="d3108-243">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="d3108-244">Так как CDR можно также настроить на уровне сайта, можно также выполнить эту команду, которая возвращает сведения обо всех параметрах конфигурации CDR:</span><span class="sxs-lookup"><span data-stu-id="d3108-244">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="d3108-245">Командлет Get-CsCdrConfiguration возвращает сведения, аналогичные приведенным ниже, для каждой коллекции параметров конфигурации CDR:</span><span class="sxs-lookup"><span data-stu-id="d3108-245">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="d3108-246">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="d3108-246">Identity : Global</span></span>

<span data-ttu-id="d3108-247">EnableCDR: true</span><span class="sxs-lookup"><span data-stu-id="d3108-247">EnableCDR : True</span></span>

<span data-ttu-id="d3108-248">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="d3108-248">EnablePurging : True</span></span>

<span data-ttu-id="d3108-249">Кипкаллдетаилфордайс: 60</span><span class="sxs-lookup"><span data-stu-id="d3108-249">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="d3108-250">Киперроррепортфордайс: 60</span><span class="sxs-lookup"><span data-stu-id="d3108-250">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="d3108-251">Пуржехаурофдай: 2</span><span class="sxs-lookup"><span data-stu-id="d3108-251">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="d3108-252">Аналогичные сведения можно возвратить для мониторинга QoE с помощью командлета Get-CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="d3108-252">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="d3108-253">Например, эта команда возвращает сведения о глобальной коллекции параметров конфигурации QoE:</span><span class="sxs-lookup"><span data-stu-id="d3108-253">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="d3108-254">Эти сведения будут выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="d3108-254">That information will resemble this:</span></span>

<span data-ttu-id="d3108-255">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="d3108-255">Identity : Global</span></span>

<span data-ttu-id="d3108-256">Екстерналконсумериссуедцертид:</span><span class="sxs-lookup"><span data-stu-id="d3108-256">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="d3108-257">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="d3108-257">EnablePurging : True</span></span>

<span data-ttu-id="d3108-258">KeepQoEDataForDays: 60</span><span class="sxs-lookup"><span data-stu-id="d3108-258">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="d3108-259">Пуржехаурофдай: 1</span><span class="sxs-lookup"><span data-stu-id="d3108-259">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="d3108-260">Енабликстерналконсумер: false</span><span class="sxs-lookup"><span data-stu-id="d3108-260">EnableExternalConsumer : False</span></span>

<span data-ttu-id="d3108-261">Екстерналконсумернаме:</span><span class="sxs-lookup"><span data-stu-id="d3108-261">ExternalConsumerName :</span></span>

<span data-ttu-id="d3108-262">Екстерналконсумерурл:</span><span class="sxs-lookup"><span data-stu-id="d3108-262">ExternalConsumerURL :</span></span>

<span data-ttu-id="d3108-263">EnableQoE: true</span><span class="sxs-lookup"><span data-stu-id="d3108-263">EnableQoE : True</span></span>

<span data-ttu-id="d3108-264">Если вы хотите сравнить текущие параметры CDR с параметрами CDR по умолчанию, можно проверить значения по умолчанию, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d3108-264">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="d3108-265">Аналогично, значения по умолчанию для мониторинга QoE можно получить с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="d3108-265">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="d3108-266">Вы также можете вернуть полное доменное имя серверов мониторинга, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d3108-266">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="d3108-267">Проверка параметров голосовой связи</span><span class="sxs-lookup"><span data-stu-id="d3108-267">Check voice settings</span></span>

<span data-ttu-id="d3108-268">Параметры голосовой связи, как правило, важны для администраторов в политиках голосовой связи и голосовых маршрутах: политики голосовой связи содержат параметры, определяющие возможности, предоставляемые отдельным пользователям (например, возможность пересылки или передачи), а маршруты голосовой связи определяют маршрутизацию вызовов по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="d3108-268">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="d3108-269">Сведения о политике голосовой связи можно получить с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3108-269">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="d3108-270">Например, эта команда возвращает сведения о глобальной политике голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="d3108-270">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="d3108-271">Эта команда возвращает сведения обо всех политиках голосовой связи, настроенных для использования в Организации.</span><span class="sxs-lookup"><span data-stu-id="d3108-271">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="d3108-272">Информация, возвращаемая командлетом Get-CsVoicePolicy, выглядит следующим образом:</span><span class="sxs-lookup"><span data-stu-id="d3108-272">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="d3108-273">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="d3108-273">Identity : Global</span></span>

<span data-ttu-id="d3108-274">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="d3108-274">PstnUsages : {}</span></span>

<span data-ttu-id="d3108-275">Обзор</span><span class="sxs-lookup"><span data-stu-id="d3108-275">Description :</span></span>

<span data-ttu-id="d3108-276">Алловсимулринг: true</span><span class="sxs-lookup"><span data-stu-id="d3108-276">AllowSimulRing : True</span></span>

<span data-ttu-id="d3108-277">Алловкаллфорвардинг: true</span><span class="sxs-lookup"><span data-stu-id="d3108-277">AllowCallForwarding : True</span></span>

<span data-ttu-id="d3108-278">Алловпстнрераутинг: true</span><span class="sxs-lookup"><span data-stu-id="d3108-278">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="d3108-279">Name: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="d3108-279">Name : DefaultPolicy</span></span>

<span data-ttu-id="d3108-280">Енабледелегатион: true</span><span class="sxs-lookup"><span data-stu-id="d3108-280">EnableDelegation : True</span></span>

<span data-ttu-id="d3108-281">Енаблетеамкалл: true</span><span class="sxs-lookup"><span data-stu-id="d3108-281">EnableTeamCall : True</span></span>

<span data-ttu-id="d3108-282">Енаблекаллтрансфер: true</span><span class="sxs-lookup"><span data-stu-id="d3108-282">EnableCallTransfer : True</span></span>

<span data-ttu-id="d3108-283">Enablecallpark задано: false</span><span class="sxs-lookup"><span data-stu-id="d3108-283">EnableCallPark : False</span></span>

<span data-ttu-id="d3108-284">ЕнаблемалиЦиаускаллтраЦинг: false</span><span class="sxs-lookup"><span data-stu-id="d3108-284">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="d3108-285">Енаблебвполициоверриде: false</span><span class="sxs-lookup"><span data-stu-id="d3108-285">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="d3108-286">Превентпстнтоллбипасс: false</span><span class="sxs-lookup"><span data-stu-id="d3108-286">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="d3108-287">Кроме того, можно создавать запросы, которые возвращают подмножество политик голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="d3108-287">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="d3108-288">Например, эта команда возвращает все политики голосовой связи, которые допускают переадресацию вызовов:</span><span class="sxs-lookup"><span data-stu-id="d3108-288">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="d3108-289">Эта команда возвращает все политики голосовой связи, которые не допускают переадресацию вызовов:</span><span class="sxs-lookup"><span data-stu-id="d3108-289">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="d3108-290">В Windows PowerShell используйте командлет Get-CsVoiceRouting, чтобы получить сведения о маршрутах голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="d3108-290">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="d3108-291">Эта команда возвращает такие сведения, как, например, для всех маршрутов голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="d3108-291">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="d3108-292">Identity: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="d3108-292">Identity : LocalRoute</span></span>

<span data-ttu-id="d3108-293">Приоритет: 0</span><span class="sxs-lookup"><span data-stu-id="d3108-293">Priority : 0</span></span>

<span data-ttu-id="d3108-294">Обзор</span><span class="sxs-lookup"><span data-stu-id="d3108-294">Description :</span></span>

<span data-ttu-id="d3108-295">Нумберпаттерн: ^ ( \\ + 1 \[ 0-9 \] {10} ) $</span><span class="sxs-lookup"><span data-stu-id="d3108-295">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="d3108-296">PstnUsages {}</span><span class="sxs-lookup"><span data-stu-id="d3108-296">PstnUsages : {}</span></span>

<span data-ttu-id="d3108-297">Пстнгатевайлист: {}</span><span class="sxs-lookup"><span data-stu-id="d3108-297">PstnGatewayList : {}</span></span>

<span data-ttu-id="d3108-298">Name: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="d3108-298">Name : LocalRoute</span></span>

<span data-ttu-id="d3108-299">Суппресскаллерид:</span><span class="sxs-lookup"><span data-stu-id="d3108-299">SuppressCallerId :</span></span>

<span data-ttu-id="d3108-300">AlternateCallerId</span><span class="sxs-lookup"><span data-stu-id="d3108-300">AlternateCallerId :</span></span>

<span data-ttu-id="d3108-301">Lync Server позволяет создавать маршруты голосовой связи, для которых не используется PSTN, и не указывать шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="d3108-301">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="d3108-302">Однако вы не можете направлять вызовы через маршрут голосовой связи, для которого не настроены эти два значения свойств.</span><span class="sxs-lookup"><span data-stu-id="d3108-302">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="d3108-303">Из-за этого может оказаться полезной возможность периодически запускать эту команду, которая возвращает идентификатор маршрута голосовой связи, для которого не используется PSTN:</span><span class="sxs-lookup"><span data-stu-id="d3108-303">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="d3108-304">Аналогично, эта команда возвращает идентификатор маршрута голосовой связи, для которого не настроен шлюз PSTN:</span><span class="sxs-lookup"><span data-stu-id="d3108-304">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="d3108-305">Проверка параметров помощника по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="d3108-305">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="d3108-306">Проверьте параметры помощника для конференц-связи с телефонным подключением PSTN.</span><span class="sxs-lookup"><span data-stu-id="d3108-306">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="d3108-307">Параметры помощника по конференц-связи можно получить только с помощью командлета **Get-CsDialInConferencingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="d3108-307">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="d3108-308">Эти параметры недоступны в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d3108-308">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="d3108-309">Чтобы просмотреть параметры помощника по конференц-связи, используйте команду Windows PowerShell, аналогичную приведенной ниже, которая возвращает глобальную коллекцию параметров помощника по конференц-связи:</span><span class="sxs-lookup"><span data-stu-id="d3108-309">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="d3108-310">Обратите внимание на то, что параметры помощника по конференц-связи также можно настроить в области сайта.</span><span class="sxs-lookup"><span data-stu-id="d3108-310">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="d3108-311">Чтобы получить сведения обо всех параметрах помощника по конференц-связи, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="d3108-311">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="d3108-312">Командлет Get-CsDialInConferencingConfiguration возвращает данные, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="d3108-312">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="d3108-313">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="d3108-313">Identity : Global</span></span>

<span data-ttu-id="d3108-314">Ентрекситаннаунцементстипе: Усенамес</span><span class="sxs-lookup"><span data-stu-id="d3108-314">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="d3108-315">Енабленамерекординг: true</span><span class="sxs-lookup"><span data-stu-id="d3108-315">EnableNameRecording : True</span></span>

<span data-ttu-id="d3108-316">Ентрекситаннаунцементсенабледбидефаулт: false</span><span class="sxs-lookup"><span data-stu-id="d3108-316">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="d3108-317">Если для Ентрекситаннаунцементсенабледбидефаулт задано значение false, объявления конференций отключены.</span><span class="sxs-lookup"><span data-stu-id="d3108-317">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="d3108-318">Чтобы включить объявления входа и выхода, выполните следующую команду Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d3108-318">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d3108-319">См. также</span><span class="sxs-lookup"><span data-stu-id="d3108-319">See Also</span></span>


[<span data-ttu-id="d3108-320">Get — CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="d3108-320">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="d3108-321">Get — CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d3108-321">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="d3108-322">Get — CsService</span><span class="sxs-lookup"><span data-stu-id="d3108-322">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="d3108-323">Get — CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="d3108-323">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="d3108-324">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="d3108-324">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="d3108-325">Get — CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d3108-325">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="d3108-326">Get — CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="d3108-326">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="d3108-327">Get — CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="d3108-327">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="d3108-328">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="d3108-328">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="d3108-329">Get — Ксвоицерауте</span><span class="sxs-lookup"><span data-stu-id="d3108-329">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="d3108-330">Get — CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="d3108-330">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

