---
title: Управление сопоставлением клавиш для команд DTMF в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: Сводка. Сведения об управлении сопоставлением клавиш двухтональных многочастотных команд (DTMF) в Skype для бизнеса Server.
ms.openlocfilehash: b804c9a0923630f6de3d1b5af2acdda123cc6331
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828099"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a><span data-ttu-id="c38b9-103">Управление сопоставлением клавиш для команд DTMF в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c38b9-103">Manage key mapping for DTMF commands in Skype for Business Server</span></span>
 
<span data-ttu-id="c38b9-104">**Сводка:** Узнайте, как управлять сопоставлением клавиш двухтональных многочастотных команд (DTMF) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c38b9-104">**Summary:** Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype for Business Server.</span></span>
  
<span data-ttu-id="c38b9-105">Пользователи конференц-связи с телефонным подключением могут использовать клавиши на клавиатуре телефона для выполнения команд DTMF.</span><span class="sxs-lookup"><span data-stu-id="c38b9-105">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands.</span></span> <span data-ttu-id="c38b9-106">Команды DTMF позволяют пользователям, подключающимся к конференции по телефону, управлять параметрами конференции (например, включением и отключением звука микрофона или блокированием и снятием блокировки конференции) с помощью клавиатуры телефона.</span><span class="sxs-lookup"><span data-stu-id="c38b9-106">DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> 
  
<span data-ttu-id="c38b9-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration,** **Set-CsDialinConferencingDtmfConfiguration,** and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span><span class="sxs-lookup"><span data-stu-id="c38b9-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**, and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span></span>
  
<span data-ttu-id="c38b9-108">При создании новых параметров DTMF для сайтов параметры сайта имеют приоритет над глобальными.</span><span class="sxs-lookup"><span data-stu-id="c38b9-108">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="c38b9-109">Управление сопоставлением клавиш для команд DTMF</span><span class="sxs-lookup"><span data-stu-id="c38b9-109">Manage the key mapping of DTMF commands</span></span>

1. <span data-ttu-id="c38b9-110">Войдите на компьютер как член группы RTCUniversalServerAdmins или участник роли Cs-ServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c38b9-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="c38b9-111">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="c38b9-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="c38b9-112">Чтобы просмотреть параметры DTMF, используемые для телефонной связи, в командной области запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c38b9-112">To view the DTMF settings used for dial-in conferencing, run the following command at the command prompt :</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. <span data-ttu-id="c38b9-113">Чтобы изменить параметры DTMF, используемые для конференций с телефонной телефонной телефонией, запустите следующий cmdlet и укажите клавишу, которую необходимо нажать для каждого параметра, который требуется изменить:</span><span class="sxs-lookup"><span data-stu-id="c38b9-113">To modify the DTMF settings used for dial-in conferencing, run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. <span data-ttu-id="c38b9-114">(Необязательно) Чтобы создать дополнительные наборы команд DTMF для определенных сайтов, используйте командлет **New-CsDialinConferencingDtmfConfiguration** с удостоверением сайта.</span><span class="sxs-lookup"><span data-stu-id="c38b9-114">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span>
    
<span data-ttu-id="c38b9-115">В следующем примере поменяется клавиша, нажатая для отключения объявлений, и клавиша, нажатая для отключения и отключения звука всех участников.</span><span class="sxs-lookup"><span data-stu-id="c38b9-115">The following example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants.</span></span> <span data-ttu-id="c38b9-116">Поскольку параметр Identity не указан, эти изменения применяются к глобальным настройкам DTMF:</span><span class="sxs-lookup"><span data-stu-id="c38b9-116">Because no Identity is specified, these changes apply to the global DTMF settings:</span></span>
  
```PowerShell
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

<span data-ttu-id="c38b9-117">Дополнительные сведения см. в настройках [Get-CsDialInConferencingDtmfConfiguration,](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps) [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)и [New-CsDialInConferencingDtmfConfiguration.](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c38b9-117">For more information, see [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps), and [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span></span>
  

