---
title: Удостоверения, области и клиенты в Skype для бизнеса Online
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3e5217c4214e6e86ca4c1dff62410c247cf7f8c
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="b4b04-102">Удостоверения, области и клиенты в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="b4b04-102">Identities, scopes, and tenants in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4b04-103">_**Последнее изменение темы:** 2015-03-09_</span><span class="sxs-lookup"><span data-stu-id="b4b04-103">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="b4b04-104">Многие командлеты Windows PowerShell, используемые для управления Skype для бизнеса Online, требуют особой важности об элементе, который вы пытаетесь управлять.</span><span class="sxs-lookup"><span data-stu-id="b4b04-104">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="b4b04-105">Например, при запуске командлета [Set – CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) необходимо указать пользователя, которым вы пытаетесь управлять.</span><span class="sxs-lookup"><span data-stu-id="b4b04-105">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="b4b04-106">Это вполне обоснованно.</span><span class="sxs-lookup"><span data-stu-id="b4b04-106">This makes sense.</span></span> <span data-ttu-id="b4b04-107">Если вы явно не сообщаете командлету, какую учетную запись пользователя необходимо управлять, командлет **Set-CsUserAcp** не имеет представления о том, какие сведения о голосовых конференциях следует изменить.</span><span class="sxs-lookup"><span data-stu-id="b4b04-107">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="b4b04-108">По этой причине при каждом запуске командлета **Set – CsUserAcp** необходимо включить параметр Identity, а затем идентификатор учетной записи пользователя, которую необходимо изменить:</span><span class="sxs-lookup"><span data-stu-id="b4b04-108">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="b4b04-109">Если *идентификатору удостоверения* всегда присвоены сведения об удостоверении учетной записи пользователя, путаницу было бы мало.</span><span class="sxs-lookup"><span data-stu-id="b4b04-109">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="b4b04-110">При работе с людьми (пользователями, контактами и т. д.) удостоверения относятся к отдельным пользователям.</span><span class="sxs-lookup"><span data-stu-id="b4b04-110">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="b4b04-111">Однако у элементов, отличных от учетных записей пользователей, также есть удостоверения.</span><span class="sxs-lookup"><span data-stu-id="b4b04-111">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="b4b04-112">При работе с компонентами службы Skype для бизнеса Online — политиками, параметрами конфигурации и т. д. термин идентификация означает нечто немного другое.</span><span class="sxs-lookup"><span data-stu-id="b4b04-112">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="b4b04-113">Например, рассмотрим следующую команду:</span><span class="sxs-lookup"><span data-stu-id="b4b04-113">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="b4b04-114">В этом случае идентификатор "Global" относится к области параметров конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="b4b04-114">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="b4b04-115">*Область* — термин, используемый в Skype для бизнеса Online (и в Lync Server) для обозначения сферес управления.</span><span class="sxs-lookup"><span data-stu-id="b4b04-115">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="b4b04-116">По умолчанию политики и параметры всегда имеют глобальную область.</span><span class="sxs-lookup"><span data-stu-id="b4b04-116">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="b4b04-117">При первой настройке учетной записи Skype для бизнеса Online у вас будет по умолчанию набор глобальных политик и параметров — глобальные параметры конфигурации собраний, Глобальная политика внешнего доступа, Глобальная абонентская группа и т. д.</span><span class="sxs-lookup"><span data-stu-id="b4b04-117">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="b4b04-118">Эти глобальные политики и параметры были представлены в Microsoft Lync Server 2010, чтобы гарантировать, что все пользователи и все компоненты всегда будут управляться каким бы то ни было образом.</span><span class="sxs-lookup"><span data-stu-id="b4b04-118">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="b4b04-119">В Microsoft Office Communicator 2007 R2 это было не так.</span><span class="sxs-lookup"><span data-stu-id="b4b04-119">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="b4b04-120">В зависимости от того, как вы заменили доступ к системе, вы могли в значительной степени в неуправляемом состоянии (как правило, так как групповая политика не применяется к учетной записи пользователя).</span><span class="sxs-lookup"><span data-stu-id="b4b04-120">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="b4b04-121">В отличие от того, что в Lync Server и Skype для бизнеса Online, ничего не остается неуправляемым.</span><span class="sxs-lookup"><span data-stu-id="b4b04-121">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="b4b04-122">Это вызвано тем, что вместо чего-либо еще все остальные глобальные политики и параметры всегда будут применены.</span><span class="sxs-lookup"><span data-stu-id="b4b04-122">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="b4b04-123">Что означает "вместо чего-нибудь еще"?</span><span class="sxs-lookup"><span data-stu-id="b4b04-123">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="b4b04-124">Кроме того, в случае Skype для бизнеса Online можно создавать политики на уровне *тегов*или в сфере управления.</span><span class="sxs-lookup"><span data-stu-id="b4b04-124">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="b4b04-125">Политики, созданные на уровне тега (также называемые *областью "на пользователя*"), имеют приоритет над политиками, созданными в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="b4b04-125">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="b4b04-126">Другими словами, политика на уровне пользователя всегда будет иметь приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="b4b04-126">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="b4b04-127">Например, у вас могут быть две политики доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="b4b04-127">For example, you might have two external user access policies.</span></span> <span data-ttu-id="b4b04-128">Глобальная политика запрещает пользователям связываться с пользователями, у которых есть учетные записи общедоступных служб обмена мгновенными сообщениями (IM), таких как Windows Live.</span><span class="sxs-lookup"><span data-stu-id="b4b04-128">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="b4b04-129">Политика на уровне пользователя АлловпублиЦимкоммуникатион позволяет обмениваться данными с поставщиками общедоступной системы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="b4b04-129">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="b4b04-130">Кроме того, у вас могут быть два пользователя: Кен Myer и Pilar Ackerman.</span><span class="sxs-lookup"><span data-stu-id="b4b04-130">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="b4b04-131">Кен Myer назначена политика на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="b4b04-131">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="b4b04-132">Pilar Ackerman не назначена политика на уровне пользователя; то есть она управляется глобальной политикой внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="b4b04-132">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="b4b04-133">В приведенной ниже таблице показано, какие пользователи могут обмениваться данными с поставщиками общедоступного обмена мгновенными сообщениями:</span><span class="sxs-lookup"><span data-stu-id="b4b04-133">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b4b04-134">Параметры политики</span><span class="sxs-lookup"><span data-stu-id="b4b04-134">Policy Settings</span></span></th>
<th><span data-ttu-id="b4b04-135">Кен Майер</span><span class="sxs-lookup"><span data-stu-id="b4b04-135">Ken Myer</span></span></th>
<th><span data-ttu-id="b4b04-136">Пилар Аккерман</span><span class="sxs-lookup"><span data-stu-id="b4b04-136">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b4b04-137">Глобальный параметр политики для общедоступных служб обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="b4b04-137">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="b4b04-138">Нет</span><span class="sxs-lookup"><span data-stu-id="b4b04-138">No</span></span></p></td>
<td><p><span data-ttu-id="b4b04-139">Нет</span><span class="sxs-lookup"><span data-stu-id="b4b04-139">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b4b04-140">Параметр политики на уровне пользователя для общедоступных служб обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="b4b04-140">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="b4b04-141">Да</span><span class="sxs-lookup"><span data-stu-id="b4b04-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="b4b04-142">Нет</span><span class="sxs-lookup"><span data-stu-id="b4b04-142">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b4b04-143">Пользователь может общаться с поставщиками общедоступных мгновенных сообщений</span><span class="sxs-lookup"><span data-stu-id="b4b04-143">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="b4b04-144">Да</span><span class="sxs-lookup"><span data-stu-id="b4b04-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="b4b04-145">Нет</span><span class="sxs-lookup"><span data-stu-id="b4b04-145">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="b4b04-146">Как видите, Ken Myer может обмениваться данными с поставщиками общедоступной системы обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="b4b04-146">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="b4b04-147">Это связано с тем, что параметры политики на уровне пользователей, которым назначена эта политика, переопределяют параметры в глобальной политике.</span><span class="sxs-lookup"><span data-stu-id="b4b04-147">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="b4b04-148">Pilar Ackerman не может обмениваться данными с поставщиками общедоступных мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="b4b04-148">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="b4b04-149">Это связано с тем, что она управляется глобальной политикой, а глобальная политика запрещает такое взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="b4b04-149">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="b4b04-150">Политики для отдельных пользователей должны создаваться службой поддержки Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b4b04-150">Per-user policies must be created for you by Microsoft Support.</span></span> <span data-ttu-id="b4b04-151">После создания политик их можно назначить пользователям с помощью соответствующего командлета **Grant-CS** (например, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span><span class="sxs-lookup"><span data-stu-id="b4b04-151">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="b4b04-152">Политики на уровне пользователя легко определить, так как удостоверение политики всегда начинается с **префикса**тега.</span><span class="sxs-lookup"><span data-stu-id="b4b04-152">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="b4b04-153">Пример:</span><span class="sxs-lookup"><span data-stu-id="b4b04-153">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="b4b04-154"><STRONG>Префикс</STRONG> тега даты до первых дней разработки Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="b4b04-154">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="b4b04-155">В эти дни политики на уровне пользователя назывались <EM>политиками тегов</EM> и были определены <STRONG>префиксом</STRONG>тега.</span><span class="sxs-lookup"><span data-stu-id="b4b04-155">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="b4b04-156">Теперь эти политики более точно называются <EM>политиками на уровне пользователя</EM>, а область тегов более точно называется <EM>областью отдельных пользователей</EM>.</span><span class="sxs-lookup"><span data-stu-id="b4b04-156">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="b4b04-157">Однако по техническим причинам <STRONG>префикс</STRONG> тега никогда не изменился.</span><span class="sxs-lookup"><span data-stu-id="b4b04-157">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="b4b04-158">Еще один ключевой термин, используемый при работе со Skype для бизнеса Online и Windows PowerShell — *клиент*.</span><span class="sxs-lookup"><span data-stu-id="b4b04-158">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="b4b04-159">Когда вы настраиваете учетную запись Skype для бизнеса Online, новому развертыванию назначается ИДЕНТИФИКАЦИОНный номер клиента, который является глобальным уникальным идентификатором (GUID), аналогичным следующему:</span><span class="sxs-lookup"><span data-stu-id="b4b04-159">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="b4b04-160">Некоторые командлеты Skype для бизнеса Online требуют ввода идентификатора клиента при каждом запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="b4b04-160">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="b4b04-161">Необходимо ввести идентификатор клиента даже в том случае, если вы выполнили вход в систему и у вас есть только один клиент.</span><span class="sxs-lookup"><span data-stu-id="b4b04-161">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="b4b04-162">К счастью, вам не нужно запоминать идентификатор клиента.</span><span class="sxs-lookup"><span data-stu-id="b4b04-162">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="b4b04-163">Вы можете получить идентификатор клиента в любое время, выполнив следующую команду Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="b4b04-163">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="b4b04-164">Конечно, знание того, как разница между глобальной областью и областью "на пользователя" (или областью тега), состоит только из половины дела.</span><span class="sxs-lookup"><span data-stu-id="b4b04-164">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="b4b04-165">Кроме того, важно знать, когда (или даже если) вы можете использовать эти области.</span><span class="sxs-lookup"><span data-stu-id="b4b04-165">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="b4b04-166">То же самое справедливо для удостоверений и параметра клиента.</span><span class="sxs-lookup"><span data-stu-id="b4b04-166">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="b4b04-167">В следующих разделах описывается использование удостоверений, областей и параметров клиента в различных командлетах Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="b4b04-167">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="b4b04-168">Командлеты в Skype для бизнеса Online, использующие только глобальную область</span><span class="sxs-lookup"><span data-stu-id="b4b04-168">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="b4b04-169">Командлеты в Skype для бизнеса Online, использующие глобальную область и область тегов</span><span class="sxs-lookup"><span data-stu-id="b4b04-169">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="b4b04-170">Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя</span><span class="sxs-lookup"><span data-stu-id="b4b04-170">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="b4b04-171">Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя и область тегов</span><span class="sxs-lookup"><span data-stu-id="b4b04-171">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="b4b04-172">Командлеты в Skype для бизнеса Online, использующие параметр клиента</span><span class="sxs-lookup"><span data-stu-id="b4b04-172">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="b4b04-173">Командлеты в Skype для бизнеса Online с использованием удостоверения поставщика конференц-связи</span><span class="sxs-lookup"><span data-stu-id="b4b04-173">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="b4b04-174">Командлеты в Skype для бизнеса Online, не использующие область или удостоверение</span><span class="sxs-lookup"><span data-stu-id="b4b04-174">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

