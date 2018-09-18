---
title: Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords: None
ms.custom:
- Audio Conferencing
description: Сведения об отправке пользователям сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams.
ms.openlocfilehash: 85e219481884bb08a2574809b6170c232abccf83
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "23892094"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-microsoft-teams"></a><span data-ttu-id="6d065-103">Отправка пользователю сообщения электронной почты со сведениями об аудиоконференции в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6d065-103">See Send an email to a user with their Audio Conferencing information.</span></span>

<span data-ttu-id="6d065-104">Иногда пользователям Microsoft Teams требуется, чтобы вы отправляли им информацию об аудиоконференциях.</span><span class="sxs-lookup"><span data-stu-id="6d065-104">Sometimes Skype for Business users may need you to send them their Audio Conferencing information.</span></span> <span data-ttu-id="6d065-105">Вы можете сделать это, выбрав пункт **Отправить сведения о конференции по эл. почте** в свойствах для пользователя.</span><span class="sxs-lookup"><span data-stu-id="6d065-105">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the dial-in properties for a user.</span></span> <span data-ttu-id="6d065-106">Отправляемое сообщение будет содержать всю информацию об аудиоконференции, включая следующее:</span><span class="sxs-lookup"><span data-stu-id="6d065-106">When you send this email, it will contain all of the dial-in information including:</span></span>
  
- <span data-ttu-id="6d065-107">телефонный номер конференции или номер телефонного подключения для пользователя;</span><span class="sxs-lookup"><span data-stu-id="6d065-107">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="6d065-108">идентификатор конференции пользователя.</span><span class="sxs-lookup"><span data-stu-id="6d065-108">The user's conference ID.</span></span>
    
   
<span data-ttu-id="6d065-109">Далее приведен пример отправляемого сообщения электронной почты:</span><span class="sxs-lookup"><span data-stu-id="6d065-109">Here is an example of the email that is sent to users that are enabled for dial-in conferencing:</span></span>
  
![Сообщение о конференц-связи с телефонным подключением](media/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="6d065-111">Отправка пользователю сообщения электронной почты с информацией для участия в аудиоконференциях</span><span class="sxs-lookup"><span data-stu-id="6d065-111">Send an email with audio conferencing information to a user</span></span>

1. <span data-ttu-id="6d065-112">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="6d065-112">In the **Skype for Business admin center**, in the left navigation go to Audio conferencingDial-in users, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="6d065-113">В верхней части страницы щелкните на элементе **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="6d065-113">At the top of the Conference Bridges page, click Bridge Settings.</span></span>

3. <span data-ttu-id="6d065-114">В области **Аудиоконференции** щелкните на элементе **Отправить сведения о конференции по эл. почте**.</span><span class="sxs-lookup"><span data-stu-id="6d065-114">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>


## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="6d065-115">Что еще нужно знать о таких сообщениях?</span><span class="sxs-lookup"><span data-stu-id="6d065-115">What else should you know about this email?</span></span>

- <span data-ttu-id="6d065-116">Когда пользователям в вашей организации разрешены аудиоконференции, им направляется несколько сообщений электронной почты в следующих случаях.</span><span class="sxs-lookup"><span data-stu-id="6d065-116">There are several emails that are set to users in your organization after they are enabled for dial-in conferencing:</span></span>
    
  - <span data-ttu-id="6d065-117">При назначении пользователям лицензии **аудиоконференций**.</span><span class="sxs-lookup"><span data-stu-id="6d065-117">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="6d065-118">Сброс ПИН-кода аудиоконференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="6d065-118">When you manually reset the user's dial-in conferencing PIN.</span></span>
    
  - <span data-ttu-id="6d065-119">Сброс идентификатора конференции пользователя вручную.</span><span class="sxs-lookup"><span data-stu-id="6d065-119">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="6d065-120">При изъятии лицензии **аудиоконференций** у пользователя.</span><span class="sxs-lookup"><span data-stu-id="6d065-120">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="6d065-121">Изменение поставщика услуг аудиоконференций с Майкрософт на другого поставщика или на значение **Нет**.</span><span class="sxs-lookup"><span data-stu-id="6d065-121">When the dial-in conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="6d065-122">Изменение поставщика услуг аудиоконференций на Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="6d065-122">When the dial-in conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="6d065-123">По умолчанию эти сообщения электронной почты отправляются из Office 365, но вы можете изменить адрес электронной почты и отображаемое имя с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6d065-123">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and the Set-CsOnlineDialInConferencingTenantSettings cmdlet.</span></span> <span data-ttu-id="6d065-124">Дополнительные сведения см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="6d065-124">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6d065-125">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="6d065-125">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="6d065-p103">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="6d065-p103">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6d065-129">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="6d065-129">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="6d065-130">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6d065-130">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="6d065-131">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="6d065-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="6d065-132">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="6d065-132">Related topics</span></span>

[<span data-ttu-id="6d065-133">Оцените или приобретите аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="6d065-133">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
