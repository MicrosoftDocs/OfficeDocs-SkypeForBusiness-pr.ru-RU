---
title: 'Lync Server 2013: Просмотр состояния глобальных параметров для леса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View status of global settings for a forest
ms:assetid: 2ab0f2f1-9908-4e6f-aff3-d6b3cc474b6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747889(v=OCS.15)
ms:contentKeyID: 63969590
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2215e0514f019e94467a204ae86e604dcc0da61
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-status-of-global-settings-for-a-forest-in-lync-server-2013"></a><span data-ttu-id="523a2-102">Просмотр состояния глобальных параметров для леса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="523a2-102">View status of global settings for a forest in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="523a2-103">_**Тема последнего изменения:** 2014-05-20_</span><span class="sxs-lookup"><span data-stu-id="523a2-103">_**Topic Last Modified:** 2014-05-20_</span></span>

<span data-ttu-id="523a2-104">Администраторам ежемесячно просматривайте глобальные параметры развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="523a2-104">Administrators should review the global settings for a Lync Server 2013 deployment monthly.</span></span> <span data-ttu-id="523a2-105">Цель состоит в том, чтобы проанализировать реализованные параметры для набора известных конфигураций — базовой конфигурации, чтобы гарантировать допустимость параметров, а также определить, следует ли обновлять базовую документацию.</span><span class="sxs-lookup"><span data-stu-id="523a2-105">The objective would be to review implemented settings against a set of known configurations—a baseline configuration to help guarantee that settings are valid and to determine whether the baseline documentation should be updated.</span></span> <span data-ttu-id="523a2-106">Изменения в глобальных параметрах должны быть реализованы с помощью процесса управления изменениями, который включает в себя документирование новых параметров.</span><span class="sxs-lookup"><span data-stu-id="523a2-106">Changes to global setting should be implemented through a Change Control process which should include documenting the new settings.</span></span>

<span data-ttu-id="523a2-107">Глобальные параметры, которые необходимо проверить, описаны в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="523a2-107">Global settings that should be reviewed are described in the following sections:</span></span>

<div>

## <a name="check-general-settings"></a><span data-ttu-id="523a2-108">Проверка общих параметров</span><span class="sxs-lookup"><span data-stu-id="523a2-108">Check general settings</span></span>

<span data-ttu-id="523a2-109">Проверьте общие параметры, включая домены, поддерживаемые протоколом SIP для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="523a2-109">Check general settings, including the supported Session Initiation Protocol (SIP) domains for Lync Server 2013.</span></span>

<span data-ttu-id="523a2-110">Данные домена SIP можно вернуть с помощью Windows PowerShell и командлета **Get-кссипдомаин** .</span><span class="sxs-lookup"><span data-stu-id="523a2-110">SIP domain information can be returned by using Windows PowerShell and the **Get-CsSipDomain** cmdlet.</span></span> <span data-ttu-id="523a2-111">Чтобы вернуть эти данные, запустите команду `Get-CsSipDomain` Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="523a2-111">To return this information, run the `Get-CsSipDomain` Windows PowerShell command.</span></span>

<span data-ttu-id="523a2-112">Get-Кссипдомаин будет возвращать примерно такие данные, как и для всех авторизованных доменов SIP:</span><span class="sxs-lookup"><span data-stu-id="523a2-112">Get-CsSipDomain will return information similar to this for all the authorized SIP domains:</span></span>

<span data-ttu-id="523a2-113">Имя удостоверения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="523a2-113">Identity Name IsDefault</span></span>

<span data-ttu-id="523a2-114">\-------- ---- ---------</span><span class="sxs-lookup"><span data-stu-id="523a2-114"></span></span>

<span data-ttu-id="523a2-115">fabrikam.com fabrikam.com истина</span><span class="sxs-lookup"><span data-stu-id="523a2-115">fabrikam.com fabrikam.com True</span></span>

<span data-ttu-id="523a2-116">na.fabrikam.com na.fabrikam.com ложь</span><span class="sxs-lookup"><span data-stu-id="523a2-116">na.fabrikam.com na.fabrikam.com False</span></span>

<span data-ttu-id="523a2-117">Если для свойства по умолчанию задано значение "true", соответствующий домен является доменом SIP по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="523a2-117">If the IsDefault property is set to True, the corresponding domain is your default SIP domain.</span></span> <span data-ttu-id="523a2-118">Вы можете использовать командлет Set-Кссипдомаин для изменения домена SIP по умолчанию для Организации.</span><span class="sxs-lookup"><span data-stu-id="523a2-118">You can use the Set-CsSipDomain cmdlet to change the default SIP domain for your organization.</span></span> <span data-ttu-id="523a2-119">Однако вы не можете просто удалить стандартный домен SIP, так как это оставит без домена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="523a2-119">However, you can't just delete the default SIP domain because that would leave you without a default domain.</span></span> <span data-ttu-id="523a2-120">Если вы хотите удалить домен fabrikam.com (как показано в предыдущем примере), сначала необходимо настроить na.fabrikam.com в качестве домена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="523a2-120">If you wanted to delete the fabrikam.com domain (as shown in the previous example), you would first have to configure na.fabrikam.com to be your default domain.</span></span>

</div>

<div>

## <a name="check-meeting-settings"></a><span data-ttu-id="523a2-121">Проверка параметров собрания</span><span class="sxs-lookup"><span data-stu-id="523a2-121">Check meeting settings</span></span>

<span data-ttu-id="523a2-122">Параметры собрания включают определения политик собраний и поддержку участия анонимных пользователей в собраниях.</span><span class="sxs-lookup"><span data-stu-id="523a2-122">Meeting settings include meeting policy definitions and support for participation of anonymous users in meetings.</span></span>

<span data-ttu-id="523a2-123">Параметры конфигурации собраний можно получить с помощью Windows PowerShell и командлета **Get-ксмитингконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="523a2-123">Meeting configuration settings can be retrieved by using Windows PowerShell and the **Get-CsMeetingConfiguration** cmdlet.</span></span> <span data-ttu-id="523a2-124">Например, эта команда возвращает сведения о глобальных параметрах конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="523a2-124">For example, this command returns information about the global meeting configuration settings:</span></span>

<span data-ttu-id="523a2-125">Параметры конфигурации собрания Get-Ксмитингконфигуратион-Identity "Global" также можно настроить на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="523a2-125">Get-CsMeetingConfiguration –Identity "Global"Meeting configuration settings can also be configured at the site scope.</span></span> <span data-ttu-id="523a2-126">По этой причине вы можете использовать следующую команду, которая возвращает сведения о всех параметрах конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="523a2-126">Because of that, you might want to use the following command, which returns information about all the meeting configuration settings:</span></span>

`Get-CsMeetingConfiguration`

<span data-ttu-id="523a2-127">Командлет **Get-ксмитингконфигуратион** возвращает информацию, подобную приведенной ниже:</span><span class="sxs-lookup"><span data-stu-id="523a2-127">The **Get-CsMeetingConfiguration** cmdlet returns information similar to the following:</span></span>

<span data-ttu-id="523a2-128">Идентификация: Глобальная</span><span class="sxs-lookup"><span data-stu-id="523a2-128">Identity : Global</span></span>

<span data-ttu-id="523a2-129">Пстнкаллерсбипасслобби: true</span><span class="sxs-lookup"><span data-stu-id="523a2-129">PstnCallersBypassLobby : True</span></span>

<span data-ttu-id="523a2-130">Енаблеассигнедконференцетипе: true</span><span class="sxs-lookup"><span data-stu-id="523a2-130">EnableAssignedConferenceType : True</span></span>

<span data-ttu-id="523a2-131">Десигнатеаспресентер: Company</span><span class="sxs-lookup"><span data-stu-id="523a2-131">DesignateAsPresenter : Company</span></span>

<span data-ttu-id="523a2-132">Ассигнедконференцетипебидефаулт: true</span><span class="sxs-lookup"><span data-stu-id="523a2-132">AssignedConferenceTypeByDefault : True</span></span>

<span data-ttu-id="523a2-133">Адмитанонимаусусерсбидефаулт: true</span><span class="sxs-lookup"><span data-stu-id="523a2-133">AdmitAnonymousUsersByDefault : True</span></span>

<span data-ttu-id="523a2-134">Кроме того, последний элемент в списке, **адмитанонимаусусерсбидефаулт**, включает или отключает возможность анонимных пользователей принимать участие в собраниях.</span><span class="sxs-lookup"><span data-stu-id="523a2-134">Again, the final item in the list, **AdmitAnonymousUsersByDefault**, enables or disables the ability of anonymous users to participate in meetings.</span></span>

<span data-ttu-id="523a2-135">При проверке параметров конфигурации собрания может оказаться полезным сравнить текущие параметры с эквивалентами по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="523a2-135">When checking meeting configuration settings, you might find it useful to compare the current settings against the default equivalents.</span></span> <span data-ttu-id="523a2-136">Вы можете просмотреть параметры конфигурации собрания по умолчанию, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="523a2-136">You can view the default meeting configuration settings by running the following command:</span></span>

`New-CsMeetingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="523a2-137">Предыдущая команда создает одновременный экземпляр глобальных параметров конфигурации собрания в памяти, экземпляр которого использует значение по умолчанию для каждого свойства.</span><span class="sxs-lookup"><span data-stu-id="523a2-137">The previous command creates an in-memory-only instance of the global meeting configuration settings, an instance that uses the default value for each property.</span></span> <span data-ttu-id="523a2-138">При выполнении команды не создаются фактические параметры конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="523a2-138">No actual meeting configuration settings are created when you run the command.</span></span> <span data-ttu-id="523a2-139">Тем не менее, на экране будут отображаться все значения свойств по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="523a2-139">However, all the default property values will be displayed on-screen.</span></span>

</div>

<div>

## <a name="check-edge-servers-and-their-settings"></a><span data-ttu-id="523a2-140">Проверка серверов пограничного сервера и их параметров</span><span class="sxs-lookup"><span data-stu-id="523a2-140">Check Edge Servers and their settings</span></span>

<span data-ttu-id="523a2-141">Данные пограничного сервера можно получить с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="523a2-141">Edge Server information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="523a2-142">Эта команда возвращает сведения о всех пограничных серверах, настроенных для использования в вашей организации:</span><span class="sxs-lookup"><span data-stu-id="523a2-142">This command returns information about all the Edge Servers configured for use in your organization:</span></span>

`Get-CsService -EdgeServer`

<span data-ttu-id="523a2-143">Возвращенные сведения включают все полные доменные значения и параметры порта для каждого пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="523a2-143">The returned information includes all of the FQDN and port settings for each Edge Server:</span></span>

<span data-ttu-id="523a2-144">Identity: Еджесервер: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="523a2-144">Identity : EdgeServer: dc.fabrikam.com</span></span>

<span data-ttu-id="523a2-145">Регистратор: регистратор: LYNC-SE.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="523a2-145">Registrar : Registrar: LYNC-SE.fabrikam.com</span></span>

<span data-ttu-id="523a2-146">Акцесседжеинтерналсиппорт: 5061</span><span class="sxs-lookup"><span data-stu-id="523a2-146">AccessEdgeInternalSipPort : 5061</span></span>

<span data-ttu-id="523a2-147">Акцесседжеекстерналсиппорт: 5061</span><span class="sxs-lookup"><span data-stu-id="523a2-147">AccessEdgeExternalSipPort : 5061</span></span>

<span data-ttu-id="523a2-148">Акцесседжеклиентпорт: 443</span><span class="sxs-lookup"><span data-stu-id="523a2-148">AccessEdgeClientPort : 443</span></span>

<span data-ttu-id="523a2-149">Датапсомсерверпорт: 8057</span><span class="sxs-lookup"><span data-stu-id="523a2-149">DataPsomServerPort : 8057</span></span>

<span data-ttu-id="523a2-150">Датапсомклиентпорт: 444</span><span class="sxs-lookup"><span data-stu-id="523a2-150">DataPsomClientPort : 444</span></span>

<span data-ttu-id="523a2-151">Медиарелайауседжепорт: 5062</span><span class="sxs-lookup"><span data-stu-id="523a2-151">MediaRelayAuthEdgePort : 5062</span></span>

<span data-ttu-id="523a2-152">Медиарелайаусинтерналтурнткппорт: 443</span><span class="sxs-lookup"><span data-stu-id="523a2-152">MediaRelayAuthInternalTurnTcpPort : 443</span></span>

<span data-ttu-id="523a2-153">Медиарелайаусекстерналтурнткппорт: 445</span><span class="sxs-lookup"><span data-stu-id="523a2-153">MediaRelayAuthExternalTurnTcpPort : 445</span></span>

<span data-ttu-id="523a2-154">Медиарелайаусинтерналтурнудппорт: 3478</span><span class="sxs-lookup"><span data-stu-id="523a2-154">MediaRelayAuthInternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="523a2-155">Медиарелайаусекстерналтурнудппорт: 3478</span><span class="sxs-lookup"><span data-stu-id="523a2-155">MediaRelayAuthExternalTurnUdpPort : 3478</span></span>

<span data-ttu-id="523a2-156">Медиакоммуникатионпортстарт: 50000</span><span class="sxs-lookup"><span data-stu-id="523a2-156">MediaCommunicationPortStart : 50000</span></span>

<span data-ttu-id="523a2-157">Медиакомуникатионпорткаунт: 10000</span><span class="sxs-lookup"><span data-stu-id="523a2-157">MediaComunicationPortCount : 10000</span></span>

<span data-ttu-id="523a2-158">Акцесседжеекстерналфкдн: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="523a2-158">AccessEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="523a2-159">Датаеджеекстерналфкдн: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="523a2-159">DataEdgeExternalFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="523a2-160">Аведжеекстерналфкдн:</span><span class="sxs-lookup"><span data-stu-id="523a2-160">AVEdgeExternalFqdn :</span></span>

<span data-ttu-id="523a2-161">Интерналинтерфацефкдн:</span><span class="sxs-lookup"><span data-stu-id="523a2-161">InternalInterfaceFqdn :</span></span>

<span data-ttu-id="523a2-162">Екстерналмрасфкдн: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="523a2-162">ExternalMrasFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="523a2-163">Депендентсервицелист: {регистратор: LYNC-SE.fabrikam.com,</span><span class="sxs-lookup"><span data-stu-id="523a2-163">DependentServiceList : {Registrar:LYNC-SE.fabrikam.com,</span></span>

<span data-ttu-id="523a2-164">КонференЦингсервер: LYNC-SE. fabrikam</span><span class="sxs-lookup"><span data-stu-id="523a2-164">ConferencingServer:LYNC-SE.fabrikam</span></span>

<span data-ttu-id="523a2-165">com, Медиатионсервер: LYNC-SE.</span><span class="sxs-lookup"><span data-stu-id="523a2-165">com, MediationServer:LYNC-SE.</span></span>

<span data-ttu-id="523a2-166">fabrikam.com}</span><span class="sxs-lookup"><span data-stu-id="523a2-166">fabrikam.com}</span></span>

<span data-ttu-id="523a2-167">Сервицеид: fabrikam.com-Еджесервер-2</span><span class="sxs-lookup"><span data-stu-id="523a2-167">ServiceId : fabrikam.com-EdgeServer-2</span></span>

<span data-ttu-id="523a2-168">Идентификатор сайта: сайт:фабрикам. com</span><span class="sxs-lookup"><span data-stu-id="523a2-168">SiteId : site:fabrikam.com</span></span>

<span data-ttu-id="523a2-169">Пулфкдн: dc.fabrikam.com</span><span class="sxs-lookup"><span data-stu-id="523a2-169">PoolFqdn : dc.fabrikam.com</span></span>

<span data-ttu-id="523a2-170">Версия: 5</span><span class="sxs-lookup"><span data-stu-id="523a2-170">Version : 5</span></span>

<span data-ttu-id="523a2-171">Role (роль): Еджесервер</span><span class="sxs-lookup"><span data-stu-id="523a2-171">Role : EdgeServer</span></span>

<div>

## <a name="check-federation-settings"></a><span data-ttu-id="523a2-172">Проверка параметров Федерации</span><span class="sxs-lookup"><span data-stu-id="523a2-172">Check federation settings</span></span>

<span data-ttu-id="523a2-173">Установите флажки для параметров Федерации, например, настроены ли они, и, если вы ответили "Да", полное доменное имя и порт.</span><span class="sxs-lookup"><span data-stu-id="523a2-173">Check Federation settings, such as whether it is configured and, if the answer is "yes,", the FQDN and port.</span></span> <span data-ttu-id="523a2-174">Интеграция включена и отключена с помощью глобальной коллекции параметров конфигурации пограничного доступа.</span><span class="sxs-lookup"><span data-stu-id="523a2-174">Federation is enabled and disabled by using the global collection of Access Edge configuration settings.</span></span> <span data-ttu-id="523a2-175">Помимо прочего, это означает, что Федерация настроена на уровне "все" или "все". включена либо Федерация для всей Организации, либо Федерация отключена для всей Организации.</span><span class="sxs-lookup"><span data-stu-id="523a2-175">Among other things, these mean that federation is configured on an all-or-nothing basis: either federation is enabled for the whole organization or federation is disabled for the whole organization</span></span>

<span data-ttu-id="523a2-176">Параметры конфигурации Edge Access можно вернуть с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="523a2-176">Your Access Edge configuration settings can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="523a2-177">Для этого выполните следующую команду Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="523a2-177">To do that, run the following Windows PowerShell command:</span></span>

`Get-CsAccessEdgeConfiguration`

<span data-ttu-id="523a2-178">В свою очередь она возвращает данные примерно так:</span><span class="sxs-lookup"><span data-stu-id="523a2-178">In turn, that command will return data similar to this:</span></span>

<span data-ttu-id="523a2-179">Идентификация: Глобальная</span><span class="sxs-lookup"><span data-stu-id="523a2-179">Identity : Global</span></span>

<span data-ttu-id="523a2-180">Аллованонимаусусерс: false</span><span class="sxs-lookup"><span data-stu-id="523a2-180">AllowAnonymousUsers : False</span></span>

<span data-ttu-id="523a2-181">Алловфедератедусерс: false</span><span class="sxs-lookup"><span data-stu-id="523a2-181">AllowFederatedUsers : False</span></span>

<span data-ttu-id="523a2-182">Алловаутсидеусерс: false</span><span class="sxs-lookup"><span data-stu-id="523a2-182">AllowOutsideUsers : False</span></span>

<span data-ttu-id="523a2-183">Беклеарингхаусе: false</span><span class="sxs-lookup"><span data-stu-id="523a2-183">BeClearingHouse : False</span></span>

<span data-ttu-id="523a2-184">Енаблепартнердисковери: false</span><span class="sxs-lookup"><span data-stu-id="523a2-184">EnablePartnerDiscovery : False</span></span>

<span data-ttu-id="523a2-185">Енаблеарчивингдисклаимер: false</span><span class="sxs-lookup"><span data-stu-id="523a2-185">EnableArchivingDisclaimer : False</span></span>

<span data-ttu-id="523a2-186">Кипкрлсуптодатефорпирс: true</span><span class="sxs-lookup"><span data-stu-id="523a2-186">KeepCrlsUpToDateForPeers : True</span></span>

<span data-ttu-id="523a2-187">Марксаурцеверифиаблеонаутгоингмессажес: true</span><span class="sxs-lookup"><span data-stu-id="523a2-187">MarkSourceVerifiableOnOutgoingMessages : True</span></span>

<span data-ttu-id="523a2-188">Аутгоингтлскаунтфорфедератедпартнерс: 4</span><span class="sxs-lookup"><span data-stu-id="523a2-188">OutgoingTlsCountForFederatedPartners : 4</span></span>

<span data-ttu-id="523a2-189">Раутингмесод: Уседнссрвраутинг</span><span class="sxs-lookup"><span data-stu-id="523a2-189">RoutingMethod : UseDnsSrvRouting</span></span>

<span data-ttu-id="523a2-190">Если для свойства **алловфедератедусерс** задано значение "true", это означает, что для вашей организации включена Федерация.</span><span class="sxs-lookup"><span data-stu-id="523a2-190">If the **AllowFederatedUsers** property is set to True, that means that federation is enabled for your organization.</span></span> <span data-ttu-id="523a2-191">(Установка **алловфедератедусерс** в true также означает, что в сценарии разделенного домена локальные пользователи смогут легко общаться с пользователями в облаке).</span><span class="sxs-lookup"><span data-stu-id="523a2-191">(Setting **AllowFederatedUsers** to True also means that, in a split domain scenario, your on-premises users will be able to communicate seamlessly with your in-the-cloud users.)</span></span>

<span data-ttu-id="523a2-192">Чтобы получить полные доменные имена и параметры порта для пограничного сервера, ознакомьтесь с предыдущими задачами (пограничные серверы и их параметры).</span><span class="sxs-lookup"><span data-stu-id="523a2-192">To retrieve the FQDN and port settings for your Edge Server, see the previous task (Edge Servers and their settings).</span></span>

<span data-ttu-id="523a2-193">Включение Федерации в глобальной области означает, что пользователи могут взаимодействовать с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="523a2-193">Enabling federation at the global scope only means that users can potentially communicate with federated users.</span></span> <span data-ttu-id="523a2-194">Чтобы определить, могут ли какие либо пользователи самим взаимодействовать с федеративными пользователями, необходимо проверить политику доступа внешних пользователей, назначенную для этого пользователя.</span><span class="sxs-lookup"><span data-stu-id="523a2-194">To determine whether any individual users can actually communicate with federated users requires you to examine the external user access policy assigned to that user.</span></span>

<span data-ttu-id="523a2-195">Сведения о внешнем пользовательском доступе можно вернуть с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="523a2-195">External user access information can be returned by using Windows PowerShell.</span></span> <span data-ttu-id="523a2-196">Например, эта команда возвращает сведения о глобальной политике доступа внешних пользователей:</span><span class="sxs-lookup"><span data-stu-id="523a2-196">For example, this command returns information for the global external user access policy:</span></span>

`Get-CsExternalAccessPolicy -Identity "Global"`

<span data-ttu-id="523a2-197">Эта команда возвращает сведения обо всех внешних политиках доступа пользователей.</span><span class="sxs-lookup"><span data-stu-id="523a2-197">And this command returns information for all the external user access policies:</span></span>

`Get-CsExternalAccessPolicy`

<span data-ttu-id="523a2-198">Возвращенные сведения будут выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="523a2-198">The returned information will resemble this:</span></span>

<span data-ttu-id="523a2-199">Идентификация: ложь</span><span class="sxs-lookup"><span data-stu-id="523a2-199">Identity : False</span></span>

<span data-ttu-id="523a2-200">Nописание</span><span class="sxs-lookup"><span data-stu-id="523a2-200">Description :</span></span>

<span data-ttu-id="523a2-201">Енаблефедератионакцесс: false</span><span class="sxs-lookup"><span data-stu-id="523a2-201">EnableFederationAccess : False</span></span>

<span data-ttu-id="523a2-202">Енаблепубликклаудакцесс: false</span><span class="sxs-lookup"><span data-stu-id="523a2-202">EnablePublicCloudAccess : False</span></span>

<span data-ttu-id="523a2-203">Енаблепубликклаудакцессаудиовидеоакцесс: false</span><span class="sxs-lookup"><span data-stu-id="523a2-203">EnablePublicCloudAccessAudioVideoAccess : False</span></span>

<span data-ttu-id="523a2-204">Енаблеаутсидеакцесс: false</span><span class="sxs-lookup"><span data-stu-id="523a2-204">EnableOutsideAccess : False</span></span>

<span data-ttu-id="523a2-205">Если для **енаблефедератионакцесс** задано значение "true", пользователи, управляемые данной политикой, могут общаться с федеративными пользователями.</span><span class="sxs-lookup"><span data-stu-id="523a2-205">If **EnableFederationAccess** is set to True, then users managed by the given policy can communicate with federated users.</span></span>

</div>

</div>

<div>

## <a name="check-archiving-settings"></a><span data-ttu-id="523a2-206">Проверка параметров архивации</span><span class="sxs-lookup"><span data-stu-id="523a2-206">Check archiving settings</span></span>

<span data-ttu-id="523a2-207">Проверка параметров архивирования для внутренних и Федеративных коммуникаций. Перед проверкой параметров внутренних и внешних архиваций убедитесь, что архивация включена.</span><span class="sxs-lookup"><span data-stu-id="523a2-207">Check archiving settings for internal and federated communications.Before verifying the settings for internal and external archiving, you should verify that archiving is enabled.</span></span>

<span data-ttu-id="523a2-208">Параметры конфигурации архивации можно проверить с помощью Windows PowerShell и командлета Get-Ксарчивингконфигуратион:</span><span class="sxs-lookup"><span data-stu-id="523a2-208">Archiving configuration settings can be verified by using Windows PowerShell and the Get-CsArchivingConfiguration cmdlet:</span></span>

`Get-CsArchivingConfiguration -Identity "Global"`

<span data-ttu-id="523a2-209">Обратите внимание, что параметры архивации также можно настроить в области сайта.</span><span class="sxs-lookup"><span data-stu-id="523a2-209">Note that archiving settings can also be configured at the site scope.</span></span> <span data-ttu-id="523a2-210">Чтобы получить сведения о всех параметрах архивации, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="523a2-210">To return information about all the archiving settings, use this command:</span></span>

`Get-CsArchivingConfiguration`

<span data-ttu-id="523a2-211">Командлет Get-Ксарчивингконфигуратион возвращает данные примерно так:</span><span class="sxs-lookup"><span data-stu-id="523a2-211">The Get-CsArchivingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="523a2-212">Идентификация: Глобальная</span><span class="sxs-lookup"><span data-stu-id="523a2-212">Identity : Global</span></span>

<span data-ttu-id="523a2-213">Енаблеарчивинг: false</span><span class="sxs-lookup"><span data-stu-id="523a2-213">EnableArchiving : False</span></span>

<span data-ttu-id="523a2-214">Енаблепургинг: false</span><span class="sxs-lookup"><span data-stu-id="523a2-214">EnablePurging : False</span></span>

<span data-ttu-id="523a2-215">Пуржеекспортедарчивесонли: false</span><span class="sxs-lookup"><span data-stu-id="523a2-215">PurgeExportedArchivesOnly : False</span></span>

<span data-ttu-id="523a2-216">Блокконарчивефаилуре: false</span><span class="sxs-lookup"><span data-stu-id="523a2-216">BlockOnArchiveFailure : False</span></span>

<span data-ttu-id="523a2-217">Кипарчивингдатафордайс: 14</span><span class="sxs-lookup"><span data-stu-id="523a2-217">KeepArchivingDataForDays : 14</span></span>

<span data-ttu-id="523a2-218">Пуржехаурофдай: 2</span><span class="sxs-lookup"><span data-stu-id="523a2-218">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="523a2-219">Арчиведупликатемессажес: true</span><span class="sxs-lookup"><span data-stu-id="523a2-219">ArchiveDuplicateMessages : True</span></span>

<span data-ttu-id="523a2-220">Качепургингинтервал: 24</span><span class="sxs-lookup"><span data-stu-id="523a2-220">CachePurgingInterval : 24</span></span>

<span data-ttu-id="523a2-221">Если свойство Енаблеарчивинг имеет значение false, это означает, что сеансы связи не будут заархивированы.</span><span class="sxs-lookup"><span data-stu-id="523a2-221">If the EnableArchiving property is set to False, that means that no communication sessions will be archived.</span></span> <span data-ttu-id="523a2-222">Если вы хотите архивировать сеансы мгновенных сообщений, используйте следующую команду, чтобы включить архивацию сеансов обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="523a2-222">If you want to archive instant messaging sessions only, use a command such as the following to enable the archiving of IM sessions:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="523a2-223">Для архивации сеансов конференций и сеансов обмена мгновенными сообщениями используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="523a2-223">To archive conferencing sessions and instant messaging sessions, use this command:</span></span>

`Set-CsArchivingConfiguration -Identity "Global" -EnableArchiving "IMOnly"`

<span data-ttu-id="523a2-224">Если вы хотите сравнить текущие параметры архивации с параметрами по умолчанию, выполните следующую команду Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="523a2-224">If you’d like to compare your current archiving settings with the default settings, run the following Windows PowerShell command:</span></span>

`New-CsArchivingConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="523a2-225">Эта команда создает одновременный экземпляр глобальных параметров конфигурации архивации в памяти.</span><span class="sxs-lookup"><span data-stu-id="523a2-225">That command creates an in-memory-only instance of the global archiving configuration settings.</span></span> <span data-ttu-id="523a2-226">Это не является реальной коллекцией параметров, которые используются в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="523a2-226">This is not a real collection of settings that is used by Lync Server.</span></span> <span data-ttu-id="523a2-227">Тем не менее, в нем отображаются значения по умолчанию для всех свойств конфигурации архивации.</span><span class="sxs-lookup"><span data-stu-id="523a2-227">However, it does display the default values for all the archiving configuration properties.</span></span>

<span data-ttu-id="523a2-228">Вы также можете использовать эту команду, чтобы вернуть полные доменные имена серверов архивации.</span><span class="sxs-lookup"><span data-stu-id="523a2-228">You can also use this command to return the FQDN of your Archiving servers:</span></span>

`Get-CsService -ArchivingServer`

<span data-ttu-id="523a2-229">После того как вы убедитесь, что архивация включена, вы можете просмотреть политики архивации, чтобы определить, архивируются ли внутренние и внешние сеансы связи.</span><span class="sxs-lookup"><span data-stu-id="523a2-229">After you have verified that archiving is enabled, you can then view your archiving policies to determine whether internal and external communication sessions are being archived.</span></span>

<span data-ttu-id="523a2-230">Сведения о политике архивации можно получить с помощью командлета Get-Ксарчивингполици.</span><span class="sxs-lookup"><span data-stu-id="523a2-230">Archiving policy information can be retrieved by using the Get-CsArchivingPolicy cmdlet.</span></span> <span data-ttu-id="523a2-231">Например, эта команда возвращает сведения о глобальной политике архивации.</span><span class="sxs-lookup"><span data-stu-id="523a2-231">For example, this command returns information about the global archiving policy:</span></span>

`Get-CsArchivingPolicy -Identity "Global"`

<span data-ttu-id="523a2-232">Поскольку политики архивации также можно настроить на сайте и на уровне пользователя, вам также может потребоваться использовать эту команду, которая возвращает сведения обо всех политиках архивации.</span><span class="sxs-lookup"><span data-stu-id="523a2-232">Because archiving policies can also be configured at the site and the per-user scope, you might also want to use this command, which returns information about all the archiving policies:</span></span>

`Get-CsArchivingPolicy`

<span data-ttu-id="523a2-233">Данные, получаемые из Get-Ксарчивингполици, будут выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="523a2-233">The information that you receive from Get-CsArchivingPolicy will resemble this:</span></span>

<span data-ttu-id="523a2-234">Идентификация: Глобальная</span><span class="sxs-lookup"><span data-stu-id="523a2-234">Identity : Global</span></span>

<span data-ttu-id="523a2-235">Nописание</span><span class="sxs-lookup"><span data-stu-id="523a2-235">Description :</span></span>

<span data-ttu-id="523a2-236">Арчивеинтернал: false</span><span class="sxs-lookup"><span data-stu-id="523a2-236">ArchiveInternal : False</span></span>

<span data-ttu-id="523a2-237">Арчивикстернал: false</span><span class="sxs-lookup"><span data-stu-id="523a2-237">ArchiveExternal : False</span></span>

<span data-ttu-id="523a2-238">Обратите внимание, что по умолчанию как внутренние, так и внешние архивации отключены в политике архивации.</span><span class="sxs-lookup"><span data-stu-id="523a2-238">Note that, by default, both internal and external archiving are disabled in an archiving policy.</span></span>

</div>

<div>

## <a name="check-cdr-settings"></a><span data-ttu-id="523a2-239">Проверка параметров CDR</span><span class="sxs-lookup"><span data-stu-id="523a2-239">Check CDR settings</span></span>

<span data-ttu-id="523a2-240">Установите флажок запись с подробными сведениями о звонке (CDR) для одноранговой сети, Конференции и записи голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="523a2-240">Check Call Detail Record (CDR) settings for peer-to-peer, conferencing, and Voice call detail recording.</span></span> <span data-ttu-id="523a2-241">Подробные сведения о параметрах CDR можно вернуть с помощью командлета **Get-кскдрконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="523a2-241">Detailed information about your CDR settings can be returned by using the **Get-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="523a2-242">Например, эта команда возвращает сведения о глобальной коллекции параметров конфигурации CDR:</span><span class="sxs-lookup"><span data-stu-id="523a2-242">For example, this command returns information about the global collection of CDR configuration settings:</span></span>

`Get-CsCdrConfiguration -Identity "Global"`

<span data-ttu-id="523a2-243">Так как CDR также можно настроить на уровне сайта, вы также можете запустить эту команду, которая возвращает сведения обо всех параметрах конфигурации CDR:</span><span class="sxs-lookup"><span data-stu-id="523a2-243">Because CDR can also be configured at the site scope, you might also want to run this command, which returns information about all the CDR configuration settings:</span></span>

`Get-CsCdrConfiguration`

<span data-ttu-id="523a2-244">Командлет Get-Кскдрконфигуратион возвращает такие сведения, как и для каждой коллекции параметров конфигурации CDR:</span><span class="sxs-lookup"><span data-stu-id="523a2-244">The Get-CsCdrConfiguration cmdlet returns information similar to this for each collection of CDR configuration settings:</span></span>

<span data-ttu-id="523a2-245">Идентификация: Глобальная</span><span class="sxs-lookup"><span data-stu-id="523a2-245">Identity : Global</span></span>

<span data-ttu-id="523a2-246">Енаблекдр: true</span><span class="sxs-lookup"><span data-stu-id="523a2-246">EnableCDR : True</span></span>

<span data-ttu-id="523a2-247">Енаблепургинг: true</span><span class="sxs-lookup"><span data-stu-id="523a2-247">EnablePurging : True</span></span>

<span data-ttu-id="523a2-248">Кипкаллдетаилфордайс: 60</span><span class="sxs-lookup"><span data-stu-id="523a2-248">KeepCallDetailForDays : 60</span></span>

<span data-ttu-id="523a2-249">Киперроррепортфордайс: 60</span><span class="sxs-lookup"><span data-stu-id="523a2-249">KeepErrorReportForDays : 60</span></span>

<span data-ttu-id="523a2-250">Пуржехаурофдай: 2</span><span class="sxs-lookup"><span data-stu-id="523a2-250">PurgeHourOfDay : 2</span></span>

<span data-ttu-id="523a2-251">Аналогичные данные могут возвращаться для мониторинга QoE с помощью командлета Get-Кскоеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="523a2-251">Similar information can be returned for QoE monitoring by using the Get-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="523a2-252">Например, эта команда возвращает сведения о глобальной коллекции параметров конфигурации QoE:</span><span class="sxs-lookup"><span data-stu-id="523a2-252">For example, this command returns information about the global collection of QoE configuration settings:</span></span>

`Get-QoEConfiguration -Identity "Global"`

<span data-ttu-id="523a2-253">Эти сведения будут выглядеть примерно так:</span><span class="sxs-lookup"><span data-stu-id="523a2-253">That information will resemble this:</span></span>

<span data-ttu-id="523a2-254">Идентификация: Глобальная</span><span class="sxs-lookup"><span data-stu-id="523a2-254">Identity : Global</span></span>

<span data-ttu-id="523a2-255">Екстерналконсумериссуедцертид:</span><span class="sxs-lookup"><span data-stu-id="523a2-255">ExternalConsumerIssuedCertId :</span></span>

<span data-ttu-id="523a2-256">Енаблепургинг: true</span><span class="sxs-lookup"><span data-stu-id="523a2-256">EnablePurging : True</span></span>

<span data-ttu-id="523a2-257">Кипкоедатафордайс: 60</span><span class="sxs-lookup"><span data-stu-id="523a2-257">KeepQoEDataForDays : 60</span></span>

<span data-ttu-id="523a2-258">Пуржехаурофдай: 1</span><span class="sxs-lookup"><span data-stu-id="523a2-258">PurgeHourOfDay : 1</span></span>

<span data-ttu-id="523a2-259">Енабликстерналконсумер: false</span><span class="sxs-lookup"><span data-stu-id="523a2-259">EnableExternalConsumer : False</span></span>

<span data-ttu-id="523a2-260">Екстерналконсумернаме:</span><span class="sxs-lookup"><span data-stu-id="523a2-260">ExternalConsumerName :</span></span>

<span data-ttu-id="523a2-261">Екстерналконсумерурл:</span><span class="sxs-lookup"><span data-stu-id="523a2-261">ExternalConsumerURL :</span></span>

<span data-ttu-id="523a2-262">Енаблекое: true</span><span class="sxs-lookup"><span data-stu-id="523a2-262">EnableQoE : True</span></span>

<span data-ttu-id="523a2-263">Если вы хотите сравнить текущие параметры CDR с параметрами CDR по умолчанию, можно просмотреть значения по умолчанию, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="523a2-263">If you want to compare your current CDR settings with the default CDR settings, the default values can be reviewed by running this command:</span></span>

`New-CsCdrConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="523a2-264">Также значения по умолчанию для мониторинга QoE можно получить с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="523a2-264">Likewise, the default values for QoE monitoring can be retrieved by using this command:</span></span>

`New-CsQoEConfiguration -Identity "Global" -InMemory`

<span data-ttu-id="523a2-265">Вы также можете вернуть полные доменные имена серверов мониторинга, выполнив следующую команду:</span><span class="sxs-lookup"><span data-stu-id="523a2-265">You can also return the FQDN of your Monitoring servers by running this command:</span></span>

`Get-CsService -MonitoringServer`

</div>

<div>

## <a name="check-voice-settings"></a><span data-ttu-id="523a2-266">Проверка параметров голоса</span><span class="sxs-lookup"><span data-stu-id="523a2-266">Check voice settings</span></span>

<span data-ttu-id="523a2-267">Параметры голосовой связи, как правило, важны для администраторов в политиках голосовой связи и голосовых маршрутах: политики голосовой связи содержат параметры, определяющие возможности, доступные для отдельных пользователей (например, возможность пересылки или передачи звонков). Голосовые маршруты определяют, как звонки (и если) направляются по протоколу КТСОП.</span><span class="sxs-lookup"><span data-stu-id="523a2-267">The voice settings typically important to administrators are contained in voice policies and voice routes: voice policies contain the settings that determine the capabilities exposed to individual users (such as the ability to forward or transfer calls), while voice routes determine how (and if) calls are routed across the PSTN.</span></span>

<span data-ttu-id="523a2-268">Сведения о политике голосовой связи можно получить с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="523a2-268">Voice policy information can be retrieved by using Windows PowerShell.</span></span> <span data-ttu-id="523a2-269">Например, эта команда возвращает сведения о глобальной политике голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="523a2-269">For example, this command returns information about the global voice policy:</span></span>

`Get-CsVoicePolicy -Identity "Global"`

<span data-ttu-id="523a2-270">Эта команда возвращает сведения обо всех голосовых политиках, настроенных для использования в Организации.</span><span class="sxs-lookup"><span data-stu-id="523a2-270">And this command returns information about all the voice policies configured for use in the organization:</span></span>

`Get-CsVoicePolicy`

<span data-ttu-id="523a2-271">Данные, возвращаемые командлетом Get-Ксвоицеполици, похожи на приведенные ниже.</span><span class="sxs-lookup"><span data-stu-id="523a2-271">The information returned by the Get-CsVoicePolicy cmdlet resembles the following:</span></span>

<span data-ttu-id="523a2-272">Идентификация: Глобальная</span><span class="sxs-lookup"><span data-stu-id="523a2-272">Identity : Global</span></span>

<span data-ttu-id="523a2-273">Пстнусажес:{}</span><span class="sxs-lookup"><span data-stu-id="523a2-273">PstnUsages : {}</span></span>

<span data-ttu-id="523a2-274">Nописание</span><span class="sxs-lookup"><span data-stu-id="523a2-274">Description :</span></span>

<span data-ttu-id="523a2-275">Алловсимулринг: true</span><span class="sxs-lookup"><span data-stu-id="523a2-275">AllowSimulRing : True</span></span>

<span data-ttu-id="523a2-276">Алловкаллфорвардинг: true</span><span class="sxs-lookup"><span data-stu-id="523a2-276">AllowCallForwarding : True</span></span>

<span data-ttu-id="523a2-277">Алловпстнрераутинг: true</span><span class="sxs-lookup"><span data-stu-id="523a2-277">AllowPSTNReRouting : True</span></span>

<span data-ttu-id="523a2-278">Name (имя): Дефаултполици</span><span class="sxs-lookup"><span data-stu-id="523a2-278">Name : DefaultPolicy</span></span>

<span data-ttu-id="523a2-279">Енабледелегатион: true</span><span class="sxs-lookup"><span data-stu-id="523a2-279">EnableDelegation : True</span></span>

<span data-ttu-id="523a2-280">Енаблетеамкалл: true</span><span class="sxs-lookup"><span data-stu-id="523a2-280">EnableTeamCall : True</span></span>

<span data-ttu-id="523a2-281">Енаблекаллтрансфер: true</span><span class="sxs-lookup"><span data-stu-id="523a2-281">EnableCallTransfer : True</span></span>

<span data-ttu-id="523a2-282">Енаблекаллпарк: false</span><span class="sxs-lookup"><span data-stu-id="523a2-282">EnableCallPark : False</span></span>

<span data-ttu-id="523a2-283">ЕнаблемалиЦиаускаллтраЦинг: false</span><span class="sxs-lookup"><span data-stu-id="523a2-283">EnableMaliciousCallTracing : False</span></span>

<span data-ttu-id="523a2-284">Енаблебвполициоверриде: false</span><span class="sxs-lookup"><span data-stu-id="523a2-284">EnableBWPolicyOverride : False</span></span>

<span data-ttu-id="523a2-285">Превентпстнтоллбипасс: false</span><span class="sxs-lookup"><span data-stu-id="523a2-285">PreventPSTNTollBypass : False</span></span>

<span data-ttu-id="523a2-286">Вы также можете создавать запросы, которые возвращают подмножество политик голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="523a2-286">You can also create queries that returned a subset of your voice policies.</span></span> <span data-ttu-id="523a2-287">Например, эта команда возвращает все политики голосовой связи, которые разрешают переадресацию звонков.</span><span class="sxs-lookup"><span data-stu-id="523a2-287">For example, this command returns all the voice policies that allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $True}`

<span data-ttu-id="523a2-288">Эта команда возвращает все политики голосовой связи, не допускающие переадресацию звонков.</span><span class="sxs-lookup"><span data-stu-id="523a2-288">And this command returns all the voice policies that don’t allow call forwarding:</span></span>

`Get-CsVoicePolicy | Where-Object {$_.AllowCallForwarding -eq $False}`

<span data-ttu-id="523a2-289">В Windows PowerShell используйте командлет Get-Ксвоицераутинг, чтобы получить сведения о голосовых маршрутах.</span><span class="sxs-lookup"><span data-stu-id="523a2-289">In Windows PowerShell, use the Get-CsVoiceRouting cmdlet to return information about your voice routes:</span></span>

`Get-CsVoiceRoute`

<span data-ttu-id="523a2-290">Эта команда возвращает такие сведения, как, например, для всех голосовых маршрутов.</span><span class="sxs-lookup"><span data-stu-id="523a2-290">That command returns information such as this for all the voice routes:</span></span>

<span data-ttu-id="523a2-291">Identity: Локалрауте</span><span class="sxs-lookup"><span data-stu-id="523a2-291">Identity : LocalRoute</span></span>

<span data-ttu-id="523a2-292">Priority (приоритет): 0</span><span class="sxs-lookup"><span data-stu-id="523a2-292">Priority : 0</span></span>

<span data-ttu-id="523a2-293">Nописание</span><span class="sxs-lookup"><span data-stu-id="523a2-293">Description :</span></span>

<span data-ttu-id="523a2-294">Нумберпаттерн: ^ (\\+ 1\[0-9\]{10}) $</span><span class="sxs-lookup"><span data-stu-id="523a2-294">NumberPattern : ^(\\+1\[0-9\]{10})$</span></span>

<span data-ttu-id="523a2-295">Пстнусажес:{}</span><span class="sxs-lookup"><span data-stu-id="523a2-295">PstnUsages : {}</span></span>

<span data-ttu-id="523a2-296">Пстнгатевайлист:{}</span><span class="sxs-lookup"><span data-stu-id="523a2-296">PstnGatewayList : {}</span></span>

<span data-ttu-id="523a2-297">Name (имя): Локалрауте</span><span class="sxs-lookup"><span data-stu-id="523a2-297">Name : LocalRoute</span></span>

<span data-ttu-id="523a2-298">Суппресскаллерид:</span><span class="sxs-lookup"><span data-stu-id="523a2-298">SuppressCallerId :</span></span>

<span data-ttu-id="523a2-299">Алтернатекаллерид:</span><span class="sxs-lookup"><span data-stu-id="523a2-299">AlternateCallerId :</span></span>

<span data-ttu-id="523a2-300">Lync Server позволяет создавать маршруты голосовой связи, для которых не используется PSTN, и не указывать шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="523a2-300">Lync Server allows you to create voice routes that do not have a PSTN usage and do not specify a PSTN gateway.</span></span> <span data-ttu-id="523a2-301">Однако вы не можете перенаправлять звонки через голосовой маршрут, для которого не настроены эти два значения свойств.</span><span class="sxs-lookup"><span data-stu-id="523a2-301">However, you can't actually route calls over a voice route that does not have these two property values configured.</span></span> <span data-ttu-id="523a2-302">По этой причине вам может понадобиться периодически запускать эту команду, которая возвращает идентификационные данные любого маршрута голосовой связи, для которого не используется PSTN.</span><span class="sxs-lookup"><span data-stu-id="523a2-302">Because of that, you might find it useful to periodically run this command, which returns the identity of any voice route that does not have a PSTN usage:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnUsages -eq $Null} | Select-Object Identity`

<span data-ttu-id="523a2-303">Аналогичным образом эта команда возвращает идентификационные данные любого маршрута голосовой связи, для которого не настроен шлюз PSTN.</span><span class="sxs-lookup"><span data-stu-id="523a2-303">Similarly, this command returns the identity of any voice route that has not been configured to have a PSTN gateway:</span></span>

`Get-CsVoiceRoute | Where-Object {$_.PstnGatewayList -eq $Null}} | Select-Object Identity`

</div>

<div>

## <a name="check-conferencing-attendant-settings"></a><span data-ttu-id="523a2-304">Проверка параметров помощника по конференциям</span><span class="sxs-lookup"><span data-stu-id="523a2-304">Check Conferencing Attendant settings</span></span>

<span data-ttu-id="523a2-305">Проверьте параметры помощника по конференциям для конференц-связи с телефонным подключением PSTN.</span><span class="sxs-lookup"><span data-stu-id="523a2-305">Check conferencing Attendant settings for PSTN dial-in conferencing.</span></span> <span data-ttu-id="523a2-306">Параметры помощника по конференциям можно получить только с помощью командлета **Get-ксдиалинконференЦингконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="523a2-306">Conferencing Attendant settings can only be retrieved by using the **Get-CsDialInConferencingConfiguration** cmdlet.</span></span> <span data-ttu-id="523a2-307">Эти параметры недоступны на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="523a2-307">These settings are not available in the Lync Server Control Panel.</span></span> <span data-ttu-id="523a2-308">Чтобы просмотреть параметры помощника по конференциям, используйте команду Windows PowerShell, как показано ниже, и возвращающая глобальную коллекцию параметров конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="523a2-308">To view your Conferencing Attendant settings, use a Windows PowerShell command similar to the following, which returns the global collection of Conferencing Attendant settings:</span></span>

`Get-CsDialInConferencingConfiguration -Identity "Global"`

<span data-ttu-id="523a2-309">Обратите внимание, что параметры помощника по конференциям также можно настроить в области сайта.</span><span class="sxs-lookup"><span data-stu-id="523a2-309">Note that Conferencing Attendant settings can also be configured at the site scope.</span></span> <span data-ttu-id="523a2-310">Чтобы получить сведения о всех параметрах помощника по конференциям, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="523a2-310">To return information about all the Conferencing Attendant settings, use this command instead:</span></span>

`Get-CsDialInConferencingConfiguration`

<span data-ttu-id="523a2-311">Командлет Get-КсдиалинконференЦингконфигуратион возвращает данные примерно так:</span><span class="sxs-lookup"><span data-stu-id="523a2-311">The Get-CsDialInConferencingConfiguration cmdlet returns data similar to this:</span></span>

<span data-ttu-id="523a2-312">Идентификация: Глобальная</span><span class="sxs-lookup"><span data-stu-id="523a2-312">Identity : Global</span></span>

<span data-ttu-id="523a2-313">Ентрекситаннаунцементстипе: Усенамес</span><span class="sxs-lookup"><span data-stu-id="523a2-313">EntryExitAnnouncementsType : UseNames</span></span>

<span data-ttu-id="523a2-314">Енабленамерекординг: true</span><span class="sxs-lookup"><span data-stu-id="523a2-314">EnableNameRecording : True</span></span>

<span data-ttu-id="523a2-315">Ентрекситаннаунцементсенабледбидефаулт: false</span><span class="sxs-lookup"><span data-stu-id="523a2-315">EntryExitAnnouncementsEnabledByDefault : False</span></span>

<span data-ttu-id="523a2-316">Если для Ентрекситаннаунцементсенабледбидефаулт задано значение false, объявления конференций отключены.</span><span class="sxs-lookup"><span data-stu-id="523a2-316">If EntryExitAnnouncementsEnabledByDefault is set to False, that means the conferencing announcements are disabled.</span></span> <span data-ttu-id="523a2-317">Чтобы включить объявления входа и выхода, выполните команду Windows PowerShell, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="523a2-317">To enable entry and exit announcements, run a Windows PowerShell command similar to this:</span></span>

`Set-CsDialInConferencingConfiguration -Identity "Global" -EntryExitAnnouncementsEnabledByDefault $True`

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="523a2-318">См. также</span><span class="sxs-lookup"><span data-stu-id="523a2-318">See Also</span></span>


[<span data-ttu-id="523a2-319">Get-CsSipDomain</span><span class="sxs-lookup"><span data-stu-id="523a2-319">Get-CsSipDomain</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsSipDomain)  
[<span data-ttu-id="523a2-320">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="523a2-320">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)  
[<span data-ttu-id="523a2-321">Get-CsService</span><span class="sxs-lookup"><span data-stu-id="523a2-321">Get-CsService</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsService)  
[<span data-ttu-id="523a2-322">Get-CsAccessEdgeConfiguration</span><span class="sxs-lookup"><span data-stu-id="523a2-322">Get-CsAccessEdgeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsAccessEdgeConfiguration)  
[<span data-ttu-id="523a2-323">Get-CsExternalAccessPolicy</span><span class="sxs-lookup"><span data-stu-id="523a2-323">Get-CsExternalAccessPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[<span data-ttu-id="523a2-324">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="523a2-324">Get-CsArchivingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsArchivingConfiguration)  
[<span data-ttu-id="523a2-325">Get-CsCdrConfiguration</span><span class="sxs-lookup"><span data-stu-id="523a2-325">Get-CsCdrConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsCdrConfiguration)  
[<span data-ttu-id="523a2-326">Get-CsQoEConfiguration</span><span class="sxs-lookup"><span data-stu-id="523a2-326">Get-CsQoEConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsQoEConfiguration)  
[<span data-ttu-id="523a2-327">Get-Ксвоицеполици</span><span class="sxs-lookup"><span data-stu-id="523a2-327">Get-CsVoicePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoicePolicy)  
[<span data-ttu-id="523a2-328">Get-CsVoiceRoute</span><span class="sxs-lookup"><span data-stu-id="523a2-328">Get-CsVoiceRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsVoiceRoute)  
[<span data-ttu-id="523a2-329">Get-CsDialInConferencingConfiguration</span><span class="sxs-lookup"><span data-stu-id="523a2-329">Get-CsDialInConferencingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsDialInConferencingConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

