---
title: Изменение параметров для конференц-связи аудио мост
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Получите действий, необходимых для изменения параметров конференц-канал, используемый для запрашивать абонентов и сбор имена и ПИН-коды для организаторам собрания, когда они не используют Скайп для бизнеса или группами Майкрософт приложений. '
ms.openlocfilehash: 1ab6f5f82d8282f9062439f875ea15d2ab6d7fd5
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="90ae4-103">Изменение параметров для конференц-связи аудио мост</span><span class="sxs-lookup"><span data-stu-id="90ae4-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="90ae4-104">При установке аудиоконференций в Office 365, вы получите номера телефонов для пользователей из называемое звукового конференц-канала.</span><span class="sxs-lookup"><span data-stu-id="90ae4-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="90ae4-105">Конференц-канал может содержать один или несколько номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="90ae4-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="90ae4-106">Эти номера телефонов используются при абонентов телефонное подключение к собранию.</span><span class="sxs-lookup"><span data-stu-id="90ae4-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="90ae4-107">Номер телефона включен в нижней части Скайп для бизнеса или группами Майкрософт приглашение.</span><span class="sxs-lookup"><span data-stu-id="90ae4-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="90ae4-108">Конференц-канал отвечает на звонок, и предлагает вызывающего голосовые приглашения, с помощью собрания автоматически, attendant, а затем, в зависимости от параметров, его можно воспроизвести уведомлений, попросите звонящих записать их имя и управлять параметров ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="90ae4-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="90ae4-109">ПИН-коды, предоставляемые Организаторы собраний для них начало собрания при неиспользуемые Скайп для бизнеса или группами Майкрософт приложения.</span><span class="sxs-lookup"><span data-stu-id="90ae4-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="90ae4-110">ПИН-код является только необходимых Организатор собрания при Скайп для бизнеса или группами Майкрософт пользователя приложения еще не запущена собрания.</span><span class="sxs-lookup"><span data-stu-id="90ae4-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="90ae4-111">Если все пытается подключиться к собранию, ПИН-код является обязательным для организатора собрания начать собрание.</span><span class="sxs-lookup"><span data-stu-id="90ae4-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!CAUTION]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-and-skype-for-business-admin-center"></a><span data-ttu-id="90ae4-112">Использование групп Майкрософт и Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="90ae4-112">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="90ae4-113">В левой области переходов, перейдите к **собраниям** > **мостов конференции**.</span><span class="sxs-lookup"><span data-stu-id="90ae4-113">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="90ae4-114">В верхней части страницы **мостов конференции** нажмите кнопку **Параметры Bridge**.</span><span class="sxs-lookup"><span data-stu-id="90ae4-114">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="90ae4-115">В области **Параметры моста** выберите:</span><span class="sxs-lookup"><span data-stu-id="90ae4-115">In the **Bridge settings** pane, select:</span></span> 
  - <span data-ttu-id="90ae4-116">**Собрание и выйти из уведомления** Если отключить этот режим, пользователей, которые уже присоединились к собранию не будут уведомлены, когда кто-то или выходе из собрания.</span><span class="sxs-lookup"><span data-stu-id="90ae4-116">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="90ae4-117">При **входе и выходе уведомления о собрании**, можно выбрать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="90ae4-117">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
  - <span data-ttu-id="90ae4-118">**Имена или телефонных номеров** Когда пользователи телефонное подключение к собранию, телефонный номер, воспроизводимый при их присоединении к.</span><span class="sxs-lookup"><span data-stu-id="90ae4-118">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="90ae4-119">**Мелодии** Когда пользователи телефонное подключение к собранию, звукового сигнала будет воспроизводиться при их присоединении к.</span><span class="sxs-lookup"><span data-stu-id="90ae4-119">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
  - <span data-ttu-id="90ae4-120">**ASK абонентов записать их имя перед присоединением к собранию** Если отключить этот режим, вызывающие объекты не будет предложено записать их имя перед их присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="90ae4-120">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="90ae4-121">Чтобы задать длину ПИН-кода для собраний, выберите количество знаков, которое необходимо использовать для ПИН-кода в списке **Длина ПИН-кода** .</span><span class="sxs-lookup"><span data-stu-id="90ae4-121">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="90ae4-122">Чтобы указать необходимость отправки электронной почты для пользователей, включение или отключение **автоматически отправлять пользователям по электронной почте при изменении их конфигурации аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="90ae4-122">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="90ae4-123">Для получения дополнительных сведений в разделе [по электронной почте, автоматически отправляются пользователям при изменении их параметров звука конференц-связи](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="90ae4-123">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
 
6. <span data-ttu-id="90ae4-124">Нажмите кнопку **Применить**.</span><span class="sxs-lookup"><span data-stu-id="90ae4-124">Click **Apply**.</span></span> 

## <a name="using-skype-for-business-admin-center"></a><span data-ttu-id="90ae4-125">С помощью Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="90ae4-125">Using Skype for Business admin center</span></span>

 <span data-ttu-id="90ae4-126">**Настройка качества собрания при абонентов присоединиться к собранию**</span><span class="sxs-lookup"><span data-stu-id="90ae4-126">**Set up the meeting experience when callers join a meeting**</span></span>
    
1. <span data-ttu-id="90ae4-127">В **Скайп по центру администрирования бизнеса**, в левой панели навигации выберите пункты **аудиоконференции** > **параметров моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="90ae4-127">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="90ae4-128">На странице **параметров моста Microsoft** в разделе **при присоединении к собраниям**выберите:</span><span class="sxs-lookup"><span data-stu-id="90ae4-128">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="90ae4-129">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="90ae4-129">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="90ae4-130">Если снять этот флажок, пользователей, которые уже присоединились к собранию не будут уведомлены, когда кто-то или выходе из собрания.</span><span class="sxs-lookup"><span data-stu-id="90ae4-130">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="90ae4-131">При выборе **Включить запись собрание и выйти из уведомления, чтобы быть включенным**эти параметры можно выбрать в списке **Тип объявлений входа и выхода** :</span><span class="sxs-lookup"><span data-stu-id="90ae4-131">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="90ae4-132">**Имена или телефонных номеров** Когда пользователи телефонное подключение к собранию, телефонный номер, воспроизводимый при их присоединении к.</span><span class="sxs-lookup"><span data-stu-id="90ae4-132">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="90ae4-133">**Мелодии** Когда пользователи телефонное подключение к собранию, звукового сигнала будет воспроизводиться при их присоединении к.</span><span class="sxs-lookup"><span data-stu-id="90ae4-133">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
  
  - <span data-ttu-id="90ae4-134">**ASK абонентов записать их имя перед присоединением к собранию** Этот флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="90ae4-134">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="90ae4-135">Если снять этот флажок, вызывающие объекты не будет предложено записать их имя перед их присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="90ae4-135">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
3. <span data-ttu-id="90ae4-136">См. статью **Изменение параметров моста аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="90ae4-136">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="90ae4-137">**Задать длину ПИН-кода для собраний**</span><span class="sxs-lookup"><span data-stu-id="90ae4-137">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="90ae4-138">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="90ae4-138">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="90ae4-139">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="90ae4-139">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="90ae4-140">В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="90ae4-140">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="90ae4-141">На странице **параметров моста корпорации Майкрософт** в области **безопасности**введите количество цифр, которое необходимо использовать для ПИН-кода в списке **Длина ПИН-код** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="90ae4-141">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="90ae4-142">ПИН-код должен быть от 4 до 12 цифр.</span><span class="sxs-lookup"><span data-stu-id="90ae4-142">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="90ae4-143">**Выберите, следует ли для отправки электронной почты для пользователей**</span><span class="sxs-lookup"><span data-stu-id="90ae4-143">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="90ae4-144">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="90ae4-144">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="90ae4-145">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="90ae4-145">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="90ae4-146">В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="90ae4-146">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="90ae4-147">На странице **параметров Microsoft моста** установите или снимите флажок **автоматически отправлять пользователям по электронной почте при изменении их данные для подключения**и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="90ae4-147">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their dial-in information changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="90ae4-148">Для получения дополнительных сведений в разделе [по электронной почте, автоматически отправляются пользователям при изменении их параметров звука конференц-связи](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="90ae4-148">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="90ae4-149">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90ae4-149">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="90ae4-150">Для экономии времени или автоматизировать этот процесс, можно использовать командлет [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .</span><span class="sxs-lookup"><span data-stu-id="90ae4-150">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="90ae4-p107">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="90ae4-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="90ae4-154">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="90ae4-154">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="90ae4-155">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="90ae4-155">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="90ae4-p108">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="90ae4-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="90ae4-158">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="90ae4-158">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="90ae4-159">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="90ae4-159">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="90ae4-160">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="90ae4-160">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="90ae4-p109">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="90ae4-p109">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="90ae4-163">See also</span><span class="sxs-lookup"><span data-stu-id="90ae4-163">Related topics</span></span>

[<span data-ttu-id="90ae4-164">Настройка аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="90ae4-164">Set up Audio Conferencing</span></span>](set-up-audio-conferencing.md)
