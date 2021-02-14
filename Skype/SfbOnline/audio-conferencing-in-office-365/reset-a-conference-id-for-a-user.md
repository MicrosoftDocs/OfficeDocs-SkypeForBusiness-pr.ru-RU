---
title: Сброс ИД конференции для пользователя в Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: 'Узнайте, как сбросить ИД конференции пользователя в Skype для бизнеса Online и получить ссылки на средства обновления собраний и миграции. '
ms.openlocfilehash: f0bf8a991cfa7c597bb7a0424709e81851291307
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164708"
---
# <a name="reset-a-conference-id-for-a-user-in-skype-for-business-online"></a><span data-ttu-id="7da29-103">Сброс ИД конференции для пользователя в Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7da29-103">Reset a conference ID for a user in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="7da29-104">Сведения о сбросе ИД конференции в Microsoft Teams см. в сведениях о сбросе ИД конференции для [пользователя в Microsoft Teams.](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams)</span><span class="sxs-lookup"><span data-stu-id="7da29-104">For information about resetting conference ID in Microsoft Teams, see [Reset a conference ID for a user in Microsoft Teams](/MicrosoftTeams/reset-a-conference-id-for-a-user-in-teams).</span></span>

<span data-ttu-id="7da29-105">Динамический ИД конференции содержится в нижней части приглашений на собрание, а также номера телефонов для телефонного звонка, которые могут использоваться звонителями для звонков на собрание.</span><span class="sxs-lookup"><span data-stu-id="7da29-105">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="7da29-106">Когда пользователь наберет номер телефона, автозавод для собрания попросит вызывающего пользователя ввести этот номер конференции, чтобы он принял участие в собрании.</span><span class="sxs-lookup"><span data-stu-id="7da29-106">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7da29-107">Если поставщиком конференц-связи является Корпорация Майкрософт, для ваших пользователей задаются только динамические ID-записи конференций.</span><span class="sxs-lookup"><span data-stu-id="7da29-107">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only.</span></span> <span data-ttu-id="7da29-108">Эта настройка не может быть изменена.</span><span class="sxs-lookup"><span data-stu-id="7da29-108">This cannot be changed.</span></span> <span data-ttu-id="7da29-109">IDs конференции автоматически задаются только для пользователей Skype для бизнеса, включенных для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="7da29-109">Conference IDs are automatically set only for Skype for Business users enabled for Audio Conferencing.</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="7da29-110">Сброс ИД конференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="7da29-110">Resetting the conference ID for a user</span></span>
   
1. <span data-ttu-id="7da29-111">В Центре **администрирования Skype** для бизнеса щелкните "Пользователи аудиоконференции", выберите пользователя, а затем в области действий в области "ИД конференции" нажмите кнопку  >    **"Сброс".**</span><span class="sxs-lookup"><span data-stu-id="7da29-111">In the **Skype for Business admin center**, click **Audio conferencing** > **Users**, select a user, and then in the Action pane under **Conference ID** click **Reset**.</span></span>
    
2. <span data-ttu-id="7da29-112">В **окне "Сбросить ИД конференции?"** нажмите кнопку **"Да".**</span><span class="sxs-lookup"><span data-stu-id="7da29-112">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="7da29-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="7da29-113">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="7da29-114">По умолчанию электронные письма отправляются пользователям, но это можно отключить.</span><span class="sxs-lookup"><span data-stu-id="7da29-114">By default, emails are sent to users, but this can be turned off.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7da29-115">После сброса идентификатора конференции на электронную почту пользователя отправляется сообщение с новым идентификатором конференции.</span><span class="sxs-lookup"><span data-stu-id="7da29-115">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="7da29-116">Во многих случаях это сообщение электронной почты отправляется на основной адрес электронной почты их почтового ящика Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="7da29-116">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="7da29-117">Сообщение электронной почты содержит новый идентификатор конференции, номера телефонов для телефонного подключения по умолчанию и инструкции по использованию средства обновления для собраний Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7da29-117">The email contains the new conference ID, default dial-in phone number(s) and instructions to use the Skype for Business Meeting Update Tool to update existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="7da29-118">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="7da29-118">What else should I know?</span></span>

- <span data-ttu-id="7da29-119">Вы можете отправить пользователю по электронной почте все сведения о конференции, включая ее ИД и  номера телефонов для телефонного звонка, нажав кнопку "Отправить сведения о конференции по электронной почте" для пользователя на области действий.</span><span class="sxs-lookup"><span data-stu-id="7da29-119">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info via email** for the user in the Action pane.</span></span> <span data-ttu-id="7da29-120">ПИН-код не отправляется.</span><span class="sxs-lookup"><span data-stu-id="7da29-120">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="7da29-121">Код конференции будет содержать 7 цифр, и вы не сможете изменить его длину в Центре администрирования Skype для бизнеса или с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7da29-121">A conference ID will contain 7 digits, and you can't change its length in the Skype for Business admin center or by using Windows PowerShell.</span></span>
    
- <span data-ttu-id="7da29-122">После сброса новый идентификатор конференции будет отображаться в поле **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="7da29-122">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="7da29-123">При выборе пользователя на странице "Пользователи" в нижней части области действий в  области действий можно просмотреть ИД конференции пользователя для аудиоконференции. </span><span class="sxs-lookup"><span data-stu-id="7da29-123">The conference ID for a user for audio conferencing can be viewed at the bottom of the Action pane under **Audio conferencing** when you select the user on the **Users** page.</span></span>
    
- <span data-ttu-id="7da29-124">После создания нового идентификатора конференции старый идентификатор не может использоваться для выполнения вызовов.</span><span class="sxs-lookup"><span data-stu-id="7da29-124">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="7da29-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="7da29-125">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="7da29-126">Пользователи могут использовать инструмент "Собрание Skype для бизнеса" для обновления существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="7da29-126">The users can use Skype for Business Meeting Tool to update their existing meetings.</span></span> <span data-ttu-id="7da29-127">Чтобы узнать, как скачать, установить и запустить средство обновления для собраний Skype для бизнеса, см. 365.</span><span class="sxs-lookup"><span data-stu-id="7da29-127">To see how to download, install, and run the Skype for Business Meeting Update Tool, see:</span></span>
    
  - [<span data-ttu-id="7da29-128">Средство обновления для собраний Skype для бизнеса и Lync</span><span class="sxs-lookup"><span data-stu-id="7da29-128">Meeting Update Tool for Skype for Business and Lync</span></span>](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)
    
  - [<span data-ttu-id="7da29-129">Skype для бизнеса Online, инструмент переноса собраний (64-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="7da29-129">Skype for Business Online, Meeting Migration Tool (64-bit)</span></span>](https://go.microsoft.com/fwlink/?LinkID=626047)
    
  - [<span data-ttu-id="7da29-130">Skype для бизнеса Online, инструмент переноса собраний (32-разрядная версия)</span><span class="sxs-lookup"><span data-stu-id="7da29-130">Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>](https://www.microsoft.com/download/details.aspx?id=54079)
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="7da29-131">Сведения по управлению с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7da29-131">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="7da29-132">Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия.</span><span class="sxs-lookup"><span data-stu-id="7da29-132">When it comes to Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="7da29-133">С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="7da29-133">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="7da29-134">Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="7da29-134">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7da29-135">Введение в Windows PowerShell и Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7da29-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="7da29-136">Зачем нужно использовать Microsoft 365 или Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="7da29-136">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
 
- <span data-ttu-id="7da29-137">Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно.</span><span class="sxs-lookup"><span data-stu-id="7da29-137">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="7da29-138">Подробнее об этих преимуществах можно узнать в следующих разделах:</span><span class="sxs-lookup"><span data-stu-id="7da29-138">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="7da29-139">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7da29-139">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="7da29-140">Использование Windows PowerShell для управления Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7da29-140">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="7da29-141">Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7da29-141">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="7da29-142">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7da29-142">Related topics</span></span>

[<span data-ttu-id="7da29-143">Сброс ПИН-кода для аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="7da29-143">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin.md)
