---
title: 'Lync Server 2013: Управление пользователями размещенного сервера Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4a54c4a7a3833fdd31999d7613659f9a35f9732
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504206"
---
# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="664d7-102">Управление пользователями размещенного сервера Exchange в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="664d7-102">Hosted Exchange user management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="664d7-103">_**Последнее изменение темы:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="664d7-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="664d7-104">Для предоставления служб голосовой почты для пользователей Lync Server 2013, чьи почтовые ящики расположены в размещенной службе Exchange, необходимо включить учетные записи пользователей для размещенной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="664d7-104">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="664d7-105">Прежде чем можно будет включить поддержку размещенной голосовой почты для пользователя Lync Server 2013, необходимо развернуть политику размещенной голосовой почты, которая применяется к соответствующей учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="664d7-105">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="664d7-106">Эта политика может задаваться на глобальном уровне, на уровне сайта или на уровне пользователя и применяться к пользователю, которому требуется предоставить голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="664d7-106">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="664d7-107">Дополнительные сведения см. <A href="lync-server-2013-hosted-voice-mail-policies.md">в разделе политики размещенной голосовой почты в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="664d7-107">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="664d7-108">Атрибут msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="664d7-108">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="664d7-109">Lync Server 2013 представляет новый атрибут пользователя с именем **msExchUCVoiceMailSettings**, который создается в рамках подготовки схемы Lync Server 2013 Active Directory.</span><span class="sxs-lookup"><span data-stu-id="664d7-109">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="664d7-110">Этот многозначный атрибут содержит параметры голосовой почты, которые являются общими для Lync Server 2013 и размещенной службы Exchange.</span><span class="sxs-lookup"><span data-stu-id="664d7-110">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="664d7-111">Размещенная служба Exchange может в некоторых случаях устанавливать значение атрибута msExchUCVoiceMailSettings в процессе включения единой системы обмена сообщениями Exchange или в процессе переноса почтовых ящиков на размещенный Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="664d7-111">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="664d7-112">Если этот атрибут не задан Exchange, администратор Lync Server 2013 должен задать его, выполнив командлет Set-CsUser, как описано ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="664d7-112">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="664d7-113">В следующей таблице показаны пары "ключ-значение" для этого атрибута и их авторы.</span><span class="sxs-lookup"><span data-stu-id="664d7-113">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="664d7-114">Пары "ключ-значение" атрибута msExchUCVoiceMailSettings</span><span class="sxs-lookup"><span data-stu-id="664d7-114">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="664d7-115">Значение</span><span class="sxs-lookup"><span data-stu-id="664d7-115">Value</span></span></th>
<th><span data-ttu-id="664d7-116">Автор</span><span class="sxs-lookup"><span data-stu-id="664d7-116">Author</span></span></th>
<th><span data-ttu-id="664d7-117">Смысл</span><span class="sxs-lookup"><span data-stu-id="664d7-117">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="664d7-118">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="664d7-118">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="664d7-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="664d7-119">Exchange</span></span></p></td>
<td><p><span data-ttu-id="664d7-120">Exchange Server предоставил пользователю доступ к размещенной единой системе обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="664d7-120">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="664d7-121">Приложение маршрутизации единой системы обмена сообщениями Exchange будет проверять политику размещенной голосовой почты пользователя для сведений о маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="664d7-121">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="664d7-122">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="664d7-122">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="664d7-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="664d7-123">Exchange</span></span></p></td>
<td><p><span data-ttu-id="664d7-124">Exchange Server запретил пользователю доступ к размещенной единой системе обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="664d7-124">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="664d7-125">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="664d7-125">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="664d7-126">Lync Server</span><span class="sxs-lookup"><span data-stu-id="664d7-126">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="664d7-127">Для пользователя включен доступ к размещенной единой системе обмена сообщениями в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="664d7-127">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="664d7-128">Приложение Lync Server 2013 ExUM Routing будет проверять политику размещенной голосовой почты пользователя для сведений о маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="664d7-128">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="664d7-129">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="664d7-129">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="664d7-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="664d7-130">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="664d7-131">Пользователь отключил доступ к размещенной единой системе обмена сообщениями в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="664d7-131">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="664d7-132">Если атрибут уже содержит значения, отличные от пар "ключ-значение" в Lync Server 2013 (CSHostedVoiceMail = 0 или CSHostedVoiceMail = 1), то предупреждение будет указывать на то, что этот атрибут может управляться другим приложением.</span><span class="sxs-lookup"><span data-stu-id="664d7-132">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="664d7-133">Например, предупреждение отображается в том случае, если пара "ключ-значение" ExchangeHostedVoiceMail=0 или ExchangeHostedVoiceMail=1 уже существует.</span><span class="sxs-lookup"><span data-stu-id="664d7-133">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="664d7-134">В таком случае можно изменить это значение в Active Directory или выполнить следующий командлет, чтобы установить значение NULL:</span><span class="sxs-lookup"><span data-stu-id="664d7-134">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="664d7-135">Set-CsUser –identity user –HostedVoicemail $null</span><span class="sxs-lookup"><span data-stu-id="664d7-135">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="664d7-136">Предоставление пользователям размещенной голосовой почты</span><span class="sxs-lookup"><span data-stu-id="664d7-136">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="664d7-137">Чтобы обеспечить перенаправление вызовов голосовой почты пользователя в размещенную единую систему обмена сообщениями Exchange, необходимо выполнить командлет Set-CsUser для установки значения параметра *HostedVoiceMail*.</span><span class="sxs-lookup"><span data-stu-id="664d7-137">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="664d7-138">Этот параметр также сигнализирует Lync Server 2013, чтобы получить индикатор "позвонить голосовой почте".</span><span class="sxs-lookup"><span data-stu-id="664d7-138">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="664d7-139">В следующем примере учетной записи пользователя Пилар Акерман (Pilar Ackerman) предоставляется размещенная голосовая почта:</span><span class="sxs-lookup"><span data-stu-id="664d7-139">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="664d7-p108">Этот командлет проверяет, применяется ли к этому пользователю политика маршрутизации размещенной голосовой почты (глобально, на уровне сайта или на уровне пользователя). Если политика не применяется, то командлет завершается неудачно.</span><span class="sxs-lookup"><span data-stu-id="664d7-p108">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user. If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="664d7-142">В следующем примере учетная запись пользователя Пилар Акерман (Pilar Ackerman) отключается от размещенной голосовой почты:</span><span class="sxs-lookup"><span data-stu-id="664d7-142">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="664d7-p109">Этот командлет проверяет, применяется ли к этому пользователю политика маршрутизации размещенной голосовой почты (глобально, на уровне сайта или на уровне пользователя). Если политика применяется, то командлет завершается неудачно.</span><span class="sxs-lookup"><span data-stu-id="664d7-p109">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user. If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="664d7-145">Дополнительные сведения об использовании командлета Set-CsUser см в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="664d7-145">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

