---
title: 'Lync Server 2013: изменение глобальной политики размещенной голосовой почты'
description: 'Lync Server 2013: изменение глобальной политики размещенной голосовой почты.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the global hosted voice mail policy
ms:assetid: f059b3ce-a7d8-4ea9-b10b-0052222ec2ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412994(v=OCS.15)
ms:contentKeyID: 48185757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9cd5e16c78049ce79abd936a79b2025a14e45943
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566865"
---
# <a name="modify-the-global-hosted-voice-mail-policy-in-lync-server-2013"></a><span data-ttu-id="38704-103">Изменение глобальной политики размещенной голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38704-103">Modify the global hosted voice mail policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38704-104">_**Последнее изменение темы:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="38704-104">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="38704-105">*Глобальная* политика размещенной голосовой почты устанавливается вместе с Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="38704-105">The *global* hosted voice mail policy is installed with Lync Server 2013.</span></span> <span data-ttu-id="38704-106">Вы можете изменить ее в соответствии со своими требованиями, но переименование или удаление этой политики невозможно.</span><span class="sxs-lookup"><span data-stu-id="38704-106">You can modify it to meet your needs, but you cannot rename or delete it.</span></span> <span data-ttu-id="38704-107">Чтобы изменить глобальную политику, можно использовать командлет Set-CsHostedVoicemailPolicy для присвоения параметрам соответствующих значений для конкретного развертывания.</span><span class="sxs-lookup"><span data-stu-id="38704-107">To modify the global policy, you use the Set-CsHostedVoicemailPolicy cmdlet to set the parameters to appropriate values for your specific deployment.</span></span>

<span data-ttu-id="38704-108">Подробные сведения о командлете [Set – CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) можно найти в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38704-108">For details about the [Set-CsHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsHostedVoicemailPolicy) cmdlet, see the Lync Server Management Shell documentation.</span></span>

<div>

## <a name="to-modify-the-global-hosted-voice-mail-policy"></a><span data-ttu-id="38704-109">Изменение глобальной размещенной политики голосовой почты</span><span class="sxs-lookup"><span data-stu-id="38704-109">To modify the global hosted voice mail policy</span></span>

1.  <span data-ttu-id="38704-110">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="38704-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="38704-111">Выполните командлет Set-CsHostedVoicemailPolicy, чтобы задать параметры глобальной политики для среды.</span><span class="sxs-lookup"><span data-stu-id="38704-111">Run the Set-CsHostedVoicemailPolicy cmdlet to set the global policy parameters for your environment.</span></span> <span data-ttu-id="38704-112">Например, выполните:</span><span class="sxs-lookup"><span data-stu-id="38704-112">For example, run:</span></span>
    
        Set-CsHostedVoicemailPolicy -Destination ExUM.fabrikam.com -Organization "corp1.litwareinc.com"
    
    <span data-ttu-id="38704-113">Так как эта команда не задает параметр Identity политики, интерфейс командной строки Windows PowerShell задает следующие значения в глобальной размещенной политике голосовой почты:</span><span class="sxs-lookup"><span data-stu-id="38704-113">Because this command does not specify the policy’s Identity parameter, Windows PowerShell command-line interface sets the following values on the global hosted voice mail policy:</span></span>
    
      - <span data-ttu-id="38704-p103">**Назначение** — задает полное доменное имя размещенной службы единой системы обмена сообщениями Exchange. Этот параметр является необязательным, но если для политики, назначенной пользователю, этот параметр не задан, и вы пытаетесь активировать размещенную голосовую почту для пользователя, произойдет сбой активации.</span><span class="sxs-lookup"><span data-stu-id="38704-p103">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Exchange UM service. This parameter is optional, but if you attempt to enable a user for hosted voice mail and the user’s assigned policy does not have a Destination value, the enable will fail.</span></span>
    
      - <span data-ttu-id="38704-116">**Организация** — указывает разделенный запятыми список клиентов Exchange, которые пользователи домашней среды Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38704-116">**Organization** specifies a comma-separated list of the Exchange tenants that home Lync Server users.</span></span> <span data-ttu-id="38704-117">Каждый клиент должен быть указан в виде полного доменного имени клиента в размещенной службе Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="38704-117">Each tenant must be specified as the FQDN of that tenant on the hosted Exchange UM service.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38704-p105">В командлете, представленном в предыдущем примере, значение «corp1.litwareinc.com» заменяет любое значение, которое может быть уже представлено в параметре «Организация». Например, если политика уже содержит список организаций с разделителями-запятыми, полный список будет заменен. Если необходимо добавить организацию в список, а не заменять его целиком, выполните команду, аналогичную следующей.</span><span class="sxs-lookup"><span data-stu-id="38704-p105">In the previous example cmdlet, the value “corp1.litwareinc.com” replaces any value that might already be present in the Organization parameter. For example, if the policy already contains a comma-separated list of organizations, the full list would be replaced. If you want to add an organization to the list rather than replace the entire list, run a command similar to the following.</span></span>

    
    </div>
    
        $a = Get-CsHostedVoicemailPolicy
        $a.Organization += ",corp3.litwareinc.com"
        Set-CsHostedVoicemailPolicy -Organization $a.Organization

</div>

</div>

<span> </span>

</div>

</div>

</div>

