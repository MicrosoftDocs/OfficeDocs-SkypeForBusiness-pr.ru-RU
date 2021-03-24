---
title: Управление настройками группы реагирования на уровне приложений в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: aab749a1-fa2d-4ce8-a6c6-ebcfa37ce02a
description: Управление настройками группы реагирования на уровне приложений, такими как параметры "Музыка на удержание" и "Звон", в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 941164fb3a99f62303b45f587b64e7aff9cb1393
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103475"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a><span data-ttu-id="67470-103">Управление настройками группы реагирования на уровне приложений в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="67470-103">Managing application-level Response Group settings in Skype for Business</span></span>
 
<span data-ttu-id="67470-104">Управление настройками группы реагирования на уровне приложений, такими как параметры "Музыка на удержание" и "Звон", в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="67470-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="67470-105">Параметры уровня приложений для приложения Response Group включают конфигурацию музыки на удержание по умолчанию, аудиофайл с музыкой на удержании по умолчанию, период благодати агента и конфигурацию контекста вызовов.</span><span class="sxs-lookup"><span data-stu-id="67470-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="67470-106">Для каждого пула вы можете определить только один набор параметров уровня приложения.</span><span class="sxs-lookup"><span data-stu-id="67470-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="67470-107">Чтобы просмотреть эти параметры, используйте командлет **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="67470-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="67470-108">Чтобы изменить их, используйте командлет **Set-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="67470-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="67470-p102">Музыкальный файл по умолчанию для режима удержания воспроизводится только в том случае, если не определен настраиваемый музыкальный файл. Контекст вызова доступен только для очередей, назначенных интерактивным рабочим процессам. Если контекст вызова включен, при получении вызова агент может просматривать такие сведения, как время ожидания ответа абонентом или вопросы и ответы в рамках рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="67470-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="67470-112">Изменение параметров уровня приложений группы реагирования</span><span class="sxs-lookup"><span data-stu-id="67470-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="67470-113">Войдите в группу RTCUniversalServerAdmins или в качестве члена одной из предопределяемой административной роли, поддерживаемой группой реагирования.</span><span class="sxs-lookup"><span data-stu-id="67470-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="67470-114">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="67470-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="67470-115">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="67470-115">At the command line, run:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="67470-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="67470-116">For example:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="67470-p103">Перед тем как указывать звуковой файл, который должен использоваться по умолчанию для режима удержания, нужно импортировать его. Пример:</span><span class="sxs-lookup"><span data-stu-id="67470-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="67470-119">См. также</span><span class="sxs-lookup"><span data-stu-id="67470-119">See also</span></span>

[<span data-ttu-id="67470-120">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="67470-120">Get-CsRgsConfiguration</span></span>](/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="67470-121">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="67470-121">Set-CsRgsConfiguration</span></span>](/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="67470-122">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="67470-122">Import-CsRgsAudioFile</span></span>](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)