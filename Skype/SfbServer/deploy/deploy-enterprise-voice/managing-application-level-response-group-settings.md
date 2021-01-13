---
title: Управление настройками группы ответа на уровне приложения в Skype для бизнеса
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
description: Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Корпоративная голосовая связь.
ms.openlocfilehash: d41211b83e5ce0c27bb9efe1d3d15a6289ae38fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830789"
---
# <a name="managing-application-level-response-group-settings-in-skype-for-business"></a><span data-ttu-id="6ddac-103">Управление настройками группы ответа на уровне приложения в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6ddac-103">Managing application-level Response Group settings in Skype for Business</span></span>
 
<span data-ttu-id="6ddac-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="6ddac-104">Managing application-level Response Group settings, such as music-on-hold and ringback settings, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="6ddac-105">Параметры уровня приложения для приложения группы ответа включают конфигурацию музыки при удержании по умолчанию, аудиофайл музыки при удержании по умолчанию, льготный период переключения агента и конфигурацию контекста вызова.</span><span class="sxs-lookup"><span data-stu-id="6ddac-105">Application-level settings for Response Group application include the default music-on-hold configuration, the default music-on-hold audio file, the agent ringback grace period, and the call context configuration.</span></span> <span data-ttu-id="6ddac-106">Для каждого пула вы можете определить только один набор параметров уровня приложения.</span><span class="sxs-lookup"><span data-stu-id="6ddac-106">You can define only one set of application-level settings per pool.</span></span> <span data-ttu-id="6ddac-107">Чтобы просмотреть эти параметры, используйте командлет **Get-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6ddac-107">To view application-level settings, use the **Get-CsRgsConfiguration** cmdlet.</span></span> <span data-ttu-id="6ddac-108">Чтобы изменить их, используйте командлет **Set-CsRgsConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="6ddac-108">To modify the application-level settings, use the **Set-CsRgsConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="6ddac-p102">Музыкальный файл по умолчанию для режима удержания воспроизводится только в том случае, если не определен настраиваемый музыкальный файл. Контекст вызова доступен только для очередей, назначенных интерактивным рабочим процессам. Если контекст вызова включен, при получении вызова агент может просматривать такие сведения, как время ожидания ответа абонентом или вопросы и ответы в рамках рабочего процесса.</span><span class="sxs-lookup"><span data-stu-id="6ddac-p102">The default music on hold is played when a call is placed on hold only if no custom music on hold is defined. Call context is available only for queues assigned to interactive workflows. If call context is enabled, an agent can see information such as caller wait time or workflow questions and answers when the call is received.</span></span>
  
### <a name="to-modify-response-group-application-level-settings"></a><span data-ttu-id="6ddac-112">Изменение параметров уровня приложения группы ответа</span><span class="sxs-lookup"><span data-stu-id="6ddac-112">To modify Response Group application-level settings</span></span>

1. <span data-ttu-id="6ddac-113">Войдите как член группы RTCUniversalServerAdmins или как член одной из предопределеных административных ролей, которые поддерживают группу ответа.</span><span class="sxs-lookup"><span data-stu-id="6ddac-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="6ddac-114">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="6ddac-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="6ddac-115">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="6ddac-115">At the command line, run:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity <name of service hosting Response Group> [-AgentRingbackGracePeriod <# seconds until call returns to agent after declined>] [-DefaultMusicOnHoldFile <audio file>] [-DisableCallContext <$true | $false>]
   ```

    <span data-ttu-id="6ddac-116">Пример:</span><span class="sxs-lookup"><span data-stu-id="6ddac-116">For example:</span></span>
    
   ```powershell
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -AgentRingbackGracePeriod 30 -DisableCallContext $false
   ```

    <span data-ttu-id="6ddac-p103">Перед тем как указывать звуковой файл, который должен использоваться по умолчанию для режима удержания, нужно импортировать его. Пример:</span><span class="sxs-lookup"><span data-stu-id="6ddac-p103">To specify an audio file to use as the default music on hold, you need to import the audio file first. For example:</span></span>
    
   ```powershell
   $x = Import-CsRgsAudioFile -Identity "service:ApplicationServer:redmond.contoso.com" -FileName "MusicWhileYouWait.wav" -Content (Get-Content C:\Media\ MusicWhileYouWait.wav -Encoding byte -ReadCount 0)
   Set-CsRgsConfiguration -Identity "service:ApplicationServer:redmond.contoso.com" -DefaultMusicOnHoldFile <$x>
   ```

## <a name="see-also"></a><span data-ttu-id="6ddac-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6ddac-119">See also</span></span>

[<span data-ttu-id="6ddac-120">Get-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="6ddac-120">Get-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="6ddac-121">Set-CsRgsConfiguration</span><span class="sxs-lookup"><span data-stu-id="6ddac-121">Set-CsRgsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csrgsconfiguration?view=skype-ps)
  
[<span data-ttu-id="6ddac-122">Import-CsRgsAudioFile</span><span class="sxs-lookup"><span data-stu-id="6ddac-122">Import-CsRgsAudioFile</span></span>](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
