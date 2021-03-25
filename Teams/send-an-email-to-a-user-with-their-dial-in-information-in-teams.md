---
title: Отправка пользователю по электронной почте сведений об аудиоконференции
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Узнайте, как отправить пользователям сообщение электронной почты с информацией об аудиоконференции в Microsoft Teams.
ms.openlocfilehash: 8cc0e549d502a2c7a8d8052ebe496a82e36b6648
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117217"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="0589a-103">Отправка пользователю письма с данными для аудиоконференций в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0589a-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="0589a-104">Иногда пользователям Microsoft Teams требуется, чтобы вы отправили им данные для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="0589a-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="0589a-105">Для этого щелкните ссылку "Отправить сведения о **конференции"** по электронной почте в свойствах пользователя.</span><span class="sxs-lookup"><span data-stu-id="0589a-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="0589a-106">При отправке этого сообщения электронной почты будут содержаться все сведения об аудиоконференции, включая следующие:</span><span class="sxs-lookup"><span data-stu-id="0589a-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="0589a-107">Телефонный номер конференции или номер телефонного подключения для пользователя.</span><span class="sxs-lookup"><span data-stu-id="0589a-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="0589a-108">Идентификатор конференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="0589a-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="0589a-109">Вот пример отправленного сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="0589a-109">Here is an example of the email that is sent:</span></span>
  
![Пример сообщения электронной почты для conferencing с dial-in](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="0589a-111">Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="0589a-111">Send an email with audio conferencing information to a user</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="0589a-113">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0589a-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="0589a-114">В области навигации слева **щелкните**"Пользователи" и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0589a-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="0589a-115">В верхней части страницы нажмите кнопку **"Изменить".**</span><span class="sxs-lookup"><span data-stu-id="0589a-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="0589a-116">В разделе **Аудиоконференции** щелкните **Отправить информацию для конференций в электронном письме**.</span><span class="sxs-lookup"><span data-stu-id="0589a-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="0589a-117">Что еще необходимо знать о таких сообщениях?</span><span class="sxs-lookup"><span data-stu-id="0589a-117">What else should you know about this email?</span></span>

- <span data-ttu-id="0589a-118">После включения аудиоконференции пользователям в организации отправляется несколько сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="0589a-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="0589a-119">При назначении пользователям лицензии **аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="0589a-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="0589a-120">При сбросе ПИН-кода аудиоконференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="0589a-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="0589a-121">Выполнение сброса идентификатора конференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="0589a-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="0589a-122">При изъятии лицензии **аудиоконференций** у пользователя.</span><span class="sxs-lookup"><span data-stu-id="0589a-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="0589a-123">При смене поставщика услуг аудиоконференций для пользователя с Microsoft на другого поставщика или **"Нет".**</span><span class="sxs-lookup"><span data-stu-id="0589a-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="0589a-124">При смене поставщика услуг аудиоконференций для пользователя на Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="0589a-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0589a-125">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="0589a-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="0589a-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="0589a-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0589a-127">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="0589a-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="0589a-128">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="0589a-128">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0589a-129">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="0589a-129">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="0589a-130">[Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="0589a-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="0589a-131">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="0589a-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="0589a-132">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0589a-132">Related topics</span></span>

[<span data-ttu-id="0589a-133">Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="0589a-133">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)