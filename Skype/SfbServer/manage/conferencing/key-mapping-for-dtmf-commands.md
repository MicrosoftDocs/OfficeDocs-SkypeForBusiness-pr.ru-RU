---
title: Управление сопоставления клавиш для команд DTMF в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f91e80ee-a587-4a1b-ac8f-12fa102c098c
description: 'Сводка: Сведения об управлении сопоставления клавиш для команд тонального (двухтональный) в Скайп для Business Server.'
ms.openlocfilehash: c745a621704c677ffb36acb4667021e9734ca398
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374880"
---
# <a name="manage-key-mapping-for-dtmf-commands-in-skype-for-business-server"></a><span data-ttu-id="48674-103">Управление сопоставления клавиш для команд DTMF в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="48674-103">Manage key mapping for DTMF commands in Skype for Business Server</span></span>
 
<span data-ttu-id="48674-104">**Сводка:** Сведения об управлении сопоставления клавиш для команд тонального (двухтональный) в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="48674-104">**Summary:** Learn how to manage key mapping of dual-tone multi-frequency (DTMF) commands in Skype for Business Server.</span></span>
  
<span data-ttu-id="48674-p101">Пользователи конференц-связи с телефонным подключением могут использовать клавиши на клавиатуре телефона для выполнения команд DTMF. Команды DTMF позволяют пользователям, подключающимся к конференции по телефону, управлять параметрами конференции (например, включением и отключением звука микрофона или блокированием и снятием блокировки конференции) с помощью клавиатуры телефона.</span><span class="sxs-lookup"><span data-stu-id="48674-p101">Dial-in conferencing users can press keys on the telephone keypad to perform dual-tone multi-frequency (DTMF) commands. DTMF commands enable users who dial in to a conference to control conference settings (such as muting and unmuting themselves or locking and unlocking the conference) by using the keypad on their telephone.</span></span> 
  
<span data-ttu-id="48674-107">Чтобы управлять клавиш, используемые для команд DTMF, используйте Скайп оболочки управления Business Server с **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**и \*\* Новые CsDialinConferencingDtmfConfiguration\*\* командлетов.</span><span class="sxs-lookup"><span data-stu-id="48674-107">To manage the keys used for the DTMF commands, use the Skype for Business Server Management Shell with the **Get-CsDialinConferencingDtmfConfiguration**, **Set-CsDialinConferencingDtmfConfiguration**, and **New-CsDialinConferencingDtmfConfiguration** cmdlets.</span></span>
  
<span data-ttu-id="48674-108">При создании новых параметров DTMF для сайтов эти параметры сайтов имеют приоритет перед глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="48674-108">When you create new DTMF settings for sites, the site settings take precedence over the global settings.</span></span> 

### <a name="manage-the-key-mapping-of-dtmf-commands"></a><span data-ttu-id="48674-109">Управление сопоставлением клавиш для команд DTMF</span><span class="sxs-lookup"><span data-stu-id="48674-109">Manage the key mapping of DTMF commands</span></span>

1. <span data-ttu-id="48674-110">Войдите на компьютер как член группы  RTCUniversalServerAdmins  или роли  Cs-ServerAdministrator  или  CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="48674-110">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="48674-111">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="48674-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="48674-112">Для просмотра параметров DTMF, используемых для конференц-связи с телефонным подключением, выполните следующую команду в окне командной строки:</span><span class="sxs-lookup"><span data-stu-id="48674-112">To view the DTMF settings used for dial-in conferencing, run the following command at the command prompt :</span></span>
    
   ```
   Get-CsDialinConferencingDtmfConfiguration
   ```

4. <span data-ttu-id="48674-113">Для изменения параметров DTMF, используемых для конференц-связи с телефонным подключением, выполните следующий командлет и укажите клавишу, назначаемую каждому параметру, который требуется изменить:</span><span class="sxs-lookup"><span data-stu-id="48674-113">To modify the DTMF settings used for dial-in conferencing, run the following cmdlet and specify the key to be pressed for each option that you want to change:</span></span>
    
   ```
   Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
   [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
   [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
   [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
   [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
   ```

5. <span data-ttu-id="48674-114">(Дополнительно). Чтобы создать дополнительные наборы команд DTMF для конкретных сайтов, используйте командлет **New-CsDialinConferencingDtmfConfiguration**, указав идентификатор сайта.</span><span class="sxs-lookup"><span data-stu-id="48674-114">(Optional) To create additional sets of DTMF commands for specific sites, use the **New-CsDialinConferencingDtmfConfiguration** cmdlet with a site identity.</span></span>
    
<span data-ttu-id="48674-p102">В следующем примере функции клавиш включения и отключения объявлений, а также включения и отключения звука всех участников меняются местами. Поскольку идентификатор не указан, эти изменения применяются к глобальным параметрам DTMF.</span><span class="sxs-lookup"><span data-stu-id="48674-p102">The following example swaps the key that is pressed to enable or disable announcements and the key that is pressed to mute and unmute all participants. Because no Identity is specified, these changes apply to the global DTMF settings:</span></span>
  
```
Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
```

<span data-ttu-id="48674-117">Для получения дополнительных сведений см [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps)и [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="48674-117">For more information, see [Get-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/get-csdialinconferencingdtmfconfiguration?view=skype-ps), [Set-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingdtmfconfiguration?view=skype-ps), and [New-CsDialInConferencingDtmfConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdialinconferencingdtmfconfiguration?view=skype-ps).</span></span>
  

