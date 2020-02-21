---
title: 'Lync Server 2013: Просмотр состояния глобальных параметров для леса'
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
ms.openlocfilehash: ab574067b05b494601e0dd769003cb01904c52bc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211108"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="9a6d0-102">Просмотр состояния глобальных параметров для леса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9a6d0-102">View status of global settings for a forest in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a6d0-103">_**Последнее изменение темы:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="9a6d0-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="9a6d0-104">Администраторам ежемесячно просматривайте глобальные параметры развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="9a6d0-105">Цель — рассмотреть реализацию параметров для набора известных конфигураций — базовой конфигурации, чтобы гарантировать допустимость параметров и определить, следует ли обновлять базовую документацию.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="9a6d0-106">Изменения в глобальном параметре должны быть реализованы с помощью процесса контроля изменений, который должен включать документирование новых параметров.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="9a6d0-107">Глобальные параметры, которые следует проверить, описаны в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="9a6d0-108">Проверка общих параметров</span><span class="sxs-lookup"><span data-stu-id="9a6d0-108">Check general settings</span></span>

<span data-ttu-id="9a6d0-109">Проверьте общие параметры, в том числе поддерживаемые домены протокола SIP для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="9a6d0-110">Сведения о домене SIP можно возвратить с помощью Windows PowerShell и командлета **Get – CsSipDomain** .</span><span class="sxs-lookup"><span data-stu-id="9a6d0-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="9a6d0-111">Чтобы получить эти сведения, выполните команду `Get-CsSipDomain` Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="9a6d0-112">Get – CsSipDomain возвратит сведения, аналогичные приведенным ниже, для всех авторизованных доменов SIP:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="9a6d0-113">Имя удостоверения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="9a6d0-113">Identity Name IsDefault</span></span>

<span data-ttu-id="9a6d0-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="9a6d0-114">\-------- ---- ---------</span></span>

<span data-ttu-id="9a6d0-115">fabrikam.com fabrikam.com true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="9a6d0-116">na.fabrikam.com na.fabrikam.com false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="9a6d0-117">Если для свойства IsDefault задано значение true, соответствующий домен является доменом SIP по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="9a6d0-118">Командлет Set – CsSipDomain можно использовать для изменения домена SIP по умолчанию для Организации.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="9a6d0-119">Однако вы не можете просто удалить домен SIP по умолчанию, так как это приведет к тому, что вы не покинете домен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="9a6d0-120">Если вы хотите удалить домен fabrikam.com (как показано в предыдущем примере), необходимо сначала настроить na.fabrikam.com в качестве домена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="9a6d0-121">Проверка параметров собрания</span><span class="sxs-lookup"><span data-stu-id="9a6d0-121">Check meeting settings</span></span>

<span data-ttu-id="9a6d0-122">Параметры собраний включают определения политик собраний и поддержку для участия анонимных пользователей в собраниях.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="9a6d0-123">Параметры конфигурации собраний можно получить с помощью Windows PowerShell и командлета **Get – CsMeetingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9a6d0-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="9a6d0-124">Например, эта команда возвращает сведения о глобальных параметрах конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="9a6d0-125">Параметры конфигурации собрания Get-CsMeetingConfiguration – Identity "Global" также можно настроить на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="9a6d0-126">Поэтому можно использовать следующую команду, которая возвращает сведения обо всех параметрах конфигурации собраний:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="9a6d0-127">Командлет **Get – CsMeetingConfiguration** возвращает сведения, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="9a6d0-128">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9a6d0-128">Identity : Global</span></span>

<span data-ttu-id="9a6d0-129">Пстнкаллерсбипасслобби: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="9a6d0-130">Енаблеассигнедконференцетипе: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="9a6d0-131">Десигнатеаспресентер: Организация</span><span class="sxs-lookup"><span data-stu-id="9a6d0-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="9a6d0-132">Ассигнедконференцетипебидефаулт: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="9a6d0-133">Адмитанонимаусусерсбидефаулт: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="9a6d0-134">Опять же, конечный элемент в списке, **адмитанонимаусусерсбидефаулт**, включает или отключает возможность анонимным пользователям участвовать в собраниях.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="9a6d0-135">При проверке параметров конфигурации собраний может оказаться целесообразным сравнить текущие параметры с эквивалентами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="9a6d0-136">Параметры конфигурации собраний по умолчанию можно просмотреть, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="9a6d0-137">Предыдущая команда создает в памяти экземпляр глобальных параметров конфигурации собраний, экземпляр которого использует значение по умолчанию для каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="9a6d0-138">При выполнении команды не создаются фактические параметры конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="9a6d0-139">Однако все значения свойств по умолчанию будут отображаться на экране.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="9a6d0-140">Проверка пограничных серверов и их параметров</span><span class="sxs-lookup"><span data-stu-id="9a6d0-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="9a6d0-141">Сведения о пограничных серверах можно получить с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="9a6d0-142">Эта команда возвращает сведения о всех пограничных серверах, настроенных для использования в Организации.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="9a6d0-143">Возвращаемые сведения включают все параметры полного доменного имени и порта для каждого пограничного сервера:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="9a6d0-144">Identity: EdgeServer: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9a6d0-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="9a6d0-145">Регистратор: регистратор: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9a6d0-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="9a6d0-146">Акцесседжеинтерналсиппорт: 5061</span><span class="sxs-lookup"><span data-stu-id="9a6d0-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="9a6d0-147">Акцесседжеекстерналсиппорт: 5061</span><span class="sxs-lookup"><span data-stu-id="9a6d0-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="9a6d0-148">Акцесседжеклиентпорт: 443</span><span class="sxs-lookup"><span data-stu-id="9a6d0-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="9a6d0-149">Датапсомсерверпорт: 8057</span><span class="sxs-lookup"><span data-stu-id="9a6d0-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="9a6d0-150">Датапсомклиентпорт: 444</span><span class="sxs-lookup"><span data-stu-id="9a6d0-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="9a6d0-151">Медиарелайауседжепорт: 5062</span><span class="sxs-lookup"><span data-stu-id="9a6d0-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="9a6d0-152">Медиарелайаусинтерналтурнткппорт: 443</span><span class="sxs-lookup"><span data-stu-id="9a6d0-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="9a6d0-153">Медиарелайаусекстерналтурнткппорт: 445</span><span class="sxs-lookup"><span data-stu-id="9a6d0-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="9a6d0-154">Медиарелайаусинтерналтурнудппорт: 3478</span><span class="sxs-lookup"><span data-stu-id="9a6d0-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="9a6d0-155">Медиарелайаусекстерналтурнудппорт: 3478</span><span class="sxs-lookup"><span data-stu-id="9a6d0-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="9a6d0-156">Медиакоммуникатионпортстарт: 50000</span><span class="sxs-lookup"><span data-stu-id="9a6d0-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="9a6d0-157">Медиакомуникатионпорткаунт: 10000</span><span class="sxs-lookup"><span data-stu-id="9a6d0-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="9a6d0-158">Акцесседжеекстерналфкдн: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9a6d0-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="9a6d0-159">Датаеджеекстерналфкдн: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9a6d0-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="9a6d0-160">Аведжеекстерналфкдн:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="9a6d0-161">Интерналинтерфацефкдн:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="9a6d0-162">Екстерналмрасфкдн: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9a6d0-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="9a6d0-163">Депендентсервицелист: {регистратор: LYNC — SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="9a6d0-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="9a6d0-164">КонференЦингсервер: LYNC – SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="9a6d0-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="9a6d0-165">com, MediationServer: LYNC-SE.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="9a6d0-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="9a6d0-166">fabrikam.com}</span></span>

<span data-ttu-id="9a6d0-167">ServiceId: fabrikam.com — EdgeServer – 2</span><span class="sxs-lookup"><span data-stu-id="9a6d0-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="9a6d0-168">Идентификатор сайта: site:фабрикам. com</span><span class="sxs-lookup"><span data-stu-id="9a6d0-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="9a6d0-169">PoolFqdn: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="9a6d0-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="9a6d0-170">Версия: 5</span><span class="sxs-lookup"><span data-stu-id="9a6d0-170">Version : 5</span></span>

<span data-ttu-id="9a6d0-171">Роль: EdgeServer</span><span class="sxs-lookup"><span data-stu-id="9a6d0-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="9a6d0-172">Проверка параметров Федерации</span><span class="sxs-lookup"><span data-stu-id="9a6d0-172">Check federation settings</span></span>

<span data-ttu-id="9a6d0-173">Проверьте параметры Федерации, например, настроены ли они, и, если ответ имеет значение "Да", полное доменное имя и порт.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="9a6d0-174">Федерация включена и отключена с помощью глобальной коллекции параметров конфигурации пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="9a6d0-175">Помимо прочего, это означает, что Федерация настраивается на уровне "все или ничего": Любая Федерация включена для всей организации или Федерация отключена для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="9a6d0-176">Параметры конфигурации пограничного сервера доступа можно вернуть с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="9a6d0-177">Для этого выполните следующую команду Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="9a6d0-178">В свою очередь эта команда возвратит данные, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="9a6d0-179">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9a6d0-179">Identity : Global</span></span>

<span data-ttu-id="9a6d0-180">AllowAnonymousUsers: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="9a6d0-181">AllowFederatedUsers: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="9a6d0-182">AllowOutsideUsers: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="9a6d0-183">Беклеарингхаусе: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-183">BeClearingHouse : False</span></span>

<span data-ttu-id="9a6d0-184">EnablePartnerDiscovery: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="9a6d0-185">EnableArchivingDisclaimer: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="9a6d0-186">Кипкрлсуптодатефорпирс: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="9a6d0-187">Марксаурцеверифиаблеонаутгоингмессажес: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="9a6d0-188">Аутгоингтлскаунтфорфедератедпартнерс: 4</span><span class="sxs-lookup"><span data-stu-id="9a6d0-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="9a6d0-189">Раутингмесод: UseDnsSrvRouting</span><span class="sxs-lookup"><span data-stu-id="9a6d0-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="9a6d0-190">Если для свойства **AllowFederatedUsers** задано значение true, это означает, что для организации включена Федерация.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="9a6d0-191">(Установка **AllowFederatedUsers** в true также означает, что в случае с разделенным доменом ваши локальные пользователи смогут легко общаться с пользователями в облаке.)</span><span class="sxs-lookup"><span data-stu-id="9a6d0-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="9a6d0-192">Чтобы получить полное доменное имя и параметры порта для пограничного сервера, просмотрите предыдущую задачу (пограничные серверы и их параметры).</span><span class="sxs-lookup"><span data-stu-id="9a6d0-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="9a6d0-193">Включение Федерации в глобальной области означает, что пользователи потенциально могут общаться с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="9a6d0-194">Чтобы определить, могут ли какие либо отдельные пользователи в действительности общаться с федеративными пользователями, необходимо проверить политику доступа внешних пользователей, назначенную этому пользователю.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="9a6d0-195">Сведения о доступе внешних пользователей можно вернуть с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="9a6d0-196">Например, эта команда возвращает сведения о глобальной политике доступа внешних пользователей:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="9a6d0-197">Эта команда возвращает сведения обо всех политиках доступа внешних пользователей:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="9a6d0-198">Возвращаемые сведения будут выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-198">The returned information will resemble this:</span></span>

<span data-ttu-id="9a6d0-199">Identity: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-199">Identity : False</span></span>

<span data-ttu-id="9a6d0-200">Обзор</span><span class="sxs-lookup"><span data-stu-id="9a6d0-200">Description :</span></span>

<span data-ttu-id="9a6d0-201">EnableFederationAccess: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="9a6d0-202">Свойство enablepubliccloudaccess: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="9a6d0-203">Енаблепубликклаудакцессаудиовидеоакцесс: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="9a6d0-204">Енаблеаутсидеакцесс: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="9a6d0-205">Если для **EnableFederationAccess** задано значение true, пользователи, управляемые заданной политикой, могут общаться с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="9a6d0-206">Проверка параметров архивации</span><span class="sxs-lookup"><span data-stu-id="9a6d0-206">Check archiving settings</span></span>

<span data-ttu-id="9a6d0-207">Проверьте параметры архивации для внутренних и Федеративных коммуникаций. Перед проверкой параметров для внутреннего и внешнего архивации необходимо убедиться, что функция архивации включена.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="9a6d0-208">Параметры конфигурации архивации можно проверить с помощью Windows PowerShell и командлета Get – CsArchivingConfiguration:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="9a6d0-209">Обратите внимание, что параметры архивации можно также настроить в области сайта.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="9a6d0-210">Чтобы получить сведения о всех параметрах архивации, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="9a6d0-211">Командлет Get – CsArchivingConfiguration возвращает данные, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="9a6d0-212">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9a6d0-212">Identity : Global</span></span>

<span data-ttu-id="9a6d0-213">Енаблеарчивинг: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-213">EnableArchiving : False</span></span>

<span data-ttu-id="9a6d0-214">EnablePurging: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-214">EnablePurging : False</span></span>

<span data-ttu-id="9a6d0-215">Пуржеекспортедарчивесонли: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="9a6d0-216">Блокконарчивефаилуре: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="9a6d0-217">KeepArchivingDataForDays: 14</span><span class="sxs-lookup"><span data-stu-id="9a6d0-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="9a6d0-218">Пуржехаурофдай: 2</span><span class="sxs-lookup"><span data-stu-id="9a6d0-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="9a6d0-219">Арчиведупликатемессажес: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="9a6d0-220">Качепургингинтервал: 24</span><span class="sxs-lookup"><span data-stu-id="9a6d0-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="9a6d0-221">Если для свойства Енаблеарчивинг задано значение false, сеансы связи не будут архивироваться.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="9a6d0-222">Если вы хотите архивировать только сеансы обмена мгновенными сообщениями, используйте команду, аналогичную приведенной ниже, чтобы включить архивацию сеансов обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="9a6d0-223">Чтобы архивировать сеансы конференц-связи и сеансы обмена мгновенными сообщениями, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="9a6d0-224">Если вы хотите сравнить текущие параметры архивации с параметрами по умолчанию, выполните следующую команду Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="9a6d0-225">Эта команда создает в памяти экземпляр глобальных параметров конфигурации архивации.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="9a6d0-226">Это не реальный набор параметров, используемых Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="9a6d0-227">Однако в нем отображаются значения по умолчанию для всех свойств конфигурации архивации.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="9a6d0-228">Кроме того, с помощью этой команды можно получить полное доменное имя серверов архивации:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="9a6d0-229">После проверки того, включена ли архивация, вы можете просмотреть политики архивации, чтобы определить, архивируются ли внутренние и внешние сеансы связи.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="9a6d0-230">Сведения о политике архивации можно получить с помощью командлета Get – CsArchivingPolicy.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="9a6d0-231">Например, эта команда возвращает сведения о глобальной политике архивации:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="9a6d0-232">Так как политики архивации также можно настроить на уровне сайта и на уровне пользователя, можно использовать эту команду, которая возвращает сведения обо всех политиках архивации:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="9a6d0-233">Сведения, получаемые из Get – CsArchivingPolicy, будут выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="9a6d0-234">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9a6d0-234">Identity : Global</span></span>

<span data-ttu-id="9a6d0-235">Обзор</span><span class="sxs-lookup"><span data-stu-id="9a6d0-235">Description :</span></span>

<span data-ttu-id="9a6d0-236">Присвойте параметрам archiveinternal: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-236">ArchiveInternal : False</span></span>

<span data-ttu-id="9a6d0-237">ArchiveExternal: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-237">ArchiveExternal : False</span></span>

<span data-ttu-id="9a6d0-238">Обратите внимание, что по умолчанию внутренняя и внешняя Архивация отключены в политике архивирования.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="9a6d0-239">Проверка параметров CDR</span><span class="sxs-lookup"><span data-stu-id="9a6d0-239">Check CDR settings</span></span>

<span data-ttu-id="9a6d0-240">Проверьте параметры записи сведений о вызовах (CDR) для записи одноранговой сети, конференц-связи и записи сведений о голосовых вызовах.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="9a6d0-241">Подробные сведения о параметрах CDR можно возвратить с помощью командлета **Get – CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9a6d0-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="9a6d0-242">Например, эта команда возвращает сведения о глобальной коллекции параметров конфигурации CDR:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="9a6d0-243">Так как CDR можно также настроить на уровне сайта, можно также выполнить эту команду, которая возвращает сведения обо всех параметрах конфигурации CDR:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="9a6d0-244">Командлет Get-CsCdrConfiguration возвращает сведения, аналогичные приведенным ниже, для каждой коллекции параметров конфигурации CDR:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="9a6d0-245">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9a6d0-245">Identity : Global</span></span>

<span data-ttu-id="9a6d0-246">EnableCDR: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-246">EnableCDR : True</span></span>

<span data-ttu-id="9a6d0-247">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-247">EnablePurging : True</span></span>

<span data-ttu-id="9a6d0-248">Кипкаллдетаилфордайс: 60</span><span class="sxs-lookup"><span data-stu-id="9a6d0-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="9a6d0-249">Киперроррепортфордайс: 60</span><span class="sxs-lookup"><span data-stu-id="9a6d0-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="9a6d0-250">Пуржехаурофдай: 2</span><span class="sxs-lookup"><span data-stu-id="9a6d0-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="9a6d0-251">Аналогичные сведения можно возвратить для мониторинга QoE с помощью командлета Get – CsQoEConfiguration.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="9a6d0-252">Например, эта команда возвращает сведения о глобальной коллекции параметров конфигурации QoE:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="9a6d0-253">Эти сведения будут выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-253">That information will resemble this:</span></span>

<span data-ttu-id="9a6d0-254">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9a6d0-254">Identity : Global</span></span>

<span data-ttu-id="9a6d0-255">Екстерналконсумериссуедцертид:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="9a6d0-256">EnablePurging: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-256">EnablePurging : True</span></span>

<span data-ttu-id="9a6d0-257">KeepQoEDataForDays: 60</span><span class="sxs-lookup"><span data-stu-id="9a6d0-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="9a6d0-258">Пуржехаурофдай: 1</span><span class="sxs-lookup"><span data-stu-id="9a6d0-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="9a6d0-259">Енабликстерналконсумер: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="9a6d0-260">Екстерналконсумернаме:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-260">ExternalConsumerName :</span></span>

<span data-ttu-id="9a6d0-261">Екстерналконсумерурл:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="9a6d0-262">EnableQoE: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-262">EnableQoE : True</span></span>

<span data-ttu-id="9a6d0-263">Если вы хотите сравнить текущие параметры CDR с параметрами CDR по умолчанию, можно проверить значения по умолчанию, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="9a6d0-264">Аналогично, значения по умолчанию для мониторинга QoE можно получить с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="9a6d0-265">Вы также можете вернуть полное доменное имя серверов мониторинга, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="9a6d0-266">Проверка параметров голосовой связи</span><span class="sxs-lookup"><span data-stu-id="9a6d0-266">Check voice settings</span></span>

<span data-ttu-id="9a6d0-267">Параметры голосовой связи, как правило, важны для администраторов в политиках голосовой связи и голосовых маршрутах: политики голосовой связи содержат параметры, определяющие возможности, предоставляемые отдельным пользователям (например, возможность пересылать или передавать звонки), а также маршруты голосовой связи определяют, как звонки (и если) направляются по протоколу PSTN.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="9a6d0-268">Сведения о политике голосовой связи можно получить с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="9a6d0-269">Например, эта команда возвращает сведения о глобальной политике голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="9a6d0-270">Эта команда возвращает сведения обо всех политиках голосовой связи, настроенных для использования в Организации.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="9a6d0-271">Сведения, возвращаемые командлетом Get – CsVoicePolicy, похожи на следующие:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="9a6d0-272">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9a6d0-272">Identity : Global</span></span>

<span data-ttu-id="9a6d0-273">PstnUsages{}</span><span class="sxs-lookup"><span data-stu-id="9a6d0-273">PstnUsages : {}</span></span>

<span data-ttu-id="9a6d0-274">Обзор</span><span class="sxs-lookup"><span data-stu-id="9a6d0-274">Description :</span></span>

<span data-ttu-id="9a6d0-275">Алловсимулринг: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-275">AllowSimulRing : True</span></span>

<span data-ttu-id="9a6d0-276">Алловкаллфорвардинг: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="9a6d0-277">Алловпстнрераутинг: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="9a6d0-278">Name: DefaultPolicy</span><span class="sxs-lookup"><span data-stu-id="9a6d0-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="9a6d0-279">Енабледелегатион: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-279">EnableDelegation : True</span></span>

<span data-ttu-id="9a6d0-280">Енаблетеамкалл: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-280">EnableTeamCall : True</span></span>

<span data-ttu-id="9a6d0-281">Енаблекаллтрансфер: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="9a6d0-282">Enablecallpark задано: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-282">EnableCallPark : False</span></span>

<span data-ttu-id="9a6d0-283">ЕнаблемалиЦиаускаллтраЦинг: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="9a6d0-284">Енаблебвполициоверриде: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="9a6d0-285">Превентпстнтоллбипасс: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="9a6d0-286">Кроме того, можно создавать запросы, которые возвращают подмножество политик голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="9a6d0-287">Например, эта команда возвращает все политики голосовой связи, которые допускают переадресацию вызовов:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="9a6d0-288">Эта команда возвращает все политики голосовой связи, которые не допускают переадресацию вызовов:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="9a6d0-289">В Windows PowerShell используйте командлет Get – Ксвоицераутинг, чтобы получить сведения о маршрутах голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="9a6d0-290">Эта команда возвращает такие сведения, как, например, для всех маршрутов голосовой связи:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="9a6d0-291">Identity: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="9a6d0-291">Identity : LocalRoute</span></span>

<span data-ttu-id="9a6d0-292">Приоритет: 0</span><span class="sxs-lookup"><span data-stu-id="9a6d0-292">Priority : 0</span></span>

<span data-ttu-id="9a6d0-293">Обзор</span><span class="sxs-lookup"><span data-stu-id="9a6d0-293">Description :</span></span>

<span data-ttu-id="9a6d0-294">Нумберпаттерн: ^ (\\+ 1\[0-9\]{10}) $</span><span class="sxs-lookup"><span data-stu-id="9a6d0-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="9a6d0-295">PstnUsages{}</span><span class="sxs-lookup"><span data-stu-id="9a6d0-295">PstnUsages : {}</span></span>

<span data-ttu-id="9a6d0-296">Пстнгатевайлист:{}</span><span class="sxs-lookup"><span data-stu-id="9a6d0-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="9a6d0-297">Name: LocalRoute</span><span class="sxs-lookup"><span data-stu-id="9a6d0-297">Name : LocalRoute</span></span>

<span data-ttu-id="9a6d0-298">Суппресскаллерид:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-298">SuppressCallerId :</span></span>

<span data-ttu-id="9a6d0-299">AlternateCallerId</span><span class="sxs-lookup"><span data-stu-id="9a6d0-299">AlternateCallerId :</span></span>

<span data-ttu-id="9a6d0-300">Lync Server позволяет создавать маршруты голосовой связи, для которых не используется PSTN, и не указывать шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="9a6d0-301">Однако вы не можете направлять вызовы через маршрут голосовой связи, для которого не настроены эти два значения свойств.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="9a6d0-302">Из-за этого может оказаться полезной возможность периодически запускать эту команду, которая возвращает идентификатор маршрута голосовой связи, для которого не используется PSTN:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="9a6d0-303">Аналогично, эта команда возвращает идентификатор маршрута голосовой связи, для которого не настроен шлюз PSTN:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="9a6d0-304">Проверка параметров помощника по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="9a6d0-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="9a6d0-305">Проверьте параметры помощника для конференц-связи с телефонным подключением PSTN.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="9a6d0-306">Параметры помощника по конференц-связи можно получить только с помощью командлета **Get-CsDialInConferencingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9a6d0-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="9a6d0-307">Эти параметры недоступны в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="9a6d0-308">Чтобы просмотреть параметры помощника по конференц-связи, используйте команду Windows PowerShell, аналогичную приведенной ниже, которая возвращает глобальную коллекцию параметров помощника по конференц-связи:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="9a6d0-309">Обратите внимание на то, что параметры помощника по конференц-связи также можно настроить в области сайта.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="9a6d0-310">Чтобы получить сведения обо всех параметрах помощника по конференц-связи, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="9a6d0-311">Командлет Get – CsDialInConferencingConfiguration возвращает данные, аналогичные приведенным ниже.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="9a6d0-312">Identity: Global</span><span class="sxs-lookup"><span data-stu-id="9a6d0-312">Identity : Global</span></span>

<span data-ttu-id="9a6d0-313">Ентрекситаннаунцементстипе: Усенамес</span><span class="sxs-lookup"><span data-stu-id="9a6d0-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="9a6d0-314">Енабленамерекординг: true</span><span class="sxs-lookup"><span data-stu-id="9a6d0-314">EnableNameRecording : True</span></span>

<span data-ttu-id="9a6d0-315">Ентрекситаннаунцементсенабледбидефаулт: false</span><span class="sxs-lookup"><span data-stu-id="9a6d0-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="9a6d0-316">Если для Ентрекситаннаунцементсенабледбидефаулт задано значение false, объявления конференций отключены.</span><span class="sxs-lookup"><span data-stu-id="9a6d0-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="9a6d0-317">Чтобы включить объявления входа и выхода, выполните следующую команду Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="9a6d0-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9a6d0-318">См. также</span><span class="sxs-lookup"><span data-stu-id="9a6d0-318">See Also</span></span>


[<span data-ttu-id="9a6d0-319">Get — CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="9a6d0-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="9a6d0-320">Get — CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9a6d0-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="9a6d0-321">Get — CsService</span><span class="sxs-lookup"><span data-stu-id="9a6d0-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="9a6d0-322">Get — CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="9a6d0-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="9a6d0-323">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="9a6d0-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="9a6d0-324">Get — CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9a6d0-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="9a6d0-325">Get — CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="9a6d0-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="9a6d0-326">Get — CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="9a6d0-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="9a6d0-327">Get-CsVoicePolicy</span><span class="sxs-lookup"><span data-stu-id="9a6d0-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="9a6d0-328">Get — Ксвоицерауте</span><span class="sxs-lookup"><span data-stu-id="9a6d0-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="9a6d0-329">Get — CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="9a6d0-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

