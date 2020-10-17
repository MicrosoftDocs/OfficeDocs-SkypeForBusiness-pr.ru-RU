---
title: 'Lync Server 2013: Создание политики размещенной голосовой почты на уровне сайта'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site-level hosted voice mail policy
ms:assetid: 145892c8-a6ca-45fb-9e83-786f709dd775
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398216(v=OCS.15)
ms:contentKeyID: 48183481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e23f14b1db7c846d5dbaa0aa6861274a7b6a2611
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501886"
---
# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="8ff7f-102">Создание политики размещенной голосовой почты на уровне сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8ff7f-102">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8ff7f-103">_**Последнее изменение темы:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="8ff7f-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="8ff7f-104">Политика *сайта* может повлиять на всех пользователей, размещенных на сайте, для которого определена политика.</span><span class="sxs-lookup"><span data-stu-id="8ff7f-104">A *site* policy can impact all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="8ff7f-105">Если пользователь настраивается для доступа к размещенной единой системе обмена сообщениями Exchange и не имеет политики на уровне пользователя, применяется политика сайта.</span><span class="sxs-lookup"><span data-stu-id="8ff7f-105">If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies.</span></span> <span data-ttu-id="8ff7f-106">Если политика сайта не развернута, применяется Глобальная политика.</span><span class="sxs-lookup"><span data-stu-id="8ff7f-106">If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="8ff7f-107">Для получения дополнительных сведений о настройке политик сайтов обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="8ff7f-107">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="8ff7f-108">New — CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="8ff7f-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="8ff7f-109">Set — CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="8ff7f-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="8ff7f-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="8ff7f-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="8ff7f-111">Создание политики размещенной голосовой почты сайта</span><span class="sxs-lookup"><span data-stu-id="8ff7f-111">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="8ff7f-112">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="8ff7f-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8ff7f-113">Запустите командлет New-CsHostedVoicemailPolicy для создания политики.</span><span class="sxs-lookup"><span data-stu-id="8ff7f-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="8ff7f-114">Например, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8ff7f-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="8ff7f-115">В этом примере создается политика размещенной голосовой почты с областью сайта, а также задаются следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8ff7f-115">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="8ff7f-116">**Удостоверение** — задает уникальный идентификатор для политики, охватывающей указанную область.</span><span class="sxs-lookup"><span data-stu-id="8ff7f-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="8ff7f-117">Для политики с областью сайта значение параметра Identity должно быть указано в формате `site:` *\<name\>* , например `site:Redmond` .</span><span class="sxs-lookup"><span data-stu-id="8ff7f-117">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="8ff7f-p104">**Назначение** — задает полное доменное имя размещенной службы единой системы обмена сообщениями Exchange. Этот параметр является необязательным, но если для политики, назначенной пользователю, этот параметр не задан, и вы пытаетесь активировать размещенную голосовую почту для пользователя, произойдет сбой активации.</span><span class="sxs-lookup"><span data-stu-id="8ff7f-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="8ff7f-120">**Описание** — предоставляет дополнительное описание этой политики.</span><span class="sxs-lookup"><span data-stu-id="8ff7f-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="8ff7f-121">**Организация** — указывает разделенный запятыми список клиентов Exchange, которым пользователи Lync Server 2013 имеют доступ к домашнему серверу.</span><span class="sxs-lookup"><span data-stu-id="8ff7f-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="8ff7f-122">Каждый клиент должен быть указан в виде полного доменного имени клиента в размещенной службе единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="8ff7f-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

