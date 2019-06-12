---
title: Проверка параметров настройки
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a20b78ac9275657461beb74a7325c0c46e4e40fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848883"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="5ac70-102">Проверка параметров настройки</span><span class="sxs-lookup"><span data-stu-id="5ac70-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5ac70-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5ac70-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5ac70-104">После того как вы объедините топологию и запустите командлет **Import-кслегациконфигуратион** , убедитесь, что политики и параметры Office Communications Server 2007 R2 были импортированы в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ac70-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="5ac70-105">В следующей таблице перечислены политики и параметры, которые необходимо проверить.</span><span class="sxs-lookup"><span data-stu-id="5ac70-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="5ac70-106">Политики и параметры для проверки после миграции</span><span class="sxs-lookup"><span data-stu-id="5ac70-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ac70-107">При использовании этой рабочей нагрузки:</span><span class="sxs-lookup"><span data-stu-id="5ac70-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="5ac70-108">Проверьте следующие политики и параметры.</span><span class="sxs-lookup"><span data-stu-id="5ac70-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ac70-109">Обмен мгновенными сообщениями и конференц-связь</span><span class="sxs-lookup"><span data-stu-id="5ac70-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="5ac70-110">Политика присутствия</span><span class="sxs-lookup"><span data-stu-id="5ac70-110">Presence policy</span></span></p>
<p><span data-ttu-id="5ac70-111">Политика конференц-связи</span><span class="sxs-lookup"><span data-stu-id="5ac70-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac70-112">Конференц-связь с телефонным подключением</span><span class="sxs-lookup"><span data-stu-id="5ac70-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="5ac70-113">Номера доступа для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="5ac70-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="5ac70-114">Абонентские группы</span><span class="sxs-lookup"><span data-stu-id="5ac70-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ac70-115">Корпоративная голосовая связь</span><span class="sxs-lookup"><span data-stu-id="5ac70-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="5ac70-116">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="5ac70-116">Voice policy</span></span></p>
<p><span data-ttu-id="5ac70-117">Маршруты голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="5ac70-117">Voice routes</span></span></p>
<p><span data-ttu-id="5ac70-118">Абонентские группы</span><span class="sxs-lookup"><span data-stu-id="5ac70-118">Dial plans</span></span></p>
<p><span data-ttu-id="5ac70-119">Параметры использования PSTN</span><span class="sxs-lookup"><span data-stu-id="5ac70-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac70-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="5ac70-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="5ac70-121">Простые URL-адреса </span><span class="sxs-lookup"><span data-stu-id="5ac70-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ac70-122">внешние пользователи;</span><span class="sxs-lookup"><span data-stu-id="5ac70-122">External users</span></span></p></td>
<td><p><span data-ttu-id="5ac70-123">Политики внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="5ac70-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac70-124">Архивирование</span><span class="sxs-lookup"><span data-stu-id="5ac70-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="5ac70-125">Политика архивации</span><span class="sxs-lookup"><span data-stu-id="5ac70-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="5ac70-126">Проверка политик и параметров</span><span class="sxs-lookup"><span data-stu-id="5ac70-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="5ac70-127">В среде Office Communications Server 2007 R2 Обратите внимание на названия абонентских планов (прежнее название — профили местоположений) и номера доступа для телефонного подключения (номера телефонов для доступа к конференциям), Голосовые маршруты и политики, указанные в разделе Предыдущая таблица в дополнение к URL-адресам, используемым в Communicator Web Access.</span><span class="sxs-lookup"><span data-stu-id="5ac70-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="5ac70-128">На сервере переднего плана Lync Server 2013 откройте панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5ac70-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="5ac70-129">Чтобы проверить импортированные политики конференц-связи, на левой панели выберите **Конференц**-связь, нажмите кнопку **Политика конференции**и убедитесь, что все политики конференций в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="5ac70-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ac70-130">Политика <STRONG>собраний</STRONG> из предыдущих версий Office Communications Server теперь называется политикой конференц-связи в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ac70-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="5ac70-131">Кроме того, параметр <STRONG>анонимного партикпантс</STRONG> из предыдущих версий Office Communications Server теперь является параметром в политике конференц-связи Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5ac70-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ac70-132">В Office Communications Server 2007 R2, если политика Конференции не настроена на <STRONG>использование для пользователей</STRONG>, импортируются только глобальные параметры политики.</span><span class="sxs-lookup"><span data-stu-id="5ac70-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="5ac70-133">В этой ситуации другие политики Конференции не импортируются.</span><span class="sxs-lookup"><span data-stu-id="5ac70-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ac70-134">Если <STRONG>Анонимные участники</STRONG> настроены на <STRONG>принудительное применение</STRONG> в политике конференц-связи Office Communications Server 2007 R2, во время миграции создаются две политики конференций: один с <STRONG>аллованонимауспартиЦипантсинмитингс</STRONG> , для которого установлено значение <STRONG>True</STRONG> и One с <STRONG>аллованонимауспартиЦипантсинмитингс</STRONG> , для которого задано <STRONG>значение false</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5ac70-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="5ac70-135">Чтобы проверить импортированные абонентские группы, выберите пункт **Маршрутизация голосовых сообщений**, щелкните **абонентская группа**и убедитесь, что все абонентские группы в среде Office Communicator 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="5ac70-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ac70-136">В Lync Server 2013 <STRONG>Профили местоположений</STRONG> теперь называются телефонными <STRONG>планами</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="5ac70-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="5ac70-137">Чтобы проверить импортированные политики голосовой связи, выберите пункт **Маршрутизация голоса**, нажмите кнопку **политика голосовой связи**и убедитесь, что все политики голосовой связи в среде Office Communicator 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="5ac70-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="5ac70-138">Если политика голосовой связи не настроена на <STRONG>использование для пользователей</STRONG> в среде Office Communications Server 2007 R2, импортируются только глобальные параметры политики.</span><span class="sxs-lookup"><span data-stu-id="5ac70-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="5ac70-139">Другие политики голосовой связи в этой ситуации не импортируются.</span><span class="sxs-lookup"><span data-stu-id="5ac70-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="5ac70-140">Для проверки импортированных голосовых маршрутов выберите пункт **Маршрутизация голосовой связи**, нажмите кнопку **маршрут**и убедитесь в том, что все голосовые маршруты в среде Office Communicator 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="5ac70-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="5ac70-141">Чтобы проверить импорт параметров использования PSTN, выберите пункт **Маршрутизация голосовой связи**, выберите **Использование PSTN**и убедитесь, что параметры использования PSTN из среды Office Communicator 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="5ac70-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="5ac70-142">Чтобы проверить импортированные внешние политики доступа, выберите пункт **Федерация и внешний доступ**, нажмите кнопку **Политика внешних доступа**, а затем убедитесь, что все политики доступа в среде Office Communicator 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="5ac70-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="5ac70-143">Чтобы проверить политики архивации, выберите пункт **мониторинг и архивация**, нажмите кнопку **Политика архивации**и убедитесь, что все политики архивации в среде Office Communications Server 2007 R2 включены в список.</span><span class="sxs-lookup"><span data-stu-id="5ac70-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="5ac70-144">Откройте командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5ac70-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="5ac70-145">Чтобы проверить политики присутствия, в командной строке введите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5ac70-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="5ac70-146">Изучив имя в параметре **Identity** , убедитесь в том, что все политики присутствия в среде Office Communications Server 2007 R2 импортированы.</span><span class="sxs-lookup"><span data-stu-id="5ac70-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="5ac70-147">Проверка политик и параметров с помощью командлетов</span><span class="sxs-lookup"><span data-stu-id="5ac70-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="5ac70-148">Откройте командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5ac70-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="5ac70-149">Чтобы проверить политики и параметры, выполните командлеты, приведенные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="5ac70-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="5ac70-150">Синтаксис этих командлетов подобен приведенному ниже примеру.</span><span class="sxs-lookup"><span data-stu-id="5ac70-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="5ac70-151">Чтобы получить подробные сведения об этих командлетах, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5ac70-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5ac70-152">Для этой политики или параметра:</span><span class="sxs-lookup"><span data-stu-id="5ac70-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="5ac70-153">Используйте этот командлет:</span><span class="sxs-lookup"><span data-stu-id="5ac70-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5ac70-154">Политика присутствия</span><span class="sxs-lookup"><span data-stu-id="5ac70-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="5ac70-155"><strong>Get-CsPresencePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="5ac70-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac70-156">Политика конференц-связи</span><span class="sxs-lookup"><span data-stu-id="5ac70-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="5ac70-157"><strong>Get-CsConferencingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="5ac70-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ac70-158">Номера доступа для телефонного подключения</span><span class="sxs-lookup"><span data-stu-id="5ac70-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="5ac70-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span><span class="sxs-lookup"><span data-stu-id="5ac70-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac70-160">Абонентские группы</span><span class="sxs-lookup"><span data-stu-id="5ac70-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="5ac70-161"><strong>Get-CsDialPlan</strong></span><span class="sxs-lookup"><span data-stu-id="5ac70-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ac70-162">Политика голосовой связи</span><span class="sxs-lookup"><span data-stu-id="5ac70-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="5ac70-163"><strong>Get-Ксвоицеполици</strong></span><span class="sxs-lookup"><span data-stu-id="5ac70-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac70-164">Маршруты голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="5ac70-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="5ac70-165"><strong>Get-CsVoiceRoute</strong></span><span class="sxs-lookup"><span data-stu-id="5ac70-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ac70-166">Использование ТСОП</span><span class="sxs-lookup"><span data-stu-id="5ac70-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="5ac70-167"><strong>Get-CsPstnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="5ac70-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac70-168">URL-адреса</span><span class="sxs-lookup"><span data-stu-id="5ac70-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="5ac70-169"><strong>Get-CsSimpleUrlConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="5ac70-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5ac70-170">Политики внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="5ac70-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="5ac70-171"><strong>Get-CsExternalAccessPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="5ac70-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5ac70-172">Политика архивации</span><span class="sxs-lookup"><span data-stu-id="5ac70-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="5ac70-173"><strong>Get-CsArchivingPolicy</strong></span><span class="sxs-lookup"><span data-stu-id="5ac70-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

