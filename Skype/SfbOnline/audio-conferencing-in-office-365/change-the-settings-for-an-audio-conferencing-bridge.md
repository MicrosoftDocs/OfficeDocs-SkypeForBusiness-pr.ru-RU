---
title: "Изменение параметров для конференц-связи аудио мост"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
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
description: "Получите действий, необходимых для изменения параметров моста телефонных конференций Microsoft, используемый для запрашивать абонентов и сбор имен и ПИН-коды для организаторам собрания при работе с Скайп не пользователей. "
ms.openlocfilehash: 62307bf26458ae54134772a0d920bcc602265bdc
ms.sourcegitcommit: 997c03395fd1966607cef0df8ee884303401cd64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="f54a7-103">Изменение параметров для конференц-связи аудио мост</span><span class="sxs-lookup"><span data-stu-id="f54a7-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="f54a7-104">При установке аудиоконференций в Office 365, вы получите номера телефонов для пользователей из называемое звукового конференц-канала.</span><span class="sxs-lookup"><span data-stu-id="f54a7-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="f54a7-105">Конференц-канал может содержать один или несколько номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="f54a7-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="f54a7-106">Эти номера телефонов используются при абонентов телефонное подключение к собранию.</span><span class="sxs-lookup"><span data-stu-id="f54a7-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="f54a7-107">Номер телефона включен в нижней части Скайп для бизнеса или группами Майкрософт приглашение.</span><span class="sxs-lookup"><span data-stu-id="f54a7-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="f54a7-108">Конференц-канал отвечает на звонок, и предлагает вызывающего голосовые приглашения, с помощью собрания автоматически, attendant, а затем, в зависимости от параметров, его можно воспроизвести уведомлений, попросите звонящих записать их имя и управлять параметров ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="f54a7-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="f54a7-109">ПИН-коды, предоставляемые Организаторы собраний для них начало собрания при неиспользуемые Скайп для бизнеса или группами Майкрософт приложения.</span><span class="sxs-lookup"><span data-stu-id="f54a7-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="f54a7-110">ПИН-код является только необходимых Организатор собрания при Скайп для бизнеса или группами Майкрософт пользователя приложения еще не запущена собрания.</span><span class="sxs-lookup"><span data-stu-id="f54a7-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="f54a7-111">Если все пытается подключиться к собранию, ПИН-код является обязательным для организатора собрания начать собрание.</span><span class="sxs-lookup"><span data-stu-id="f54a7-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="f54a7-112">Изменение параметров для звукового конференц-канала</span><span class="sxs-lookup"><span data-stu-id="f54a7-112">Change the settings for an audio conferencing bridge</span></span>

 <span data-ttu-id="f54a7-113">**Настройка качества собрания при абонентов присоединиться к собранию**</span><span class="sxs-lookup"><span data-stu-id="f54a7-113">**Set up the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="f54a7-114">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="f54a7-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f54a7-115">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="f54a7-115">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f54a7-116">В **Скайп по центру администрирования бизнеса**, в левой панели навигации выберите пункты **аудиоконференции** > **параметров моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="f54a7-116">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="f54a7-117">На странице **параметров моста Microsoft** в разделе **при присоединении к собраниям**выберите:</span><span class="sxs-lookup"><span data-stu-id="f54a7-117">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="f54a7-118">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="f54a7-118">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="f54a7-119">Если снять этот флажок, пользователей, которые уже присоединились к собранию не будут уведомлены, когда кто-то или выходе из собрания.</span><span class="sxs-lookup"><span data-stu-id="f54a7-119">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="f54a7-120">При выборе **Включить запись собрание и выйти из уведомления, чтобы быть включенным**эти параметры можно выбрать в списке **Тип объявлений входа и выхода** :</span><span class="sxs-lookup"><span data-stu-id="f54a7-120">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="f54a7-121">**Имена или телефонных номеров** Когда пользователи телефонное подключение к собранию, телефонный номер, воспроизводимый при их присоединении к.</span><span class="sxs-lookup"><span data-stu-id="f54a7-121">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="f54a7-122">**Мелодии** Когда пользователи телефонное подключение к собранию, звукового сигнала будет воспроизводиться при их присоединении к.</span><span class="sxs-lookup"><span data-stu-id="f54a7-122">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f54a7-123">С использованием **Tone** в поле Тип оповещения в настоящее время доступны для всех клиентов как компонент предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="f54a7-123">Using **Tone** as the announcement type is currently available to all customers as a preview feature.</span></span>
  
  - <span data-ttu-id="f54a7-124">**ASK абонентов записать их имя перед присоединением к собранию** Этот флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f54a7-124">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="f54a7-125">Если снять этот флажок, вызывающие объекты не будет предложено записать их имя перед их присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="f54a7-125">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="f54a7-126">См. статью **Изменение параметров моста аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="f54a7-126">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="f54a7-127">**Задать длину ПИН-кода для собраний**</span><span class="sxs-lookup"><span data-stu-id="f54a7-127">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="f54a7-128">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="f54a7-128">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f54a7-129">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="f54a7-129">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f54a7-130">В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="f54a7-130">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="f54a7-131">На странице **параметров моста корпорации Майкрософт** в области **безопасности**введите количество цифр, которое необходимо использовать для ПИН-кода в списке **Длина ПИН-код** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f54a7-131">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f54a7-132">ПИН-код должен быть от 4 до 12 цифр.</span><span class="sxs-lookup"><span data-stu-id="f54a7-132">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="f54a7-133">**Выберите, следует ли для отправки электронной почты для пользователей**</span><span class="sxs-lookup"><span data-stu-id="f54a7-133">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="f54a7-134">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="f54a7-134">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="f54a7-135">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="f54a7-135">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="f54a7-136">В окне **Центр администрирования Skype для бизнеса** на панели навигации слева выберите **Конференц-связь с телефонным подключением** > **Параметры моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="f54a7-136">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="f54a7-137">На странице **параметров Microsoft моста** установите или снимите флажок **автоматически отправлять пользователям по электронной почте при изменении их аудиоконференций конфигурации**и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f54a7-137">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing configuration changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="f54a7-138">Для получения дополнительных сведений в разделе [по электронной почте, автоматически отправляются пользователям при изменении их параметров звука конференц-связи](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="f54a7-138">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f54a7-139">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f54a7-139">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="f54a7-140">Для экономии времени или автоматизировать этот процесс, можно использовать командлет [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .</span><span class="sxs-lookup"><span data-stu-id="f54a7-140">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="f54a7-p106">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="f54a7-p106">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f54a7-144">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="f54a7-144">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f54a7-145">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f54a7-145">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="f54a7-p107">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="f54a7-p107">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="f54a7-148">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f54a7-148">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f54a7-149">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f54a7-149">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f54a7-150">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f54a7-150">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="f54a7-p108">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="f54a7-p108">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f54a7-153">See also</span><span class="sxs-lookup"><span data-stu-id="f54a7-153">Related topics</span></span>

[<span data-ttu-id="f54a7-154">Настройка аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="f54a7-154">Set up Audio Conferencing</span></span>](set-up-audio-conferencing.md)
