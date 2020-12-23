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
- seo-marvel-mar2020
description: Изменение параметров моста аудиоконференций, включая уведомления о входе и выходе, воспроизведения имен и номеров телефонов, мелодии звука и запрос на запись имени.
ms.openlocfilehash: acebe42e8dbc5707238975c34ce97961c1493d91
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690915"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="ab287-103">Изменение настроек для моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="ab287-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="ab287-104">При настройке аудиоконференций в Microsoft 365 или Office 365 вы будете получать номера телефонов пользователей с моста аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="ab287-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="ab287-105">Мост конференц-связи может содержать один или несколько телефонных номеров.</span><span class="sxs-lookup"><span data-stu-id="ab287-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="ab287-106">Эти номера телефонов используются для звонков на собрание.</span><span class="sxs-lookup"><span data-stu-id="ab287-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="ab287-107">Номер телефона будет включен в нижнюю часть приглашения на собрание Skype для бизнеса или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ab287-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="ab287-108">Мост для conferencing отвечает на звонок и просит вызывающего человека голосовые подсказки с помощью автозавершенного помощника, а затем в зависимости от параметров может использовать для воспроизведения уведомлений, попросить вызывающего человека записать свое имя и управлять настройками ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="ab287-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="ab287-109">ПИН-записи даются организаторам собраний, чтобы они могли начинать собрания, если они не используют приложение Skype для бизнеса или Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ab287-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="ab287-110">ПИН-код требуется только организатору собрания, если пользователь приложения Skype для бизнеса или Microsoft Teams еще не начал собрание.</span><span class="sxs-lookup"><span data-stu-id="ab287-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="ab287-111">Если кто-то звонит на собрание, организатору собрания необходим ПИН-код, чтобы начать собрание.</span><span class="sxs-lookup"><span data-stu-id="ab287-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="ab287-113">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ab287-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="ab287-114">В области навигации слева перейдите к мостам  >  **конференц-залов собраний.**</span><span class="sxs-lookup"><span data-stu-id="ab287-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="ab287-115">В верхней части страницы **"Конференц-мосты"** щелкните **"Параметры моста".**</span><span class="sxs-lookup"><span data-stu-id="ab287-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="ab287-116">В области **параметров моста** выберите:</span><span class="sxs-lookup"><span data-stu-id="ab287-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="ab287-117">**Уведомления о входе и выходе из собрания** Если отключить эту возможность, пользователи, уже присоединившиеся к собранию, не будут уведомлены о том, что кто-то присоединился к собранию или покинул его.</span><span class="sxs-lookup"><span data-stu-id="ab287-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="ab287-118">Включив уведомления о **входе и выходе** из собрания, вы можете выбрать указанные здесь параметры.</span><span class="sxs-lookup"><span data-stu-id="ab287-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="ab287-119">**Имена или номера телефонов** Когда пользователи присоединяются к собранию по телефону, их номера телефонов будут играть, когда они присоединятся к нему.</span><span class="sxs-lookup"><span data-stu-id="ab287-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="ab287-120">**Мелодии** Когда пользователь присоединяется к собранию по телефонной сети, его мелодия звукового сигнала зазвучит.</span><span class="sxs-lookup"><span data-stu-id="ab287-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="ab287-121">**Попросите звоняющих записать свое имя перед присоединением к собранию** Если отключить эту возможность, то перед тем как присоединяться к собранию, не будет предложено записывать свое имя.</span><span class="sxs-lookup"><span data-stu-id="ab287-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="ab287-122">Чтобы установить длину ПИН-кода для собраний, выберите нужное количество цифр в списке длины **ПИН-кода.**</span><span class="sxs-lookup"><span data-stu-id="ab287-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="ab287-123">Чтобы указать, нужно ли отправлять пользователям электронную почту, включите или отключите функцию автоматической отправки электронных писем пользователям в случае изменения конфигурации **аудиоконференции.**</span><span class="sxs-lookup"><span data-stu-id="ab287-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="ab287-124">Дополнительные сведения см. в сообщениях электронной почты, которые автоматически отправляются пользователям при изменении настроек аудиоконференции в [Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) или электронных писем, от отправленных пользователям при изменении их параметров в Skype для бизнеса [Online.](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)</span><span class="sxs-lookup"><span data-stu-id="ab287-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="ab287-125">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ab287-125">Click **Save**.</span></span> 


## <a name="an-icon-showing-the-skype-for-business-logo--using-the-skype-for-business-admin-center"></a>![Значок с логотипом Skype для бизнеса](media/sfb-logo-30x30.png)  <span data-ttu-id="ab287-127">Использование Центра администрирования Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ab287-127">Using the Skype for Business admin center</span></span>

 <span data-ttu-id="ab287-128">**Настройка окна собрания, когда звоня люди присоединяются к собранию**</span><span class="sxs-lookup"><span data-stu-id="ab287-128">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="ab287-129">В Центре **администрирования Skype для бизнеса** на левой навигации перейдите к настройкам моста аудиоконференции  >  **Майкрософт.**</span><span class="sxs-lookup"><span data-stu-id="ab287-129">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="ab287-130">На странице **параметров моста Microsoft** в области **"Присоединиться к собранию"** выберите:</span><span class="sxs-lookup"><span data-stu-id="ab287-130">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
   - <span data-ttu-id="ab287-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="ab287-131">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="ab287-132">Если его свести, то пользователи, уже присоединившиеся к собранию, не будут уведомлены о том, что кто-то присоединился к собранию или покинул его.</span><span class="sxs-lookup"><span data-stu-id="ab287-132">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
   - <span data-ttu-id="ab287-133">Если включить **уведомления** о входе и выходе из собрания, вы можете выбрать эти параметры в списке типов извещений о входе и **выходе:**</span><span class="sxs-lookup"><span data-stu-id="ab287-133">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
   - <span data-ttu-id="ab287-134">**Имена или номера телефонов** Когда пользователи присоединяются к собранию по телефону, их номера телефонов будут играть, когда они присоединятся к нему.</span><span class="sxs-lookup"><span data-stu-id="ab287-134">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="ab287-135">**Мелодии** Когда пользователь присоединяется к собранию по телефонной сети, его мелодия звукового сигнала зазвучит.</span><span class="sxs-lookup"><span data-stu-id="ab287-135">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
   - <span data-ttu-id="ab287-136">**Попросите звоняющих записать свое имя перед присоединением к собранию** Он выбран по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ab287-136">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="ab287-137">Если этот поле не зафиксировать, то перед тем как присоединяться к собранию, не будет предложено записать свое имя.</span><span class="sxs-lookup"><span data-stu-id="ab287-137">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="ab287-138">См. статью **Изменение параметров моста аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="ab287-138">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="ab287-139">**Настройка длины ПИН-кода для собраний**</span><span class="sxs-lookup"><span data-stu-id="ab287-139">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="ab287-140">Войте свою учетную запись с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ab287-140">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="ab287-141">Перейдите в **Центр администрирования Microsoft 365**  >  **Skype для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="ab287-141">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="ab287-142">В Центре **администрирования Skype для бизнеса** на левой навигации перейдите к настройкам моста аудиоконференции  >  **Майкрософт.**</span><span class="sxs-lookup"><span data-stu-id="ab287-142">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="ab287-143">На странице **параметров** моста Microsoft в области "Безопасность" введите количество цифр ПИН-кода в списке длины **ПИН-кода** и нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="ab287-143">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ab287-144">ПИН-код должен включать в себя от 4 до 12 цифр.</span><span class="sxs-lookup"><span data-stu-id="ab287-144">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="ab287-145">**Выбор отправки электронной почты пользователям**</span><span class="sxs-lookup"><span data-stu-id="ab287-145">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="ab287-146">Войте свою учетную запись с помощью своей учебной или учебной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="ab287-146">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="ab287-147">Перейдите в **Центр администрирования Microsoft 365**  >  **Skype для бизнеса.**</span><span class="sxs-lookup"><span data-stu-id="ab287-147">Go to the **Microsoft 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="ab287-148">В Центре **администрирования Skype для бизнеса** на левой навигации перейдите к настройкам моста аудиоконференции  >  **Майкрософт.**</span><span class="sxs-lookup"><span data-stu-id="ab287-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="ab287-149">На странице **параметров** моста Microsoft выберите или отключите автоматическое отправку электронных писем пользователям в случае изменения данных для телефонного дозвона, а затем нажмите кнопку **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="ab287-149">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="ab287-150">Дополнительные сведения см. в сообщениях электронной почты, которые автоматически отправляются пользователям при изменении настроек аудиоконференции в [Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) или электронных писем, от отправленных пользователям при изменении их параметров в Skype для бизнеса [Online.](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)</span><span class="sxs-lookup"><span data-stu-id="ab287-150">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="ab287-151">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab287-151">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="ab287-152">Чтобы сэкономить время и автоматизировать этот процесс, можно воспользоваться [cmdlet Set-CsDialinConferencingBridge.](https://go.microsoft.com/fwlink/?LinkId=617686)</span><span class="sxs-lookup"><span data-stu-id="ab287-152">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="ab287-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="ab287-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ab287-154">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="ab287-154">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="ab287-155">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="ab287-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ab287-156">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="ab287-156">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="ab287-157">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab287-157">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="ab287-158">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="ab287-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ab287-159">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="ab287-159">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="ab287-160">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ab287-160">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ab287-161">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ab287-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ab287-162">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ab287-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="ab287-p109">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="ab287-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ab287-165">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ab287-165">Related topics</span></span>

[<span data-ttu-id="ab287-166">Настройка аудиоконференций для Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ab287-166">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="ab287-167">Настройка аудиоконференций в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ab287-167">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
