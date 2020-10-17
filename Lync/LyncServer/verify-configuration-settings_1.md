---
title: Проверка параметров настройки
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e1ad498f25656e01507e55c41d98ff4bb9143b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508416"
---
# <a name="verify-configuration-settings"></a><span data-ttu-id="ad569-102">Проверка параметров настройки</span><span class="sxs-lookup"><span data-stu-id="ad569-102">Verify configuration settings</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad569-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ad569-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ad569-104">После объединения топологии и запуска командлета **Import – CsLegacyConfiguration** убедитесь, что политики и параметры Office Communications Server 2007 R2 были импортированы в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad569-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="ad569-105">В следующей таблице приведены политики и параметры, которые следует проверить.</span><span class="sxs-lookup"><span data-stu-id="ad569-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="ad569-106">Политики и параметры, которые следует проверить после миграции</span><span class="sxs-lookup"><span data-stu-id="ad569-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad569-107">При использовании этой нагрузки:</span><span class="sxs-lookup"><span data-stu-id="ad569-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="ad569-108">Проверьте следующие политики и параметры:</span><span class="sxs-lookup"><span data-stu-id="ad569-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad569-109">Мгновенные сообщения и конференц-связь</span><span class="sxs-lookup"><span data-stu-id="ad569-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="ad569-110">Политика присутствия</span><span class="sxs-lookup"><span data-stu-id="ad569-110">Presence policy</span></span></p>
<p><span data-ttu-id="ad569-111">Политика конференц-связи</span><span class="sxs-lookup"><span data-stu-id="ad569-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad569-112">Конференц-связь с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="ad569-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="ad569-113">Номера для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="ad569-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="ad569-114">Абонентские группы</span><span class="sxs-lookup"><span data-stu-id="ad569-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad569-115">Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="ad569-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="ad569-116">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="ad569-116">Voice policy</span></span></p>
<p><span data-ttu-id="ad569-117">Маршруты голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="ad569-117">Voice routes</span></span></p>
<p><span data-ttu-id="ad569-118">Абонентские группы</span><span class="sxs-lookup"><span data-stu-id="ad569-118">Dial plans</span></span></p>
<p><span data-ttu-id="ad569-119">Параметры использования ТСОП</span><span class="sxs-lookup"><span data-stu-id="ad569-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad569-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="ad569-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="ad569-121">Простые URL-адреса</span><span class="sxs-lookup"><span data-stu-id="ad569-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad569-122">Внешние пользователи</span><span class="sxs-lookup"><span data-stu-id="ad569-122">External users</span></span></p></td>
<td><p><span data-ttu-id="ad569-123">Политики внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="ad569-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad569-124">Архивация</span><span class="sxs-lookup"><span data-stu-id="ad569-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="ad569-125">Политика архивации</span><span class="sxs-lookup"><span data-stu-id="ad569-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="ad569-126">Чтобы проверить политики и параметры</span><span class="sxs-lookup"><span data-stu-id="ad569-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="ad569-127">В среде Office Communications Server 2007 R2 запишите названия абонентских группы (ранее называемые профилями мест), Номера доступа для телефонного подключения (номера телефонов для доступа к конференциям и регионы), маршруты голосовой связи и политики, перечисленные в предыдущей таблице, в дополнение к URL-адресам, используемым для веб-клиента Communicator.</span><span class="sxs-lookup"><span data-stu-id="ad569-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="ad569-128">На сервере переднего плана Lync Server 2013 откройте панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ad569-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="ad569-129">Чтобы проверить импортированные политики конференц-связи, в левой области щелкните **Конференц**-связь, выберите пункт **Политика Конференц**-связи, а затем убедитесь, что все политики конференц-связи в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="ad569-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad569-130">Политика конференц-связи из предыдущих версий Office Communications Server теперь <STRONG>называется политикой Конференц</STRONG> -связи в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad569-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="ad569-131">Кроме того, параметр <STRONG>анонимного партикпантс</STRONG> из предыдущих версий Office Communications Server теперь является параметром политики конференц-связи Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ad569-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad569-132">В Office Communications Server 2007 R2, если политика конференц-связи не настроена на <STRONG>использование для пользователя</STRONG>, импортируются только глобальные параметры политики.</span><span class="sxs-lookup"><span data-stu-id="ad569-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="ad569-133">В этом случае никакие другие политики конференц-связи не импортируются.</span><span class="sxs-lookup"><span data-stu-id="ad569-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad569-134">Если <STRONG>Анонимные участники</STRONG> настроены для <STRONG>применения</STRONG> в политике конференц-связи Office Communications Server 2007 R2, в процессе миграции создаются две политики конференц-связи: один с <STRONG>аллованонимауспартиЦипантсинмитингс</STRONG> , для которого задано <STRONG>значение true</STRONG> , а для параметра <STRONG>аллованонимауспартиЦипантсинмитингс</STRONG> задано <STRONG>значение false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ad569-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="ad569-135">Чтобы проверить импортированные абонентские группы, щелкните **Маршрутизация голосовой связи**, щелкните **Абонентская группа**, затем убедитесь, что все абонентские планы из среды Office Communicator 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="ad569-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad569-136">В Lync Server 2013 <STRONG>профили местоположения</STRONG> теперь называются <STRONG>телефонными планами</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="ad569-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="ad569-137">Чтобы проверить импортированные политики голосовой связи, щелкните **Маршрутизация голосовой связи**, щелкните **Политика голосовой связи**, затем убедитесь, что все политики голосовой связи из среды Office Communicator 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="ad569-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ad569-138">Если политика голосовой связи не настроена для <STRONG>использования на уровне пользователя</STRONG> в среде Office Communications Server 2007 R2, импортируются только глобальные параметры политики.</span><span class="sxs-lookup"><span data-stu-id="ad569-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="ad569-139">В этом случае никакие другие политики голосовой связи не импортируются.</span><span class="sxs-lookup"><span data-stu-id="ad569-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="ad569-140">Чтобы проверить импортированные маршруты голосовой связи, щелкните **Маршрутизация голосовой связи**, щелкните **Маршрут**, затем убедитесь, что все маршруты голосовой связи из среды Office Communicator 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="ad569-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="ad569-141">Чтобы проверить импортированные параметры использования ТСОП, щелкните **Маршрутизация голосовой связи**, щелкните **Использование ТСОП**, затем убедитесь, что параметры использования ТСОП из среды Office Communicator 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="ad569-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="ad569-142">Чтобы проверить импортированные политики внешнего доступа, щелкните **Федерация и внешний доступ**, щелкните **Политика внешнего доступа**, затем убедитесь, что все политики внешнего доступа из среды Office Communicator 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="ad569-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="ad569-143">Чтобы проверить политики архивации, щелкните **мониторинг и архивация**, щелкните **Политика архивации**, а затем убедитесь, что все политики архивирования в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="ad569-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="ad569-144">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ad569-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="ad569-145">Чтобы проверить политики присутствия, введите в командной строке следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ad569-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="ad569-146">Взглянув на имя в параметре **Identity** , убедитесь, что все политики присутствия в среде Office Communications Server 2007 R2 импортированы.</span><span class="sxs-lookup"><span data-stu-id="ad569-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="ad569-147">Чтобы проверить политики и параметры с помощью командлетов</span><span class="sxs-lookup"><span data-stu-id="ad569-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="ad569-148">Откройте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ad569-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="ad569-149">Запустите командлеты в следующей таблице для проверки политик и параметров.</span><span class="sxs-lookup"><span data-stu-id="ad569-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="ad569-150">Синтаксис этих командлетов аналогичен следующему примеру:</span><span class="sxs-lookup"><span data-stu-id="ad569-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="ad569-151">Для получения дополнительных сведений об этих командлетах, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="ad569-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ad569-152">Для этой политики или параметра:</span><span class="sxs-lookup"><span data-stu-id="ad569-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="ad569-153">Используйте следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="ad569-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ad569-154">Политика присутствия</span><span class="sxs-lookup"><span data-stu-id="ad569-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="ad569-155"><strong>Get-CsPresencePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="ad569-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad569-156">Политика конференц-связи</span><span class="sxs-lookup"><span data-stu-id="ad569-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="ad569-157"><strong>Get-CsConferencingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="ad569-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad569-158">Номера для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="ad569-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="ad569-159"><strong>Get — CsDialInConferencingAccessNumber</strong></span><span class="sxs-lookup"><span data-stu-id="ad569-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad569-160">Абонентские группы</span><span class="sxs-lookup"><span data-stu-id="ad569-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="ad569-161"><strong>Get-CsDialPlan</strong></span><span class="sxs-lookup"><span data-stu-id="ad569-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad569-162">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="ad569-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="ad569-163"><strong>Get-CsVoicePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="ad569-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad569-164">Маршруты голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="ad569-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="ad569-165"><strong>Get — Ксвоицерауте</strong></span><span class="sxs-lookup"><span data-stu-id="ad569-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad569-166">Использование ТСОП</span><span class="sxs-lookup"><span data-stu-id="ad569-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="ad569-167"><strong>Get — Кспстнусаже</strong></span><span class="sxs-lookup"><span data-stu-id="ad569-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad569-168">URL-адреса</span><span class="sxs-lookup"><span data-stu-id="ad569-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="ad569-169"><strong>Get — CsSimpleUrlConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="ad569-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ad569-170">Политики внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="ad569-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="ad569-171"><strong>Get-CsExternalAccessPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="ad569-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ad569-172">Политика архивации</span><span class="sxs-lookup"><span data-stu-id="ad569-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="ad569-173"><strong>Get — CsArchivingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="ad569-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

