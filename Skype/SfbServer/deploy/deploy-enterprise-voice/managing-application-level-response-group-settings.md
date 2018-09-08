---
title: Управление параметрами группы ответа уровня приложения в Скайп для бизнеса
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Управление параметрами группы ответа уровня приложения, такие как параметры обратного вызова и музыка при удержании, в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 4a44ee8988925025b81eac6bd1ee340a3bbef81b
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "23890945"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a><span data-ttu-id="0e813-103">Управление параметрами группы ответа уровня приложения в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0e813-103">Managing application-level Response Group settings in Skype for Business</span></span>
 
<span data-ttu-id="0e813-104">Управление параметрами группы ответа уровня приложения, такие как параметры обратного вызова и музыка при удержании, в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0e813-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="0e813-105">Конфигурация музыки при удержании по умолчанию, звуковой файл музыки при удержании по умолчанию, длительности периода обратного вызова агента и контекста вызова следующие параметры уровня приложения для приложения группы ответа.</span><span class="sxs-lookup"><span data-stu-id="0e813-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="0e813-106">Для каждого пула можно задать на уровне приложения только один набор параметров.</span><span class="sxs-lookup"><span data-stu-id="0e813-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="0e813-107">Чтобы просмотреть параметры на уровне приложения, командлет **Get-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0e813-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="0e813-108">Для изменения параметров уровня приложения, используйте командлет **Set-CsRgsConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="0e813-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="0e813-p102">Музыкальный файл по умолчанию для режима удержания воспроизводится только в том случае, если не определен настраиваемый музыкальный файл. Контекст вызова доступен только для очередей, назначенных интерактивным рабочим процессам. Если контекст вызова включен, при получении вызова агент может просматривать такие сведения, как время ожидания ответа абонентом или вопросы и ответы в рамках рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="0e813-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="0e813-112">Для изменения параметров уровня приложения группы ответа</span><span class="sxs-lookup"><span data-stu-id="0e813-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="0e813-113">Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.</span><span class="sxs-lookup"><span data-stu-id="0e813-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="0e813-114">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="0e813-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="0e813-115">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="0e813-115">At the command line, run:</span></span>
    
   ```
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="0e813-116">Например:</span><span class="sxs-lookup"><span data-stu-id="0e813-116">For example:</span></span>
    
   ```
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="0e813-p103">Перед тем как указывать звуковой файл, который должен использоваться по умолчанию для режима удержания, нужно импортировать его. Пример:</span><span class="sxs-lookup"><span data-stu-id="0e813-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
   ```
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="0e813-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0e813-119">See also</span></span>

[<span data-ttu-id="0e813-120">Командлет Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="0e813-120">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="0e813-121">Командлет Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="0e813-121">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="0e813-122">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="0e813-122">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)