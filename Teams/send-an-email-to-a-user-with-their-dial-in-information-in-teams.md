---
title: Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Сведения об отправке пользователям сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams.
ms.openlocfilehash: 445e783fde44b3067c1bc595fa93c623404e40db
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464062"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="abd98-103">Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="abd98-103">Send an email to a user with their Audio Conferencing information in Microsoft Teams</span></span>

<span data-ttu-id="abd98-104">Иногда пользователям Microsoft Teams требуется, чтобы вы отправляли им информацию об аудиоконференциях.</span><span class="sxs-lookup"><span data-stu-id="abd98-104">Sometimes Microsoft Teams users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="abd98-105">Вы можете сделать это, выбрав пункт **Отправить сведения о конференции по эл. почте** в свойствах для пользователя.</span><span class="sxs-lookup"><span data-stu-id="abd98-105">You can do this by clicking **Send conference info via email** under the properties for a user.</span></span> <span data-ttu-id="abd98-106">Отправляемое сообщение будет содержать всю информацию об аудиоконференции, включая следующее:</span><span class="sxs-lookup"><span data-stu-id="abd98-106">When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="abd98-107">телефонный номер конференции или номер телефонного подключения для пользователя;</span><span class="sxs-lookup"><span data-stu-id="abd98-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="abd98-108">идентификатор конференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="abd98-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="abd98-109">Далее приведен пример отправляемого сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="abd98-109">Here is an example of the email that is sent:</span></span>
  
![Сообщение о конференц-связи с телефонным подключением](media/teams-send-email-to-user-with-audio-conferencing-image1.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="abd98-111">Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="abd98-111">Send an email with audio conferencing information to a user</span></span>

### <a name="teams-logo-30x30pngmediateams-logo-30x30png-using-the-microsoft-teams-admin-center"></a>![команды логотип 30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="abd98-113">С помощью центра администрирования группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="abd98-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="abd98-114">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="abd98-114">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="abd98-115">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="abd98-115">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="abd98-116">В разделе **Аудиоконференции** щелкните **Отправить информацию для конференций в электронном письме**.</span><span class="sxs-lookup"><span data-stu-id="abd98-116">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="abd98-117">Что еще необходимо знать о таких сообщениях?</span><span class="sxs-lookup"><span data-stu-id="abd98-117">What else should you know about this email?</span></span>

- <span data-ttu-id="abd98-118">Существует несколько сообщений электронной почты, отправленных для пользователей в вашей организации после их, необходимо включить для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="abd98-118">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="abd98-119">При назначении пользователям лицензии **аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="abd98-119">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="abd98-120">При сбросе вручную аудиоконференций ПИН-код пользователя.</span><span class="sxs-lookup"><span data-stu-id="abd98-120">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="abd98-121">Выполнение сброса идентификатора конференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="abd98-121">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="abd98-122">При изъятии лицензии **аудиоконференций** у пользователя.</span><span class="sxs-lookup"><span data-stu-id="abd98-122">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="abd98-123">Поставщик услуг аудиоконференций для пользователя изменении корпорацией Майкрософт на другой поставщик или **Нет**.</span><span class="sxs-lookup"><span data-stu-id="abd98-123">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="abd98-124">При изменении поставщика аудиоконференций для пользователя в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="abd98-124">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="abd98-125">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="abd98-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="abd98-p102">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="abd98-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="abd98-129">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="abd98-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="abd98-130">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="abd98-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="abd98-131">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="abd98-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="abd98-132">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="abd98-132">Related topics</span></span>

[<span data-ttu-id="abd98-133">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="abd98-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
