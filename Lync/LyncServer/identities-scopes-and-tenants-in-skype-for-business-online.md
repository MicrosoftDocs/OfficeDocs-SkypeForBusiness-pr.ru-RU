---
title: Удостоверения, области и клиенты в Skype для бизнеса Online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b08c459f64a4655ebb4dc670255645f985452aa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a><span data-ttu-id="0ebd5-102">Удостоверения, области и клиенты в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="0ebd5-102">Identities, scopes, and tenants in Skype for Business Online</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0ebd5-103">_**Тема последнего изменения:** 2015-03-09_</span><span class="sxs-lookup"><span data-stu-id="0ebd5-103">_**Topic Last Modified:** 2015-03-09_</span></span>

<span data-ttu-id="0ebd5-104">Многие командлеты Windows PowerShell, которые используются для управления Skype для бизнеса Online, должны быть особенно специфичными для элемента, который вы пытаетесь управлять.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-104">Many of the Windows PowerShell cmdlets used to manage Skype for Business Online require you to be very specific about the item that you are trying to manage.</span></span> <span data-ttu-id="0ebd5-105">Например, при запуске командлета [Set-ксусеракп](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) необходимо указать пользователя, которому вы пытаетесь управлять.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-105">For example, when you run the [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) cmdlet, you must indicate which user you are trying to manage.</span></span> <span data-ttu-id="0ebd5-106">Это имеет смысл.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-106">This makes sense.</span></span> <span data-ttu-id="0ebd5-107">Если вы явным образом не указываете на командлет, для которого нужно управлять учетной записью пользователя, командлет **Set-ксусеракп** не имеет представления о том, какие сведения о голосовой Конференции нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-107">Unless you specifically tell the cmdlet which user account to manage, the **Set-CsUserAcp** cmdlet has no idea which user’s audio conferencing information should be modified.</span></span> <span data-ttu-id="0ebd5-108">По этой причине каждый раз, когда вы запускаете командлет **Set-ксусеракп** , необходимо включить параметр Identity, а затем удостоверение учетной записи пользователя, которую нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-108">For this reason, each time you run the **Set-CsUserAcp** cmdlet, you’ll need to include the Identity parameter, followed by the Identity of the user account to be modified:</span></span>

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

<span data-ttu-id="0ebd5-109">Если *Идентификация* термина всегда известна с учетной записью пользователя, это может привести к путанице.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-109">If the term *Identity* always referred to the Identity of a user account, there would be little cause for confusion.</span></span> <span data-ttu-id="0ebd5-110">При работе с людьми (пользователями, контактами и т. д.) удостоверения сами ссылаются на отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-110">When you are dealing with people (users, contacts, and so on), Identities refer to the individual users themselves.</span></span> <span data-ttu-id="0ebd5-111">Тем не менее, в элементах, кроме учетных записей пользователей, также есть удостоверения.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-111">However, items other than user accounts also have Identities.</span></span> <span data-ttu-id="0ebd5-112">При работе с компонентами службы Skype для бизнеса Online (политики, параметры настройки и т. д.) термин "Идентификация" означает нечто немного другого.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-112">When you are dealing with components of the Skype for Business Online service—policies, configuration settings, and so on—the term Identity means something slightly different.</span></span> <span data-ttu-id="0ebd5-113">Например, можно использовать следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0ebd5-113">For example, consider this command:</span></span>

    Get-CsMeetingConfiguration -Identity "global"

<span data-ttu-id="0ebd5-114">В этом случае удостоверение "Global" относится к области параметров конфигурации собрания.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-114">In this case, the Identity "global" refers to the scope of the meeting configuration settings.</span></span> <span data-ttu-id="0ebd5-115">*Область действия* — это термин, который используется в Skype для бизнеса Online (и в Lync Server) для обозначения сфер управления.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-115">*Scope* is a term used in Skype for Business Online (and in Lync Server) to designate spheres of management.</span></span> <span data-ttu-id="0ebd5-116">По умолчанию политики и параметры всегда имеют глобальную область.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-116">By default, policies and settings always have a global scope.</span></span> <span data-ttu-id="0ebd5-117">При первой настройке учетной записи Skype для бизнеса Online вы будете по умолчанию коллекцией глобальных политик и параметров — глобальных параметров конфигурации собраний, глобальных политик внешнего доступа, глобальных абонентов и т. д.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-117">When you first set up your Skype for Business Online account you'll have, by default, a collection of global policies and settings—global meeting configuration settings, a global external access policy, a global dial plan, and so on.</span></span>

<span data-ttu-id="0ebd5-118">Эти глобальные политики и параметры были введены в Microsoft Lync Server 2010, чтобы убедиться в том, что все пользователи и все компоненты всегда могли бы управлять ими.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-118">These global policies and settings were introduced in Microsoft Lync Server 2010 to help ensure that all users and all components would always, in some way, be managed.</span></span> <span data-ttu-id="0ebd5-119">В Microsoft Office Communicator 2007 R2 это не всегда верно.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-119">This was not necessarily true in Microsoft Office Communicator 2007 R2.</span></span> <span data-ttu-id="0ebd5-120">В зависимости от того, как вы обращались к системе, вы могли бы завершить работу в значительном неуправляемом состоянии (как правило, поскольку групповая политика не применяется к вашей учетной записи пользователя).</span><span class="sxs-lookup"><span data-stu-id="0ebd5-120">Depending on how you accessed the system, you could potentially end up in a largely unmanaged state (typically, because Group Policy could not be applied to your user account).</span></span> <span data-ttu-id="0ebd5-121">Напротив, в Lync Server и в Skype для бизнеса Online ничего не остается неуправляемым.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-121">In contrast, in Lync Server and in Skype for Business Online, nothing is ever left unmanaged.</span></span> <span data-ttu-id="0ebd5-122">Это связано с тем, что вместо каких-либо других параметров будут всегда применяться глобальные политики и параметры.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-122">This is because, in lieu of anything else, global policies and settings will always be enforced.</span></span>

<span data-ttu-id="0ebd5-123">Что означает "вместо чего-нибудь еще?</span><span class="sxs-lookup"><span data-stu-id="0ebd5-123">What do we mean by "in lieu of anything else"?</span></span> <span data-ttu-id="0ebd5-124">В случае Skype для бизнеса Online вы можете создавать политики в *области тегов*или в сфере управления.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-124">Well, in the case of Skype for Business Online, it’s possible to create policies at the *tag scope*, or sphere of management.</span></span> <span data-ttu-id="0ebd5-125">Политики, созданные на основе области тега (также называемой *областью "на пользователя*"), имеют приоритет перед политиками, созданными в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-125">Policies created at the tag scope (also known as *the per-user scope*) take priority over policies created at the global scope.</span></span> <span data-ttu-id="0ebd5-126">Другими словами, политика для каждого пользователя всегда будет иметь приоритет над глобальной политикой.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-126">In other words, a per-user policy will always take precedence over a global policy.</span></span> <span data-ttu-id="0ebd5-127">Например, у вас может быть две политики доступа внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-127">For example, you might have two external user access policies.</span></span> <span data-ttu-id="0ebd5-128">Глобальная политика запрещает пользователям общаться с пользователями, у которых есть учетные записи общего доступа к мгновенным сообщениям (например, Windows Live).</span><span class="sxs-lookup"><span data-stu-id="0ebd5-128">The global policy prohibits users from communicating with people who have accounts on public instant messaging (IM) providers, such as Windows Live.</span></span> <span data-ttu-id="0ebd5-129">Политика "на пользователя", АлловпублиЦимкоммуникатион, позволяет общаться с общедоступными поставщиками обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-129">The per-user policy, AllowPublicIMCommunication, allows communication with public IM providers.</span></span>

<span data-ttu-id="0ebd5-130">Кроме того, у вас может быть два пользователя: Кен мер и почтового Вронский.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-130">You might also have two users: Ken Myer and Pilar Ackerman.</span></span> <span data-ttu-id="0ebd5-131">Кен мер назначил политику "на пользователя".</span><span class="sxs-lookup"><span data-stu-id="0ebd5-131">Ken Myer has been assigned the per-user policy.</span></span> <span data-ttu-id="0ebd5-132">Почтового Вронский не назначена политика для пользователей; то есть она управляется глобальной политикой внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-132">Pilar Ackerman has not been assigned a per-user policy; that is, she is managed by the global external access policy.</span></span> <span data-ttu-id="0ebd5-133">В приведенной ниже таблице показано, какие пользователи могут взаимодействовать с общедоступными поставщиками мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-133">The following table shows which user (if any) can communicate with public IM providers:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0ebd5-134">Параметры политики</span><span class="sxs-lookup"><span data-stu-id="0ebd5-134">Policy Settings</span></span></th>
<th><span data-ttu-id="0ebd5-135">Ken Myer</span><span class="sxs-lookup"><span data-stu-id="0ebd5-135">Ken Myer</span></span></th>
<th><span data-ttu-id="0ebd5-136">Pilar Ackerman</span><span class="sxs-lookup"><span data-stu-id="0ebd5-136">Pilar Ackerman</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0ebd5-137">Глобальный параметр политики для общедоступных служб обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="0ebd5-137">Global policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="0ebd5-138">Нет</span><span class="sxs-lookup"><span data-stu-id="0ebd5-138">No</span></span></p></td>
<td><p><span data-ttu-id="0ebd5-139">Нет</span><span class="sxs-lookup"><span data-stu-id="0ebd5-139">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0ebd5-140">Параметр политики для каждого пользователя для общедоступных служб обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="0ebd5-140">Per-user policy setting for public IM providers</span></span></p></td>
<td><p><span data-ttu-id="0ebd5-141">Да</span><span class="sxs-lookup"><span data-stu-id="0ebd5-141">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ebd5-142">Нет</span><span class="sxs-lookup"><span data-stu-id="0ebd5-142">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0ebd5-143">Пользователь может общаться с поставщиками общедоступного обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="0ebd5-143">User can communicate with public IM providers</span></span></p></td>
<td><p><span data-ttu-id="0ebd5-144">Да</span><span class="sxs-lookup"><span data-stu-id="0ebd5-144">Yes</span></span></p></td>
<td><p><span data-ttu-id="0ebd5-145">Нет</span><span class="sxs-lookup"><span data-stu-id="0ebd5-145">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0ebd5-146">Как видите, Кен мер может взаимодействовать с общедоступными поставщиками мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-146">As you can see, Ken Myer is allowed to communicate with public IM providers.</span></span> <span data-ttu-id="0ebd5-147">Это связано с тем, что параметры политики пользователя, назначенные пользователю, переопределяют параметры в глобальной политике.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-147">This is because the settings in the per-user policy assigned to him override the settings in the global policy.</span></span> <span data-ttu-id="0ebd5-148">Почтового Вронский не может взаимодействовать с общедоступными поставщиками мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-148">Pilar Ackerman cannot communicate with public IM providers.</span></span> <span data-ttu-id="0ebd5-149">Это связано с тем, что она управляется глобальной политикой, а глобальная политика запрещает такую связь.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-149">This is because she is managed by the global policy, and the global policy prohibits such communications.</span></span>

<span data-ttu-id="0ebd5-150">Политики для пользователей должны быть созданы в службе поддержки Office 365.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-150">Per-user policies must be created for you by Office 365 Support.</span></span> <span data-ttu-id="0ebd5-151">После создания политик вы можете назначить их пользователям с помощью соответствующего командлета **Grant-CS** (например, [Grant-ксекстерналакцессполици](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span><span class="sxs-lookup"><span data-stu-id="0ebd5-151">After the policies are created, you can then assign them to users by using the appropriate **Grant-Cs** cmdlet (for example, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)).</span></span> <span data-ttu-id="0ebd5-152">Политики для пользователей легко идентифицировать, так как идентификатор политики всегда начинается с **префикса**тега.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-152">Per-user policies are easy to identify because the policy Identity always begins with the tag **prefix**.</span></span> <span data-ttu-id="0ebd5-153">Например:</span><span class="sxs-lookup"><span data-stu-id="0ebd5-153">For example:</span></span>

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> <span data-ttu-id="0ebd5-154"><STRONG>Префикс</STRONG> тега — это дата, на которую можно перейти в течение первых дней разработки Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-154">The tag <STRONG>prefix</STRONG> dates back to the early development days of Lync Server 2010.</span></span> <span data-ttu-id="0ebd5-155">В этих днях политики для пользователей назывались <EM>политиками тегов</EM> и определяются <STRONG>префиксом</STRONG>тега.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-155">In those days, per-user policies were referred to as <EM>tag policies</EM> and were identified by the tag <STRONG>prefix</STRONG>.</span></span> <span data-ttu-id="0ebd5-156">Эти политики теперь более точно упоминаются как <EM>политики для пользователей</EM>, а область тегов более точно называется <EM>областью</EM>"на пользователя".</span><span class="sxs-lookup"><span data-stu-id="0ebd5-156">These policies are now more accurately referred to as <EM>per-user policies</EM>, and the tag scope is more accurately referred to as the <EM>per-user scope</EM>.</span></span> <span data-ttu-id="0ebd5-157">Тем не менее, по техническим причинам <STRONG>префикс</STRONG> тега не изменился.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-157">However, for technical reasons, the tag <STRONG>prefix</STRONG> was never changed.</span></span>



</div>

<span data-ttu-id="0ebd5-158">Еще один ключевой термин, используемый при работе с Skype для бизнеса Online и Windows PowerShell — *клиент*.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-158">Another key term used when working with Skype for Business Online and Windows PowerShell is *tenant*.</span></span> <span data-ttu-id="0ebd5-159">Когда вы настраиваете учетную запись Skype для бизнеса Online, новому развертыванию назначается ИДЕНТИФИКАЦИОНный номер клиента, который является глобальным уникальным идентификатором (GUID), как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-159">When you set up a Skype for Business Online account, your new deployment is assigned a tenant ID number, which is a globally unique identifier (GUID) similar to this:</span></span>

    bf19b7db-6960-41e5-a139-2aa373474354

<span data-ttu-id="0ebd5-160">Некоторые командлеты Skype для бизнеса Online требуют ввода идентификатора клиента при каждом запуске командлета.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-160">A few of the Skype for Business Online cmdlets require you to enter the tenant ID whenever you run the cmdlet.</span></span> <span data-ttu-id="0ebd5-161">Необходимо ввести идентификатор клиента, даже если вы вошли в систему и у вас есть только один клиент.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-161">You must enter the tenant ID even if you have logged on to, and only have, one tenant.</span></span> <span data-ttu-id="0ebd5-162">К счастью, вам не нужно запоминания идентификатора клиента.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-162">Fortunately, you do not have to memorize the tenant ID.</span></span> <span data-ttu-id="0ebd5-163">Вы можете в любое время получить идентификатор клиента, выполнив следующую команду Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0ebd5-163">You can retrieve your tenant ID at any time by running the following Windows PowerShell command:</span></span>

    Get-CsTenant | Select-Object TenantId

<span data-ttu-id="0ebd5-164">Разумеется, такие аспекты, как разница между глобальной областью и областью пользователя (или областью тега), — это только половина дела.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-164">Of course, knowing things such as the difference between the global scope and the per-user scope (or the tag scope) is only half the battle.</span></span> <span data-ttu-id="0ebd5-165">Также важно знать, когда (или даже если) вы можете использовать эти области.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-165">It’s also important to know when (or even if) you can use these scopes.</span></span> <span data-ttu-id="0ebd5-166">Это справедливо и для идентификаторов, и для параметра клиента.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-166">The same is true for Identities and the tenant parameter.</span></span> <span data-ttu-id="0ebd5-167">В следующих разделах описано, как различные командлеты Skype для бизнеса Online используют удостоверения, области и параметры клиента.</span><span class="sxs-lookup"><span data-stu-id="0ebd5-167">The following topics describe how the different Skype for Business Online cmdlets use Identities, scopes, and the tenant parameter:</span></span>

  - [<span data-ttu-id="0ebd5-168">Командлеты в Skype для бизнеса Online, использующие только глобальную область</span><span class="sxs-lookup"><span data-stu-id="0ebd5-168">Cmdlets in Skype for Business Online that use only the global scope</span></span>](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [<span data-ttu-id="0ebd5-169">Командлеты в Skype для бизнеса Online, использующие глобальную область и область тегов</span><span class="sxs-lookup"><span data-stu-id="0ebd5-169">Cmdlets in Skype for Business Online that use the global scope and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [<span data-ttu-id="0ebd5-170">Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя</span><span class="sxs-lookup"><span data-stu-id="0ebd5-170">Cmdlets in Skype for Business Online that use a user identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [<span data-ttu-id="0ebd5-171">Командлеты в Skype для бизнеса Online, использующие удостоверение пользователя и область тегов</span><span class="sxs-lookup"><span data-stu-id="0ebd5-171">Cmdlets in Skype for Business Online that use a user identity and the tag scope</span></span>](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [<span data-ttu-id="0ebd5-172">Командлеты в Skype для бизнеса Online, в которых используется параметр "клиент"</span><span class="sxs-lookup"><span data-stu-id="0ebd5-172">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [<span data-ttu-id="0ebd5-173">Командлеты в Skype для бизнеса Online с использованием удостоверения поставщика конференц-связи</span><span class="sxs-lookup"><span data-stu-id="0ebd5-173">Cmdlets in Skype for Business Online that use a conferencing provider identity</span></span>](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [<span data-ttu-id="0ebd5-174">Командлеты в Skype для бизнеса Online, не использующие область или удостоверение</span><span class="sxs-lookup"><span data-stu-id="0ebd5-174">Cmdlets in Skype for Business Online that do not use a scope or an identity</span></span>](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

