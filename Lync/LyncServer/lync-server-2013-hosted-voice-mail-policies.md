---
title: 'Lync Server 2013: политики размещенной голосовой почты'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted voice mail policies
ms:assetid: d62a35ed-cbe2-4f06-86b4-e192c18435c1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398932(v=OCS.15)
ms:contentKeyID: 48185506
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a23f5fa67a34d479bbc5b9d5c9bf55071b187c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="9471b-102">Политики размещенной голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9471b-102">Hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9471b-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9471b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9471b-104">*Политика размещенной голосовой почты* предоставляет информацию в приложение Lync Server 2013 ексум о том, где следует перенаправлять звонки для пользователей, чьи почтовые ящики находятся на размещенной службе Exchange.</span><span class="sxs-lookup"><span data-stu-id="9471b-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9471b-105">Политики размещенной голосовой почты являются обязательными только для интеграции Lync Server 2013 с размещенной единой системой обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="9471b-105">Hosted voice mail policies are required only for Lync Server 2013 integration with hosted Exchange UM.</span></span> <span data-ttu-id="9471b-106">Они не требуются для интеграции с локальной UM-системой Exchange.</span><span class="sxs-lookup"><span data-stu-id="9471b-106">They are not needed for integration with on-premises Exchange UM.</span></span>



</div>

<div>

## <a name="hosted-voice-mail-policy-scope"></a><span data-ttu-id="9471b-107">Область политики размещенной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="9471b-107">Hosted Voice Mail Policy Scope</span></span>

<span data-ttu-id="9471b-108">Область политики размещенной голосовой почты определяет уровень иерархии, на котором она действует.</span><span class="sxs-lookup"><span data-stu-id="9471b-108">Hosted voice mail policy scope determines the hierarchical level at which the policy applies.</span></span> <span data-ttu-id="9471b-109">Для политик размещенной голосовой почты можно настроить следующие уровни областей:</span><span class="sxs-lookup"><span data-stu-id="9471b-109">You can configure hosted voice mail policies with the following scope levels:</span></span>

  - <span data-ttu-id="9471b-110">*Глобальная* политика может оказать влияние на всех пользователей, которые находятся в развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9471b-110">The *global* policy can potentially affect all users in the Lync Server 2013 deployment.</span></span> <span data-ttu-id="9471b-111">Если пользователю разрешен доступ к размещенной единой системе обмена сообщениями в UM и вы не назначили политику для пользователя, а политика сайта не назначена на сайт пользователя, применяется Глобальная политика.</span><span class="sxs-lookup"><span data-stu-id="9471b-111">If a user is enabled for hosted Exchange UM access and has not been assigned a per-user policy, and if a site policy has not been assigned to the user’s site, the global policy applies.</span></span> <span data-ttu-id="9471b-112">Глобальная политика устанавливается вместе с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9471b-112">The global policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="9471b-113">Вы можете изменить его в соответствии с вашими потребностями, но переименовать или удалить его будет невозможно.</span><span class="sxs-lookup"><span data-stu-id="9471b-113">You can modify it to meet your needs, but you cannot rename or delete it.</span></span>

  - <span data-ttu-id="9471b-114">Политика *сайта* может повлиять на всех пользователей, которые размещены на сайте, для которого определена политика.</span><span class="sxs-lookup"><span data-stu-id="9471b-114">A *site* policy can affect all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="9471b-115">Если пользователь настроен на доступ к размещенной единой системе обмена сообщениями в UM и для него не назначена политика на уровне пользователя, применяется политика сайта.</span><span class="sxs-lookup"><span data-stu-id="9471b-115">If a user is configured for hosted Exchange UM access and has not been assigned a per-user policy, the site policy applies.</span></span>

  - <span data-ttu-id="9471b-116">Политика *для пользователей* может повлиять только на отдельных пользователей и группы.</span><span class="sxs-lookup"><span data-stu-id="9471b-116">A *per-user* policy can affect only individual users or groups.</span></span> <span data-ttu-id="9471b-117">Чтобы применить политику для каждого пользователя, необходимо явным образом назначить ее отдельным пользователям, группам и контактным объектам.</span><span class="sxs-lookup"><span data-stu-id="9471b-117">To enforce a per-user policy, you must explicitly assign the policy to individual users, groups, and contact objects.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9471b-118">В большинстве случаев требуется только одна политика размещенной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="9471b-118">In most cases, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="9471b-119">Вы часто можете изменить глобальную политику в соответствии с вашими потребностями.</span><span class="sxs-lookup"><span data-stu-id="9471b-119">You can often modify the global policy to meet all your needs.</span></span> <span data-ttu-id="9471b-120">При развертывании нескольких политик размещенной голосовой почты все такие политики имеют область "на пользователя".</span><span class="sxs-lookup"><span data-stu-id="9471b-120">If you deploy multiple hosted voice mail policies, all such policies have per-user scope.</span></span>



</div>

</div>

<div>

## <a name="hosted-voice-mail-policy-attributes"></a><span data-ttu-id="9471b-121">Атрибуты политики размещенной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="9471b-121">Hosted Voice Mail Policy Attributes</span></span>

<span data-ttu-id="9471b-122">Политика голосовой почты определяет два атрибута, которые приложение Ексум (Lync Server 2013) вставляет в URI запроса сообщения INVITE, которое отправляется на размещенную реализацию единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="9471b-122">A voice mail policy defines two attributes that the Lync Server 2013 ExUM Routing application inserts in the request URI of an INVITE message that is sent to the hosted Exchange UM implementation:</span></span>

  - <span data-ttu-id="9471b-123">**Destination (назначение):** Полное доменное имя (FQDN) размещенной службы единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="9471b-123">**Destination:** The fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="9471b-124">Это значение используется локальным пограничным сервером Lync Server для целей маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="9471b-124">This value is used by the on-premises Lync Server Edge Server for routing purposes.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9471b-125">Полное доменное имя Exchange Online — exap.um.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="9471b-125">The FQDN for Exchange Online is exap.um.outlook.com.</span></span>

    
    </div>

  - <span data-ttu-id="9471b-126">**Организация:** Полное доменное имя клиента в размещенной службе единой системы обмена сообщениями, которое применяет почтовые ящики пользователей Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9471b-126">**Organization:** The FQDN of the tenant on the hosted Exchange UM service that homes your Lync Server 2013 users’ mailboxes.</span></span> <span data-ttu-id="9471b-127">Политика голосовой почты может содержать несколько организаций.</span><span class="sxs-lookup"><span data-stu-id="9471b-127">A voice mail policy can contain multiple organizations.</span></span> <span data-ttu-id="9471b-128">Если в политику включена более одной организации, этот атрибут должен представлять собой список клиентов Exchange Server с разделителями-запятыми, в которых содержатся домашние почтовые ящики пользователей Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9471b-128">If more than one organization is included in the policy, this attribute must be a comma-separated list of the Exchange Server tenants that home your Lync Server 2013 user mailboxes.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9471b-129">Администратор клиента размещенной службы UM Exchange предоставит необходимые значения для параметров атрибутов назначения и Организации.</span><span class="sxs-lookup"><span data-stu-id="9471b-129">The tenant administrator of your hosted Exchange UM service will provide the necessary values for your Destination and Organization attribute settings.</span></span> <span data-ttu-id="9471b-130">Чтобы настроить политику, необходимо выполнить командлет New-Кшостедвоицемаилполици или использовать командлет Set-Кшостедвоицемаилполици, чтобы изменить существующий (например, глобальную политику).</span><span class="sxs-lookup"><span data-stu-id="9471b-130">To configure your policy, you must run the New-CsHostedVoicemailPolicy cmdlet or use the Set-CsHostedVoicemailPolicy cmdlet to modify one that exists (for example, the global policy).</span></span>



</div>

<span data-ttu-id="9471b-131">Дополнительные сведения об управлении политиками размещенной голосовой почты можно найти в документации по оболочке Lync Server Management Shell для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="9471b-131">For details about managing hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="9471b-132">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="9471b-132">New-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="9471b-133">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="9471b-133">Set-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="9471b-134">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="9471b-134">Get-CsHostedVoicemailPolicy</span></span>

</div>

<div>

## <a name="per-user-voice-mail-policy-assignment"></a><span data-ttu-id="9471b-135">Назначение политики голосовой почты для каждого пользователя</span><span class="sxs-lookup"><span data-stu-id="9471b-135">Per-User Voice Mail Policy Assignment</span></span>

<span data-ttu-id="9471b-136">Если политика размещенной голосовой почты определена с областью "на пользователя", необходимо явно назначить ее.</span><span class="sxs-lookup"><span data-stu-id="9471b-136">If your hosted voice mail policy is defined with per-user scope, you must explicitly assign it.</span></span> <span data-ttu-id="9471b-137">Командлет Grant-Кшостедвоицемаилполици можно использовать для назначения политики отдельным пользователям или группам.</span><span class="sxs-lookup"><span data-stu-id="9471b-137">You can run the Grant-CsHostedVoicemailPolicy cmdlet to assign the policy to individual users or groups.</span></span>

<span data-ttu-id="9471b-138">Сведения о назначении и удалении политики размещенной голосовой почты для отдельных пользователей можно найти в документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="9471b-138">For details about assigning or removing a per-user hosted voice mail policy, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="9471b-139">Grant-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="9471b-139">Grant-CsHostedVoicemailPolicy</span></span>

  - <span data-ttu-id="9471b-140">Remove-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="9471b-140">Remove-CsHostedVoicemailPolicy</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

