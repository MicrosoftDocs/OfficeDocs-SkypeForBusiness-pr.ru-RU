---
title: Разрешить пользователям записать их имя при их присоединиться к собранию группами Майкрософт
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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: Узнайте, как включить или отключить ли пользователям можно записать их имена при их присоединиться к собранию группами Майкрософт.
ms.openlocfilehash: 55aa14f53e71bb13c7219e3730cf91388b566047
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850795"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="a3029-103">Разрешить пользователям записать их имя при их присоединиться к собранию группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a3029-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="a3029-p101">[] При настройке конференц-связи с телефонным подключением в Skype для бизнеса online вы получите телефонные номера и ресурс, который называется мостом для конференц-связи с телефонным подключением или для аудиоконференций. Мост для конференц-связи может содержать один или несколько телефонных номеров, которые могут быть как выделенными, так и общими.</span><span class="sxs-lookup"><span data-stu-id="a3029-p101">When you are setting up Audio Conferencing in Office 365, you will receive phone numbers and what is called an audio conferencing bridge. A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="a3029-p102">Мост конференц-связи обеспечивает ответ на вызов пользователя, который присоединяется к собранию с телефона. Мост конференц-связи отвечает вызывающей стороне голосовыми подсказками с помощью автосекретаря, а затем, в зависимости от настроек, может воспроизвести уведомления, попросить вызывающую сторону записать свое имя и настроить ПИН-код безопасности для организаторов собрания. ПИН-коды предоставляются организаторам собраний. Организаторы могут начать собрание, введя ПИН-код. Однако собрание можно настроить таким образом, чтобы ПИН-код не требовался.</span><span class="sxs-lookup"><span data-stu-id="a3029-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="a3029-110">Выбор необходимости записи имени вызывающей стороны</span><span class="sxs-lookup"><span data-stu-id="a3029-110">Set whether callers should record their name</span></span>

1. <span data-ttu-id="a3029-111">В левой области переходов, перейдите к **собраниям** > **Мостов конференции**.</span><span class="sxs-lookup"><span data-stu-id="a3029-111">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="a3029-112">В верхней части страницы **Мостов конференции** нажмите кнопку **Параметры Bridge**.</span><span class="sxs-lookup"><span data-stu-id="a3029-112">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="a3029-113">Включение или отключение **собрание и выйти из уведомления**.</span><span class="sxs-lookup"><span data-stu-id="a3029-113">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="a3029-114">Если Включение уведомлений, выберите **имена или телефонных номеров** в списке **Тип входа и выхода объявлений**и включите **попросите звонящих записать их имя перед присоединением к собранию.**</span><span class="sxs-lookup"><span data-stu-id="a3029-114">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="a3029-115">Также можно отправить электронное письмо пользователю с помощью параметров аудиоконференции, выбрав на странице свойств аудиоконференции для пользователя параметр **Отправить информацию о конференции по электронной почте**.</span><span class="sxs-lookup"><span data-stu-id="a3029-115">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="a3029-116">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="a3029-116">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="a3029-p103">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="a3029-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="a3029-120">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="a3029-120">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="a3029-121">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a3029-121">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="a3029-122">Дополнительные сведения о Windows PowerShell, [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="a3029-122">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a3029-123">См. также:</span><span class="sxs-lookup"><span data-stu-id="a3029-123">Related topics</span></span>

[<span data-ttu-id="a3029-124">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="a3029-124">Try or purchase Audio Conferencing in Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
