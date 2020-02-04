---
title: 'Lync Server 2013: Создание политики для размещенной голосовой почты для отдельных пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a per-user hosted voice mail policy
ms:assetid: 39018a7c-e0c3-46a2-be4e-05604ec67a50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425867(v=OCS.15)
ms:contentKeyID: 48183902
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 535515fd11c0cb736b5b6fb4b70d041ea3af8a3c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="d073a-102">Создание политики размещенной голосовой почты для каждого пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d073a-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d073a-103">_**Тема последнего изменения:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="d073a-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="d073a-104">Политика *для пользователей* может влиять только на отдельных пользователей, группы и объекты контактов.</span><span class="sxs-lookup"><span data-stu-id="d073a-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="d073a-105">Чтобы развернуть политику для пользователя, необходимо явно назначить ее одному или нескольким пользователям, группам или контактным объектам.</span><span class="sxs-lookup"><span data-stu-id="d073a-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="d073a-106">Подробности можно найти [в разделе Назначение политики размещенной голосовой почты для отдельных пользователей в Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span><span class="sxs-lookup"><span data-stu-id="d073a-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="d073a-107">Дополнительные сведения о работе с политиками голосовой почты для отдельных пользователей можно найти в документации по оболочки управления Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="d073a-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="d073a-108">New-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="d073a-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="d073a-109">Set-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="d073a-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="d073a-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="d073a-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="d073a-111">Создание политики размещенной голосовой почты для пользователя</span><span class="sxs-lookup"><span data-stu-id="d073a-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="d073a-112">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="d073a-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d073a-113">Запустите командлет New-Кшостедвоицемаилполици, чтобы создать политику.</span><span class="sxs-lookup"><span data-stu-id="d073a-113">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy.</span></span> <span data-ttu-id="d073a-114">Например, выполните командлет:</span><span class="sxs-lookup"><span data-stu-id="d073a-114">For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="d073a-115">В предыдущем примере создается политика размещенной голосовой почты с областью "на пользователя" и устанавливаются следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="d073a-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="d073a-116">**Identity** — уникальный идентификатор для политики, включающий область.</span><span class="sxs-lookup"><span data-stu-id="d073a-116">**Identity** specifies a unique identifier for the policy, which includes the scope.</span></span> <span data-ttu-id="d073a-117">Для политики с областью "на пользователя" Этот параметр указывает на простое строковое значение, например Ексредмонд.</span><span class="sxs-lookup"><span data-stu-id="d073a-117">For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="d073a-118">**Destination** указывает полное доменное имя (FQDN) размещенной службы единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="d073a-118">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service.</span></span> <span data-ttu-id="d073a-119">Этот параметр является необязательным, но при попытке включить пользователя для размещенной голосовой почты и назначенной пользователю политики не может быть задано значение "включить".</span><span class="sxs-lookup"><span data-stu-id="d073a-119">This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="d073a-120">**Описание** — необязательные описательные сведения о политике.</span><span class="sxs-lookup"><span data-stu-id="d073a-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="d073a-121">**Организация** : список клиентов Exchange, разделенных запятыми, которые пользователи Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d073a-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="d073a-122">Каждый клиент должен быть указан в качестве полного доменного имени этого клиента в размещенной службе единой системы обмена сообщениями.</span><span class="sxs-lookup"><span data-stu-id="d073a-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d073a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d073a-123">See Also</span></span>


[<span data-ttu-id="d073a-124">Назначение политики размещенной голосовой почты для отдельных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d073a-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

