---
title: 'Lync Server 2013: Создание политики размещенной голосовой почты на уровне сайта'
description: 'Lync Server 2013: Создание политики размещенной голосовой почты на уровне сайта.'
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
ms.openlocfilehash: 8cd578359a8d20562e8887b61b86d53332e6f8d8
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578375"
---
# <a name="create-a-site-level-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="07f84-103">Создание политики размещенной голосовой почты на уровне сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07f84-103">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07f84-104">_**Последнее изменение темы:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="07f84-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="07f84-105">Политика *сайта* может повлиять на всех пользователей, размещенных на сайте, для которого определена политика.</span><span class="sxs-lookup"><span data-stu-id="07f84-105">A *site* policy can impact all users that are homed on the site for which the policy is defined.</span></span> <span data-ttu-id="07f84-106">Если пользователь настраивается для доступа к размещенной единой системе обмена сообщениями Exchange и не имеет политики на уровне пользователя, применяется политика сайта.</span><span class="sxs-lookup"><span data-stu-id="07f84-106">If a user is configured for hosted Exchange UM access and has not been assigned a Per-user policy, the site policy applies.</span></span> <span data-ttu-id="07f84-107">Если политика сайта не развернута, применяется Глобальная политика.</span><span class="sxs-lookup"><span data-stu-id="07f84-107">If you have not deployed a site policy, the global policy applies.</span></span>

<span data-ttu-id="07f84-108">Для получения дополнительных сведений о настройке политик сайтов обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="07f84-108">For details about configuring site policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="07f84-109">New — CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="07f84-109">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="07f84-110">Set — CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="07f84-110">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="07f84-111">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="07f84-111">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-site-hosted-voice-mail-policy"></a><span data-ttu-id="07f84-112">Создание политики размещенной голосовой почты сайта</span><span class="sxs-lookup"><span data-stu-id="07f84-112">To create a site hosted voice mail policy</span></span>

1.  <span data-ttu-id="07f84-113">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="07f84-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="07f84-114">Запустите командлет New-CsHostedVoicemailPolicy для создания политики.</span><span class="sxs-lookup"><span data-stu-id="07f84-114">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="07f84-115">Например, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="07f84-115">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity site:Redmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for the Redmond site." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="07f84-116">В этом примере создается политика размещенной голосовой почты с областью сайта, а также задаются следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="07f84-116">This example creates a hosted voice mail policy with site scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="07f84-117">**Удостоверение** — задает уникальный идентификатор для политики, охватывающей указанную область.</span><span class="sxs-lookup"><span data-stu-id="07f84-117">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="07f84-118">Для политики с областью сайта значение параметра Identity должно быть указано в формате `site:` *\<name\>* , например `site:Redmond` .</span><span class="sxs-lookup"><span data-stu-id="07f84-118">For a policy with site scope, the Identity parameter value must be specified in the format `site:`*\<name\>*, for example, `site:Redmond`.</span></span>
    
      - <span data-ttu-id="07f84-p104">**Назначение** — задает полное доменное имя размещенной службы единой системы обмена сообщениями Exchange. Этот параметр является необязательным, но если для политики, назначенной пользователю, этот параметр не задан, и вы пытаетесь активировать размещенную голосовую почту для пользователя, произойдет сбой активации.</span><span class="sxs-lookup"><span data-stu-id="07f84-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="07f84-121">**Описание** — предоставляет дополнительное описание этой политики.</span><span class="sxs-lookup"><span data-stu-id="07f84-121">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="07f84-122">**Организация** — указывает разделенный запятыми список клиентов Exchange, которым пользователи Lync Server 2013 имеют доступ к домашнему серверу.</span><span class="sxs-lookup"><span data-stu-id="07f84-122">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="07f84-123">Каждый клиент должен быть указан в виде полного доменного имени клиента в размещенной службе единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="07f84-123">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

