---
title: Управление присоединиться к конференции и передачи оповещений в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Сводка: Узнайте, как управление присоединиться к конференции и передачи оповещений в Скайп для Business Server.'
ms.openlocfilehash: 33c20319142608f38451a547687bc1bc9eae47d1
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371590"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="ed066-103">Управление присоединиться к конференции и передачи оповещений в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="ed066-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="ed066-104">**Сводка:** Узнайте, как управление присоединиться к конференции и передачи оповещений в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="ed066-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="ed066-105">При удаленных пользователей присоединиться к или покинуть конференцию, объявлений конференц-связи приложения можно объявить их входные или выйти из, воспроизведения звуковой сигнал или о том, их имена.</span><span class="sxs-lookup"><span data-stu-id="ed066-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="ed066-106">Можно изменить порядок работы оповещений с помощью Скайп для консоли Business Server и командлет **Set-CsDialinConferencing** со следующими параметрами:</span><span class="sxs-lookup"><span data-stu-id="ed066-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="ed066-p102">EnableNameRecording. Определяет, должны ли анонимные участники записать свое имя перед входом в конференцию. По умолчанию используется значение "$true", что означает, что анонимным участникам предлагается указать свое имя при присоединении к конференции. (Прошедшие проверку подлинности участники не записывают свое имя, поскольку используется их отображаемое имя.)</span><span class="sxs-lookup"><span data-stu-id="ed066-p102">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference. The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference. (Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="ed066-p103">EntryExitAnnouncementsEnabledByDefault. Указывает, включены или отключены ли объявления по умолчанию. По умолчанию используется значение "$false". Это означает, что по умолчанию при присоединении или выходе участников никаких объявлений нет. Организатор собрания может переопределить этот параметр при планировании.</span><span class="sxs-lookup"><span data-stu-id="ed066-p103">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default. The default value is "$false," which means that by default there are no announcements when participants join or leave a conference. The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="ed066-p104">EntryExitAnnouncementsType. Указывает действие, выполняемое всякий раз, когда один из участников подключается к конференции, для которой включены объявления, или выходит из нее. Значение по умолчанию — "UseNames", что означает, что воспроизводится объявление, аналогичное следующему: "Кен Майер присоединился к конференции", если объявления включены.</span><span class="sxs-lookup"><span data-stu-id="ed066-p104">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled. The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="ed066-p105">Эти параметры можно настроить в глобальной области или в области узла. Параметры, настроенные в области узла, имеют более высокий приоритет, чем параметры, настроенные в глобальной области.</span><span class="sxs-lookup"><span data-stu-id="ed066-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="ed066-117">Изменение объявлений при присоединении к конференции и выходе из нее</span><span class="sxs-lookup"><span data-stu-id="ed066-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="ed066-118">Войдите на компьютер как член группы  RTCUniversalServerAdmins  или роли  Cs-ServerAdministrator  или  CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="ed066-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="ed066-119">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ed066-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ed066-120">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="ed066-120">Run the following at the command prompt:</span></span>
    
   ```
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="ed066-121">Этот командлет получает сведения о, должны ли участники записать их имя при подключении к конференции, а также Скайп для Business Server реакция при участников присоединиться к или выход из нее конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="ed066-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="ed066-122">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="ed066-122">Run the following at the command prompt:</span></span>
    
   ```
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="ed066-p106">В примере ниже параметры настраиваются в области сайта Redmond. Объявления включены, но у участников не запрашивается имя при подключении к конференции. Когда участники присоединяются к конференции или выходят из нее, воспроизводится звуковой сигнал.</span><span class="sxs-lookup"><span data-stu-id="ed066-p106">In the following example, settings are configured at the site scope for Redmond. Announcements are turned on, but participants are not prompted to say their name when they join a conference. A tone is played when participants enter or leave a conference:</span></span>
  
```
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="ed066-126">Дополнительные сведения, включая синтаксиса и полный список параметров [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)см.</span><span class="sxs-lookup"><span data-stu-id="ed066-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

