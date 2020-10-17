---
title: 'Lync Server 2013: политики размещенной голосовой почты'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e72fd57b05e618f03382a19995beaf9c542dc859
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504176"
---
# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="f2899-102">Политики размещенной голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2899-102">Hosted voice mail policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2899-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f2899-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f2899-104">*Политика размещенной голосовой почты* предоставляет сведения для приложения ExUM маршрутизации Lync Server 2013, о том, где следует маршрутизировать вызовы для пользователей, чьи почтовые ящики расположены в размещенной службе Exchange.</span><span class="sxs-lookup"><span data-stu-id="f2899-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2899-105">Политики размещенной голосовой почты необходимы только для интеграции Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="f2899-105">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="f2899-106">Они не требуются для интеграции с локальной единой системой обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="f2899-106">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="f2899-107">Область действия политики маршрутизации размещенной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="f2899-107">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="f2899-p102">Область политики маршрутизации размещенной голосовой почты определяет иерархический уровень, на котором применяется политика. Можно настроить политики маршрутизации размещенной голосовой почты со следующими уровнями области.</span><span class="sxs-lookup"><span data-stu-id="f2899-p102">Hosted voice mail policy scope determines the hierarchical level at which the policy applies. You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="f2899-110">*Глобальная* политика может оказать влияние на всех пользователей в развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2899-110">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="f2899-111">Если для пользователя включен доступ к размещаемой единой системе обмена сообщениями Exchange, ему не назначена политика на пользователя и сайту пользователя не назначена политика сайта, применяется глобальная политика.</span><span class="sxs-lookup"><span data-stu-id="f2899-111">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="f2899-112">Глобальная политика устанавливается вместе с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2899-112">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="f2899-113">Можно изменить ее в соответствии с конкретными потребностями; однако ее нельзя удалить или переименовать.</span><span class="sxs-lookup"><span data-stu-id="f2899-113">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="f2899-p104">Политика *сайта* может влиять на всех пользователей, размещаемых в сайте, для которых определена политика. Если для пользователя настроен доступ к единой системой обмена сообщениями Exchange и ему не назначена политика на пользователя, применяется политика сайта.</span><span class="sxs-lookup"><span data-stu-id="f2899-p104">A *site* policy can affect all users that are homed on the site for which the policy is defined. If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="f2899-p105">Политика *на пользователя* может влиять только на отдельных пользователей или группы. Для применения политики на пользователя необходимо явно назначить политику отдельным пользователям, группам и контактным объектам.</span><span class="sxs-lookup"><span data-stu-id="f2899-p105">A *per-user* policy can affect only individual users or groups. To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2899-p106">Как правило, требуется только одна политика маршрутизации размещенной голосовой почты. Обычно используется глобальная политика, которую изменяют в соответствии с потребностями. При развертывании нескольких политик маршрутизации размещенной голосовой почты все такие политики имеют область действия, ограниченную пользователем.</span><span class="sxs-lookup"><span data-stu-id="f2899-p106">In most cases, only one hosted voice mail policy is required. You can often modify the global policy to meet all your needs. If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="f2899-121">Атрибуты политики маршрутизации размещенной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="f2899-121">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="f2899-122">Политика голосовой почты определяет два атрибута, которые приложение-служба маршрутизации Lync Server 2013 ExUM вставляет в URI запроса сообщения INVITE, которое отправляется в размещенную реализацию единой системы обмена сообщениями Exchange:</span><span class="sxs-lookup"><span data-stu-id="f2899-122">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="f2899-123">**Назначение:** Полное доменное имя размещенной службы единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="f2899-123">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="f2899-124">Это значение используется локальным пограничным сервером Lync Server для целей маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="f2899-124">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f2899-125">Полное доменное имя для Exchange Online — exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="f2899-125">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="f2899-126">**Организация:** Полное доменное имя клиента в размещенной службе единой системы обмена сообщениями Exchange, которое почтовые ящики пользователей Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2899-126">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="f2899-127">Политика голосовой почты может содержать несколько организаций.</span><span class="sxs-lookup"><span data-stu-id="f2899-127">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="f2899-128">Если в политику включено несколько организаций, этот атрибут должен быть списком клиентов Exchange Server с разделителями-запятыми, которые являются домашними почтовыми ящиками пользователей Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f2899-128">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2899-p109">Администратор клиента размещаемой службы единой системы обмена сообщениями Exchange должен предоставить необходимые значения для атрибутов "Назначение" и "Организация". Чтобы настроить политику, необходимо запустить командлет New-CsHostedVoicemailPolicy или использовать командлет Set-CsHostedVoicemailPolicy для изменения существующей политики (например, глобальной политики).</span><span class="sxs-lookup"><span data-stu-id="f2899-p109">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings. To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="f2899-131">Для получения дополнительных сведений об управлении политиками размещенной голосовой почты обратитесь к документации по консоли управления Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="f2899-131">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="f2899-132">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="f2899-132">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="f2899-133">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="f2899-133">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="f2899-134">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="f2899-134">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="f2899-135">Назначение политики голосовой почты на пользователя</span><span class="sxs-lookup"><span data-stu-id="f2899-135">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="f2899-p110">Если политика маршрутизации размещенной голосовой почты определяется для области на пользователя, ее требуется явно назначить. Чтобы назначить политику отдельным пользователям или группам, можно выполнить командлет Grant-CsHostedVoicemailPolicy.</span><span class="sxs-lookup"><span data-stu-id="f2899-p110">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it. You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="f2899-138">Дополнительные сведения о назначении или удалении политики размещенной голосовой почты для отдельных пользователей представлены в документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="f2899-138">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="f2899-139">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="f2899-139">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="f2899-140">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="f2899-140">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

