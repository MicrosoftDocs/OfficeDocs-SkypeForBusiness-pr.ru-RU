---
title: 'Lync Server 2013: Создание политики размещенной голосовой почты для отдельных пользователей'
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
ms.openlocfilehash: 4e13002fa83215c5c1aade627cb6e7ea86cf0a04
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150698"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-per-user-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="83e8b-102">Создание политики размещенной голосовой почты на уровне пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83e8b-102">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="83e8b-103">_**Последнее изменение темы:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="83e8b-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="83e8b-104">Новая политика *на уровне пользователя* может оказывать влияние только на отдельных пользователей, группы и контактные объекты.</span><span class="sxs-lookup"><span data-stu-id="83e8b-104">A *per-user* policy can only impact individual users, groups, and contact objects.</span></span> <span data-ttu-id="83e8b-105">Для развертывания политики на уровне пользователя необходимо явно назначить политику отдельным пользователям, группам или контактным объектам.</span><span class="sxs-lookup"><span data-stu-id="83e8b-105">To deploy a per-user policy, you must explicitly assign the policy to one or more users, groups, or contact objects.</span></span> <span data-ttu-id="83e8b-106">Дополнительные сведения приведены [в статье назначение политики размещенной голосовой почты для отдельных пользователей в Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span><span class="sxs-lookup"><span data-stu-id="83e8b-106">For details, see [Assign a per-user hosted voice mail policy in Lync Server 2013](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md).</span></span>

<span data-ttu-id="83e8b-107">Дополнительные сведения о работе с размещенными политиками голосовой почты для отдельных пользователей представлены в документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="83e8b-107">For details about working with per-user hosted voice mail policies, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="83e8b-108">New — CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="83e8b-108">New-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="83e8b-109">Set — CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="83e8b-109">Set-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy)

  - [<span data-ttu-id="83e8b-110">Get-CsHostedVoicemailPolicy</span><span class="sxs-lookup"><span data-stu-id="83e8b-110">Get-CsHostedVoicemailPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsHostedVoicemailPolicy)

<div>

## <a name="to-create-a-per-user-hosted-voice-mail-policy"></a><span data-ttu-id="83e8b-111">Создание политики маршрутизации размещенной голосовой почты на уровне пользователя</span><span class="sxs-lookup"><span data-stu-id="83e8b-111">To create a per-user hosted voice mail policy</span></span>

1.  <span data-ttu-id="83e8b-112">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="83e8b-112">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="83e8b-p102">Запустите командлет New-CsHostedVoicemailPolicy для создания политики. Например, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="83e8b-p102">Run the New-CsHostedVoicemailPolicy cmdlet to create the policy. For example, run:</span></span>
    
        New-CsHostedVoicemailPolicy -Identity ExRedmond -Destination ExUM.fabrikam.com -Description "Hosted voice mail policy for Redmond users." -Organization "corp1.litwareinc.com, corp2.litwareinc.com"
    
    <span data-ttu-id="83e8b-115">В этом примере создается политика размещенной голосовой почты на уровне пользователя и задаются следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="83e8b-115">The previous example creates a hosted voice mail policy with per-user scope, and sets the following parameters:</span></span>
    
      - <span data-ttu-id="83e8b-p103">**Удостоверение** — задает уникальный идентификатор для политики, охватывающей указанную область. Для политики на уровне пользователя это значение задается в виде простой строки, например ExRedmond.</span><span class="sxs-lookup"><span data-stu-id="83e8b-p103">**Identity** specifies a unique identifier for the policy, which includes the scope. For a policy with per-user scope, this parameter value is specified as a simple string, for example, ExRedmond.</span></span>
    
      - <span data-ttu-id="83e8b-p104">**Назначение** — задает полное доменное имя размещенной службы единой системы обмена сообщениями Exchange. Этот параметр является необязательным, но если для политики, назначенной пользователю, этот параметр не задан, и вы пытаетесь активировать размещенную голосовую почту для пользователя, произойдет сбой активации.</span><span class="sxs-lookup"><span data-stu-id="83e8b-p104">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="83e8b-120">**Описание** — предоставляет дополнительное описание этой политики.</span><span class="sxs-lookup"><span data-stu-id="83e8b-120">**Description** provides optional descriptive information about the policy.</span></span>
    
      - <span data-ttu-id="83e8b-121">**Организация** — указывает разделенный запятыми список клиентов Exchange, которым пользователи Lync Server 2013 имеют доступ к домашнему серверу.</span><span class="sxs-lookup"><span data-stu-id="83e8b-121">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server 2013 users.</span></span> <span data-ttu-id="83e8b-122">Каждый клиент должен быть указан в виде полного доменного имени клиента в размещенной службе единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="83e8b-122">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="83e8b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="83e8b-123">See Also</span></span>


[<span data-ttu-id="83e8b-124">Назначение политики размещенной голосовой почты на уровне пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="83e8b-124">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

