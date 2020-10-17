---
title: 'Lync Server 2013: Управление параметрами группы ответа уровня приложения'
description: 'Lync Server 2013: Управление параметрами группы ответа уровня приложения.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing application-level Response Group settings
ms:assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721843(v=OCS.15)
ms:contentKeyID: 49733776
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd362cbe8ce738a16639b89edd79439b564444ee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555275"
---
# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="c32bd-103">Управление параметрами группы ответа уровня приложения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c32bd-103">Managing application-level Response Group settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c32bd-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c32bd-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c32bd-105">Параметры уровня приложения для приложения группы ответа включают используемую по умолчанию конфигурацию музыкальных файлов по умолчанию, используемый по умолчанию звуковой файл музыки, период отсрочки агента удерживаемого абонента и контекстную конфигурацию вызова.</span><span class="sxs-lookup"><span data-stu-id="c32bd-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="c32bd-106">Для каждого пула вы можете определить только один набор параметров уровня приложения.</span><span class="sxs-lookup"><span data-stu-id="c32bd-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="c32bd-107">Чтобы просмотреть эти параметры, используйте командлет **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c32bd-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="c32bd-108">Чтобы изменить их, используйте командлет **Set-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c32bd-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="c32bd-p102">Музыкальный файл по умолчанию для режима удержания воспроизводится только в том случае, если не определен настраиваемый музыкальный файл. Контекст вызова доступен только для очередей, назначенных интерактивным рабочим процессам. Если контекст вызова включен, при получении вызова агент может просматривать такие сведения, как время ожидания ответа абонентом или вопросы и ответы в рамках рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c32bd-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="c32bd-112">Изменение параметров уровня приложения группы ответа</span><span class="sxs-lookup"><span data-stu-id="c32bd-112">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="c32bd-113">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="c32bd-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="c32bd-114">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c32bd-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c32bd-115">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c32bd-115">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="c32bd-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="c32bd-116">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="c32bd-p103">Перед тем как указывать звуковой файл, который должен использоваться по умолчанию для режима удержания, нужно импортировать его. Пример:</span><span class="sxs-lookup"><span data-stu-id="c32bd-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c32bd-119">См. также</span><span class="sxs-lookup"><span data-stu-id="c32bd-119">See Also</span></span>


[<span data-ttu-id="c32bd-120">Get — CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c32bd-120">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="c32bd-121">Set — CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c32bd-121">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="c32bd-122">Import — CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="c32bd-122">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

