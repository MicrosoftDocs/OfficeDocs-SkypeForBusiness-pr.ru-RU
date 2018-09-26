---
title: Сброс идентификатора конференции для пользователя в Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 6e12242c-55f7-4bf4-90d7-0f36c0326b8e
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Описание шагов по сбросу идентификатора конференции для пользователя в Microsoft Teams, а также получения ссылок на средства для изменения и переноса собраний. '
ms.openlocfilehash: bed015c92e197c1ee2dc1b48e495eee98445e3f0
ms.sourcegitcommit: 090ff859083ace43c08d483f4023009e8b6e79e4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/26/2018
ms.locfileid: "25019046"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="3f57a-103">Сброс идентификатора конференции для пользователя в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f57a-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="3f57a-104">Идентификатор динамических конференции включен в нижней части приглашения, а также телефонные номера телефонов, можно использовать абонентов, чтобы позвонить собрание.</span><span class="sxs-lookup"><span data-stu-id="3f57a-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="3f57a-105">Когда пользователь набирает номер телефона, автосекретаря собрания запросит вызывающему введите этот идентификатор конференции, поэтому они могут участниками собрания.</span><span class="sxs-lookup"><span data-stu-id="3f57a-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3f57a-106">Если ваш поставщик конференц-связи Microsoft, идентификаторы пользователей конференции устанавливаются динамических только по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3f57a-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="3f57a-107">К сожалению, существует возможность изменять перестанет статическими, поскольку это теперь не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3f57a-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="3f57a-108">Идентификаторы конференции только автоматически устанавливаются группами Майкрософт пользователям, включенным для аудиоконференции.</span><span class="sxs-lookup"><span data-stu-id="3f57a-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="3f57a-109">Сброс идентификатора конференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="3f57a-109">Resetting the conference ID for a user</span></span>

![команды логотип 30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="3f57a-111">Использование групп Майкрософт и Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="3f57a-111">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="3f57a-112">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="3f57a-112">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="3f57a-113">Нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="3f57a-113">Click **Edit**.</span></span>

3. <span data-ttu-id="3f57a-114">В разделе **Аудиоконференции** щелкните **Сброс идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="3f57a-114">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="3f57a-115">В окне **сбросить идентификатор конференции** нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="3f57a-115">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="3f57a-116">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="3f57a-116">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="3f57a-117">По умолчанию по электронной почте отправляются пользователям, но это может быть отключена.</span><span class="sxs-lookup"><span data-stu-id="3f57a-117">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="3f57a-118">После сброса идентификатора конференции на электронную почту пользователя отправляется сообщение с новым идентификатором конференции.</span><span class="sxs-lookup"><span data-stu-id="3f57a-118">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="3f57a-119">В большинстве случаев это сообщение электронной почты отправляется на основной адрес электронной почты, которым, как правило, является почтовый ящик Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f57a-119">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="3f57a-120">Сообщение электронной почты содержит новый идентификатор конференции, номера телефона-связи по умолчанию и инструкции по обновлению существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="3f57a-120">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="3f57a-121">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="3f57a-121">What else should I know?</span></span>

- <span data-ttu-id="3f57a-122">Можно отправить все сведения конференц-связи для пользователя в сообщение электронной почты, включая идентификатор конференции и телефонные номера телефонов, нажав кнопку **Отправить конференции сведения в электронной почты** для пользователя в разделе **Audio конференц-связи** .</span><span class="sxs-lookup"><span data-stu-id="3f57a-122">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="3f57a-123">ПИН-код не отправляется.</span><span class="sxs-lookup"><span data-stu-id="3f57a-123">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="3f57a-124">Идентификатор конференции будет содержать 7 символов, а длина его изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="3f57a-124">A conference ID will contain 7 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="3f57a-125">После сброса новый идентификатор конференции будет отображаться в поле **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="3f57a-125">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="3f57a-126">После создания нового идентификатора конференции старый идентификатор не может использоваться для выполнения вызовов.</span><span class="sxs-lookup"><span data-stu-id="3f57a-126">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="3f57a-127">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="3f57a-127">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="3f57a-128">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="3f57a-128">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="3f57a-p107">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="3f57a-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="3f57a-132">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="3f57a-132">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="3f57a-133">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f57a-133">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="3f57a-134">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="3f57a-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="3f57a-135">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="3f57a-135">Related topics</span></span>

[<span data-ttu-id="3f57a-136">Сброс аудиоконференций ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="3f57a-136">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
