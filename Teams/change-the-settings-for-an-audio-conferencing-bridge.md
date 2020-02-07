---
title: Изменение настроек для моста аудиоконференций
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
description: 'Получите инструкции по изменению параметров для моста конференц-связи, который используется для запроса вызывающих абонентов и сбора имен и контактов для собраний организаторов, если они не пользуются приложениями Skype для бизнеса или Microsoft Teams. '
ms.openlocfilehash: d872bf3d0db2e19089716ab65fc487db601c48ea
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825117"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="98703-103">Изменение настроек для моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="98703-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="98703-104">При настройке голосовой конференции в Office 365 вы будете получать номера телефонов пользователей, которые называются мостом для голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="98703-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="98703-105">Мост конференц-связи может содержать один или несколько номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="98703-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="98703-106">Эти номера телефонов используются для звонков на собрание.</span><span class="sxs-lookup"><span data-stu-id="98703-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="98703-107">Номер телефона будет находиться в нижней части приглашения на собрание Skype для бизнеса или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="98703-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="98703-108">Мост конференц-связи отвечает на вызов и предлагает вызывающему абоненту голосовые запросы с помощью автосекретаря на собрание, а затем, в зависимости от ваших параметров, могут воспроизводить уведомления, запрашивать их имя и управлять параметрами контактов.</span><span class="sxs-lookup"><span data-stu-id="98703-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="98703-109">В организаторов собраний задаются контакты, позволяющие им начинать собрание, когда они не используют приложение Skype для бизнеса или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="98703-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="98703-110">ПИН-код требуется только для организатора собрания, когда пользователь приложения Skype для бизнеса или Microsoft Teams еще не начал собрание.</span><span class="sxs-lookup"><span data-stu-id="98703-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="98703-111">Если все будут звонить на собрание, для организатора собрания требуется ПИН-код для начала собрания.</span><span class="sxs-lookup"><span data-stu-id="98703-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logomediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![Значок, показывающий логотип Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="98703-113">Использование центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="98703-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="98703-114">На панели навигации слева перейдите к**мостам конференций**для **собраний** > .</span><span class="sxs-lookup"><span data-stu-id="98703-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="98703-115">В верхней части страницы **мосты** выберите пункт **Параметры моста**.</span><span class="sxs-lookup"><span data-stu-id="98703-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="98703-116">В области **Параметры моста** выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="98703-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="98703-117">**Уведомления о вводе собрания и выходе** Если вы отключите этот параметр, пользователи, которые уже присоединились к собранию, не будут получать уведомления о входе или выходе из собрания.</span><span class="sxs-lookup"><span data-stu-id="98703-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="98703-118">При включении **уведомлений "запись собрания" и "выход**" можно выбрать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="98703-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="98703-119">**Имена и номера телефонов** Когда пользователи направляются на собрание, номер телефона будет воспроизводиться при присоединении к собранию.</span><span class="sxs-lookup"><span data-stu-id="98703-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="98703-120">**Звуки** При подключении пользователей к собранию звуковой сигнал будет воспроизводиться при присоединении к нему.</span><span class="sxs-lookup"><span data-stu-id="98703-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="98703-121">**Порекомендуйте абонентам записать свое имя, прежде чем присоединиться к собранию** Если вы отключите этот параметр, вызывающим абонентам не будет предложено записать свое имя, прежде чем присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="98703-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="98703-122">Чтобы задать длину PIN-кода для собраний, выберите нужное количество цифр для ПИН-кода в списке **длина ПИН** -кода.</span><span class="sxs-lookup"><span data-stu-id="98703-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="98703-123">Чтобы указать, нужно ли отправлять электронную почту пользователям, включите или отключите **автоматическую отправку сообщений пользователям при изменении конфигурации голосовой конференции**.</span><span class="sxs-lookup"><span data-stu-id="98703-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="98703-124">Просмотр [сообщений, которые автоматически отправляются пользователям при изменении параметров голосовой конференции в Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) или [сообщений электронной почты, отправляемых пользователям, при изменении их параметров в Skype для бизнеса Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="98703-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="98703-125">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="98703-125">Click **Save**.</span></span> 


## <a name="an-icon-showing-the-skype-for-business-logomediasfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![Значок, показывающий логотип Skype для бизнеса](media/sfb-logo-30x30.png)  <span data-ttu-id="98703-127">Использование Центра администрирования Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="98703-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="98703-128">**Настройка процесса собрания, когда абоненты присоединяются к собранию**</span><span class="sxs-lookup"><span data-stu-id="98703-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="98703-129">В **центре администрирования Skype для бизнеса**на панели навигации слева перейдите к**параметрам моста** **видеоконференций** > Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98703-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="98703-130">На странице **Параметры моста Microsoft** в разделе **Присоединение к собранию**выберите:</span><span class="sxs-lookup"><span data-stu-id="98703-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
   - <span data-ttu-id="98703-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="98703-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="98703-132">Если снять этот флажок, пользователи, которые уже присоединились к собранию, не будут получать уведомления о входе или выходе из собрания.</span><span class="sxs-lookup"><span data-stu-id="98703-132">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
   - <span data-ttu-id="98703-133">Если вы установите флажок **включить уведомления о входе и выходе для собрания**, вы можете выбрать эти параметры из списка **Тип объявления входа и выхода** :</span><span class="sxs-lookup"><span data-stu-id="98703-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
   - <span data-ttu-id="98703-134">**Имена и номера телефонов** Когда пользователи направляются на собрание, номер телефона будет воспроизводиться при присоединении к собранию.</span><span class="sxs-lookup"><span data-stu-id="98703-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="98703-135">**Звуки** При подключении пользователей к собранию звуковой сигнал будет воспроизводиться при присоединении к нему.</span><span class="sxs-lookup"><span data-stu-id="98703-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
   - <span data-ttu-id="98703-136">**Порекомендуйте абонентам записать свое имя, прежде чем присоединиться к собранию** Этот параметр выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="98703-136">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="98703-137">Если снять флажок, вызывающим абонентам не будет предложено записать свое имя, прежде чем присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="98703-137">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="98703-138">См. статью **Изменение параметров моста аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="98703-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="98703-139">**Установка длины ПИН-кода для собраний**</span><span class="sxs-lookup"><span data-stu-id="98703-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="98703-140">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="98703-140">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="98703-141">Перейдите в > **Skype для бизнеса**в **центре администрирования Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="98703-141">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="98703-142">В **центре администрирования Skype для бизнеса**на панели навигации слева перейдите к разделу**Настройка моста** **видеоконференций** > Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98703-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="98703-143">На странице **параметров моста Microsoft** в разделе **Безопасность**введите нужное количество цифр в списке **длина ПИН** -кода, а затем нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="98703-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="98703-144">ПИН-код должен включать в себя от 4 до 12 цифр.</span><span class="sxs-lookup"><span data-stu-id="98703-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="98703-145">**Укажите, нужно ли отправлять электронную почту пользователям.**</span><span class="sxs-lookup"><span data-stu-id="98703-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="98703-146">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="98703-146">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="98703-147">Перейдите в > **Skype для бизнеса**в **центре администрирования Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="98703-147">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="98703-148">В **центре администрирования Skype для бизнеса**на панели навигации слева перейдите к разделу**Настройка моста** **видеоконференций** > Microsoft.</span><span class="sxs-lookup"><span data-stu-id="98703-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="98703-149">На странице **Параметры моста Microsoft** установите или снимите флажок **автоматически отправлять электронные письма пользователям, если их сведения о телефонном подключении изменились**, и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="98703-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="98703-150">Просмотр [сообщений, которые автоматически отправляются пользователям при изменении параметров голосовой конференции в Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) или [сообщений электронной почты, отправляемых пользователям, при изменении их параметров в Skype для бизнеса Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="98703-150">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="98703-151">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="98703-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="98703-152">Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-ксдиалинконференЦингбридже](https://go.microsoft.com/fwlink/?LinkId=617686) .</span><span class="sxs-lookup"><span data-stu-id="98703-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="98703-p107">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="98703-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="98703-156">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="98703-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="98703-157">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="98703-157">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="98703-158">Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности только при использовании центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей.</span><span class="sxs-lookup"><span data-stu-id="98703-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="98703-159">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="98703-159">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="98703-160">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="98703-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="98703-161">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="98703-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="98703-162">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="98703-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="98703-p109">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="98703-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="98703-165">См. также</span><span class="sxs-lookup"><span data-stu-id="98703-165">Related topics</span></span>

[<span data-ttu-id="98703-166">Настройка аудиоконференций для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="98703-166">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="98703-167">Настройка голосовой конференции в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="98703-167">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
