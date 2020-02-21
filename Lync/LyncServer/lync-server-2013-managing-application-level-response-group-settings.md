---
title: 'Lync Server 2013: Управление параметрами группы ответа уровня приложения'
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
ms.openlocfilehash: 53d8b89177a69da0df49ebf42f026493742f3352
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185822"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-application-level-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="c3784-102">Управление параметрами группы ответа уровня приложения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3784-102">Managing application-level Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3784-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c3784-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c3784-104">Параметры уровня приложения для приложения группы ответа включают используемую по умолчанию конфигурацию музыкальных файлов по умолчанию, используемый по умолчанию звуковой файл музыки, период отсрочки агента удерживаемого абонента и контекстную конфигурацию вызова.</span><span class="sxs-lookup"><span data-stu-id="c3784-104">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="c3784-105">Для каждого пула вы можете определить только один набор параметров уровня приложения.</span><span class="sxs-lookup"><span data-stu-id="c3784-105">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="c3784-106">Чтобы просмотреть эти параметры, используйте командлет **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c3784-106">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="c3784-107">Чтобы изменить их, используйте командлет **Set-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="c3784-107">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>

<span data-ttu-id="c3784-p102">Музыкальный файл по умолчанию для режима удержания воспроизводится только в том случае, если не определен настраиваемый музыкальный файл. Контекст вызова доступен только для очередей, назначенных интерактивным рабочим процессам. Если контекст вызова включен, при получении вызова агент может просматривать такие сведения, как время ожидания ответа абонентом или вопросы и ответы в рамках рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="c3784-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>

<div>

## <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="c3784-111">Изменение параметров уровня приложения группы ответа</span><span class="sxs-lookup"><span data-stu-id="c3784-111">To modify Response Group application-level settings</span></span>

1.  <span data-ttu-id="c3784-112">Выполните вход в качестве члена группы RTCUniversalServerAdmins или в качестве участника одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="c3784-112">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="c3784-113">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="c3784-113">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c3784-114">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c3784-114">At the command line, run:</span></span>
    
        Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
    
    <span data-ttu-id="c3784-115">Пример:</span><span class="sxs-lookup"><span data-stu-id="c3784-115">For example:</span></span>
    
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
    
    <span data-ttu-id="c3784-p103">Перед тем как указывать звуковой файл, который должен использоваться по умолчанию для режима удержания, нужно импортировать его. Пример:</span><span class="sxs-lookup"><span data-stu-id="c3784-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
        $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
        Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c3784-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c3784-118">See Also</span></span>


[<span data-ttu-id="c3784-119">Get — CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c3784-119">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsConfiguration)  
[<span data-ttu-id="c3784-120">Set — CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="c3784-120">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsConfiguration)  
[<span data-ttu-id="c3784-121">Import — CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="c3784-121">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

