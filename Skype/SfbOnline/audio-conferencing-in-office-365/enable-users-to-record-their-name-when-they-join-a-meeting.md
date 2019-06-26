---
title: Предоставление пользователям возможности записывать свое имя при присоединении к собранию в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Сведения о том, как включать и отключать возможность записи пользователями своих имен при присоединении к собранию в Skype для бизнеса Online.
ms.openlocfilehash: 7209d95db6ada7b4569ee4c6dc1aded8b2e6b877
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2019
ms.locfileid: "35221529"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a><span data-ttu-id="bcadf-103">Предоставление пользователям возможности записывать свое имя при присоединении к собранию в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="bcadf-103">Enable users to record their name when they join a meeting in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="bcadf-104">Если требуется предоставить пользователям возможность записывать свое имя в Microsoft Teams, ознакомьтесь со статьей [Предоставление пользователям возможности записи собственного имени при присоединении к собранию в Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span><span class="sxs-lookup"><span data-stu-id="bcadf-104">If you want to allow users to record their names in Teams, see [Enable users to record their name when they join a meeting in Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).</span></span>

<span data-ttu-id="bcadf-p101">[] При настройке конференц-связи с телефонным подключением в Skype для бизнеса online вы получите телефонные номера и ресурс, который называется мостом для конференц-связи с телефонным подключением или для аудиоконференций. Мост для конференц-связи может содержать один или несколько телефонных номеров, которые могут быть как выделенными, так и общими.</span><span class="sxs-lookup"><span data-stu-id="bcadf-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="bcadf-p102">Мост конференц-связи обеспечивает ответ на вызов пользователя, который присоединяется к собранию с телефона. Мост конференц-связи отвечает вызывающей стороне голосовыми подсказками с помощью автосекретаря, а затем, в зависимости от настроек, может воспроизвести уведомления, попросить вызывающую сторону записать свое имя и настроить ПИН-код безопасности для организаторов собрания. ПИН-коды предоставляются организаторам собраний. Организаторы могут начать собрание, введя ПИН-код. Однако собрание можно настроить таким образом, чтобы ПИН-код не требовался.</span><span class="sxs-lookup"><span data-stu-id="bcadf-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="bcadf-111">Определение того, должны ли вызывающие записи записывать свое имя</span><span class="sxs-lookup"><span data-stu-id="bcadf-111">Set whether callers should record their name</span></span>
    
1. <span data-ttu-id="bcadf-112">В **центре администрирования Skype для бизнеса**на панели навигации слева перейдите к разделу**Настройка моста**видеоконференций \*\*\*\* > Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bcadf-112">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="bcadf-113">В разделе **Присоединение к собранию** включите параметр **Включить уведомления о входе и выходе из собрания**.</span><span class="sxs-lookup"><span data-stu-id="bcadf-113">Under **Meeting join experience**, see the check box labeled **Enable meeting entry and exit notifications to be turned on**.</span></span>
    
   - <span data-ttu-id="bcadf-p103">**Флажок установлен**  вызывающим сторонам будет выдан запрос о вводе имени перед входом в собрание. Выбрано по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bcadf-p103">**Selected** Callers will be asked to record their name before they enter the meeting. This is selected by default.</span></span>
    
   - <span data-ttu-id="bcadf-116">**Флажок снят**  вызывающим сторонам не будет выдаваться запрос о вводе имени перед входом в собрание.</span><span class="sxs-lookup"><span data-stu-id="bcadf-116">**Cleared** Callers won't be asked to record their name before they enter the meeting.</span></span>
    
3. <span data-ttu-id="bcadf-117">После внесения изменений нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="bcadf-117">After you make your changes, click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="bcadf-118">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcadf-118">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="bcadf-119">Для экономии времени или автоматизации процесса можно воспользоваться командлетом [Set-csonlinedialinconferencingtenantsettingshttp](https://go.microsoft.com/fwlink/?LinkId=715757) .</span><span class="sxs-lookup"><span data-stu-id="bcadf-119">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757) cmdlet.</span></span>
    
- <span data-ttu-id="bcadf-p104">Что касается Windows PowerShell, то Skype для бизнеса online дает возможность управлять пользователями и предоставлять им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365, используя единый центр администрирования, который упрощает выполнение повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="bcadf-p104">Windows PowerShell is all about managing users and what users are allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bcadf-123">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="bcadf-123">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="bcadf-124">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bcadf-124">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="bcadf-p105">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="bcadf-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="bcadf-127">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="bcadf-127">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="bcadf-128">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="bcadf-128">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="bcadf-129">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="bcadf-129">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="bcadf-p106">Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль для 64-разрядных систем можно загрузить из Центра загрузки Microsoft здесь: [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="bcadf-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bcadf-132">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="bcadf-132">Related topics</span></span>

[<span data-ttu-id="bcadf-133">Платная или пробная версия аудиоконференций в Office 365</span><span class="sxs-lookup"><span data-stu-id="bcadf-133">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
