---
title: "Изменение параметров для конференц-связи аудио мост"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "Получите действий, необходимых для изменения параметров моста телефонных конференций Microsoft, используемый для запрашивать абонентов и сбор имен и ПИН-коды для организаторам собрания при работе с Скайп не пользователей. "
ms.openlocfilehash: 5da33e083999f00d217a86455f61fd58ca2d1713
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="ab17a-103">Изменение параметров для конференц-связи аудио мост</span><span class="sxs-lookup"><span data-stu-id="ab17a-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="ab17a-104">При установке аудиоконференций в Office 365, вы получите номера телефонов для пользователей из называемое звукового конференц-канала.</span><span class="sxs-lookup"><span data-stu-id="ab17a-104">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="ab17a-105">Конференц-канал может содержать один или несколько номеров телефонов.</span><span class="sxs-lookup"><span data-stu-id="ab17a-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="ab17a-106">Эти номера телефонов используются при абонентов телефонное подключение к собранию.</span><span class="sxs-lookup"><span data-stu-id="ab17a-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="ab17a-107">Номер телефона включен в нижней части Скайп для бизнеса или группами Майкрософт приглашение.</span><span class="sxs-lookup"><span data-stu-id="ab17a-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="ab17a-108">Конференц-канал отвечает на звонок, и предлагает вызывающего голосовые приглашения, с помощью собрания автоматически, attendant, а затем, в зависимости от параметров, его можно воспроизвести уведомлений, попросите звонящих записать их имя и управлять параметров ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="ab17a-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="ab17a-109">ПИН-коды, предоставляемые Организаторы собраний для них начало собрания при неиспользуемые Скайп для бизнеса или группами Майкрософт приложения.</span><span class="sxs-lookup"><span data-stu-id="ab17a-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="ab17a-110">Изменение параметров для звукового конференц-канала</span><span class="sxs-lookup"><span data-stu-id="ab17a-110">Change the settings for an audio conferencing bridge</span></span>

 <span data-ttu-id="ab17a-111">**Настройка качества собрания при абонентов присоединиться к собранию**</span><span class="sxs-lookup"><span data-stu-id="ab17a-111">**Set up the meeting experience when callers join a meeting**</span></span>
  
1. <span data-ttu-id="ab17a-112">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="ab17a-112">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="ab17a-113">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ab17a-113">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="ab17a-114">В **Скайп по центру администрирования бизнеса**, в левой панели навигации выберите пункты **аудиоконференции** > **параметров моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="ab17a-114">In the **Skype for Business admin center**, in the left navigation go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="ab17a-115">На странице **параметров моста Microsoft** в разделе **при присоединении к собраниям**выберите:</span><span class="sxs-lookup"><span data-stu-id="ab17a-115">On the **Microsoft bridge settings** page, under **Meeting join experience**, select:</span></span>
    
  - <span data-ttu-id="ab17a-116">**Включить запись собрание и выйти из уведомления, чтобы быть включенным** Этот флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ab17a-116">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="ab17a-117">Если снять этот флажок, пользователей, которые уже присоединились к собранию не будут уведомлены, когда кто-то или выходе из собрания.</span><span class="sxs-lookup"><span data-stu-id="ab17a-117">If you clear the check box, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="ab17a-118">При выборе **Включить запись собрание и выйти из уведомления, чтобы быть включенным**эти параметры можно выбрать в списке **Тип объявлений входа и выхода** :</span><span class="sxs-lookup"><span data-stu-id="ab17a-118">When you select **Enable meeting entry and exit notifications to be turned on**, you can select these options from the **Entry/exit announcement type** list:</span></span>
    
  - <span data-ttu-id="ab17a-119">**Имена или телефонных номеров** Когда пользователи телефонное подключение к собранию, телефонный номер, воспроизводимый при их присоединении к.</span><span class="sxs-lookup"><span data-stu-id="ab17a-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
  - <span data-ttu-id="ab17a-120">**Мелодии** Когда пользователи телефонное подключение к собранию, звукового сигнала будет воспроизводиться при их присоединении к.</span><span class="sxs-lookup"><span data-stu-id="ab17a-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ab17a-121">С использованием **Tone** в поле Тип оповещения в настоящее время доступны для всех клиентов как компонент предварительного просмотра.</span><span class="sxs-lookup"><span data-stu-id="ab17a-121">Using **Tone** as the announcement type is currently available to all customers as a preview feature.</span></span>
  
  - <span data-ttu-id="ab17a-122">**ASK абонентов записать их имя перед присоединением к собранию** Этот флажок установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="ab17a-122">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="ab17a-123">Если снять этот флажок, вызывающие объекты не будет предложено записать их имя перед их присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="ab17a-123">If you clear the check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="ab17a-124">После внесения изменений нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ab17a-124">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="ab17a-125">**Задать длину ПИН-кода для собраний**</span><span class="sxs-lookup"><span data-stu-id="ab17a-125">**Set the PIN length for meetings**</span></span>
  
1. <span data-ttu-id="ab17a-126">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="ab17a-126">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="ab17a-127">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ab17a-127">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="ab17a-128">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **параметров моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="ab17a-128">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="ab17a-129">На странице **параметров моста корпорации Майкрософт** в области **безопасности**введите количество цифр, которое необходимо использовать для ПИН-кода в списке **Длина ПИН-код** и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ab17a-129">On the **Microsoft bridge settings** page, under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ab17a-130">ПИН-код должен быть от 4 до 12 цифр.</span><span class="sxs-lookup"><span data-stu-id="ab17a-130">The PIN must be between 4 and 12 digits.</span></span> 
  
<span data-ttu-id="ab17a-131">**Выберите, следует ли для отправки электронной почты для пользователей**</span><span class="sxs-lookup"><span data-stu-id="ab17a-131">**Select whether to send email to your users**</span></span>
  
1. <span data-ttu-id="ab17a-132">Войдите в Office 365 под своей учебной или рабочей учетной записью.</span><span class="sxs-lookup"><span data-stu-id="ab17a-132">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="ab17a-133">Перейдите в раздел **Центр администрирования Office 365** > **Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ab17a-133">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="ab17a-134">В **Скайп по центру администрирования бизнеса**, в левой области переходов, перейдите к **аудиоконференции** > **параметров моста Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="ab17a-134">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="ab17a-135">На странице **параметров Microsoft моста** установите или снимите флажок **автоматически отправлять пользователям по электронной почте при изменении их аудиоконференций конфигурации**и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="ab17a-135">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing configuration changes**, and then click **Save**.</span></span>
    
    <span data-ttu-id="ab17a-136">Для получения дополнительных сведений в разделе [по электронной почте, автоматически отправляются пользователям при изменении их параметров звука конференц-связи](emails-sent-to-users-when-their-settings-change.md) .</span><span class="sxs-lookup"><span data-stu-id="ab17a-136">See [Emails automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md) for more information.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="ab17a-137">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab17a-137">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="ab17a-138">Для экономии времени или автоматизировать этот процесс, можно использовать командлет [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) .</span><span class="sxs-lookup"><span data-stu-id="ab17a-138">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 ) cmdlet.</span></span>
    
- <span data-ttu-id="ab17a-139">Windows PowerShell — все сведения об управлении пользователями и какие пользователи разрешенные или запрещенные для.</span><span class="sxs-lookup"><span data-stu-id="ab17a-139">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ab17a-140">С помощью Windows PowerShell можно управлять Office 365 с помощью точки администрирования, которые можно упростить повседневной работой при наличии нескольких задач для выполнения.</span><span class="sxs-lookup"><span data-stu-id="ab17a-140">With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="ab17a-141">Для начала работы с оболочкой Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="ab17a-141">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ab17a-142">Почему необходимо использовать Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab17a-142">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="ab17a-143">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ab17a-143">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="ab17a-144">Windows PowerShell имеет много преимуществ в скорости, простоты и повышения производительности по сравнению только с помощью центра администрирования Office 365, например, при внесении изменений параметров для нескольких пользователей за один раз.</span><span class="sxs-lookup"><span data-stu-id="ab17a-144">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ab17a-145">Сведения об этих преимуществах в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="ab17a-145">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="ab17a-146">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ab17a-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ab17a-147">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ab17a-147">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ab17a-148">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="ab17a-148">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="ab17a-p107">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="ab17a-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ab17a-151">См. также:</span><span class="sxs-lookup"><span data-stu-id="ab17a-151">Related topics</span></span>

[<span data-ttu-id="ab17a-152">Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ab17a-152">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](set-up-audio-conferencing.md)

