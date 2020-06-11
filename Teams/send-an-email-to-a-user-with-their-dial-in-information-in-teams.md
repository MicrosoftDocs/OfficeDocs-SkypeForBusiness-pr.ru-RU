---
title: Отправка пользователю сведений о голосовой конференции по электронной почте
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
description: Сведения о том, как отправлять пользователям сообщения электронной почты с помощью голосовой конференции в Microsoft Teams.
ms.openlocfilehash: 5f281071dd4ae9a21f9148ac86943d4ab4ce36b8
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691145"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="71fb2-103">Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71fb2-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="71fb2-104">Иногда пользователям Microsoft Teams требуется, чтобы вы отправляли им информацию об аудиоконференциях.</span><span class="sxs-lookup"><span data-stu-id="71fb2-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="71fb2-105">Вы можете сделать это, выбрав пункт **Отправить сведения о конференции по эл. почте** в свойствах для пользователя.</span><span class="sxs-lookup"><span data-stu-id="71fb2-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="71fb2-106">Отправляемое сообщение будет содержать всю информацию об аудиоконференции, включая следующее:</span><span class="sxs-lookup"><span data-stu-id="71fb2-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="71fb2-107">телефонный номер конференции или номер телефонного подключения для пользователя;</span><span class="sxs-lookup"><span data-stu-id="71fb2-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="71fb2-108">идентификатор конференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="71fb2-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="71fb2-109">Далее приведен пример отправляемого сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="71fb2-109">Here is an example of the email that is sent:</span></span>
  
![Пример сообщения электронной почты конференц-связи с телефонным подключением](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="71fb2-111">Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="71fb2-111">Send an email with audio conferencing information to a user</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="71fb2-113">С помощью Центра администрирования Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="71fb2-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="71fb2-114">На панели навигации слева выберите пункт **Пользователи**, а затем выберите пользователя из списка доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="71fb2-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="71fb2-115">В верхней части страницы нажмите кнопку **изменить**.</span><span class="sxs-lookup"><span data-stu-id="71fb2-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="71fb2-116">В разделе **Аудиоконференции** щелкните **Отправить информацию для конференций в электронном письме**.</span><span class="sxs-lookup"><span data-stu-id="71fb2-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="71fb2-117">Что еще необходимо знать о таких сообщениях?</span><span class="sxs-lookup"><span data-stu-id="71fb2-117">What else should you know about this email?</span></span>

- <span data-ttu-id="71fb2-118">После включения поддержки голосовой конференции у пользователей вашей организации есть несколько сообщений электронной почты, которые отправляются пользователям.</span><span class="sxs-lookup"><span data-stu-id="71fb2-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="71fb2-119">При назначении пользователям лицензии **аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="71fb2-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="71fb2-120">При ручном сбросе ПИН-кода голосовой конференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="71fb2-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="71fb2-121">Выполнение сброса идентификатора конференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="71fb2-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="71fb2-122">При изъятии лицензии **аудиоконференций** у пользователя.</span><span class="sxs-lookup"><span data-stu-id="71fb2-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="71fb2-123">Когда поставщик видеоконференций для пользователя будет изменен с Microsoft на другого поставщика или **нет**.</span><span class="sxs-lookup"><span data-stu-id="71fb2-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="71fb2-124">После изменения поставщика голосовой конференции для пользователя на Microsoft.</span><span class="sxs-lookup"><span data-stu-id="71fb2-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="71fb2-125">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="71fb2-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="71fb2-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="71fb2-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="71fb2-127">С помощью Windows PowerShell можно управлять Microsoft 365 или Office 365, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач.</span><span class="sxs-lookup"><span data-stu-id="71fb2-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="71fb2-128">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="71fb2-128">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="71fb2-129">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="71fb2-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="71fb2-130">Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="71fb2-130">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="71fb2-131">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="71fb2-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="71fb2-132">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="71fb2-132">Related topics</span></span>

[<span data-ttu-id="71fb2-133">Попробуйте или купите голосовую конференцию в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="71fb2-133">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
