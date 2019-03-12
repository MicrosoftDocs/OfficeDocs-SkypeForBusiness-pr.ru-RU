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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Описание шагов по сбросу идентификатора конференции для пользователя в Microsoft Teams, а также получения ссылок на средства для изменения и переноса собраний. '
ms.openlocfilehash: f5926d838d61d38eb5b8e9f840cd9d7a4694253f
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "30542849"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="91e46-103">Сброс идентификатора конференции для пользователя в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="91e46-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="91e46-104">Динамический идентификатор конференции указан в нижней части приглашений на собрания вместе с телефонными номерами, которые вызывающие абоненты могут использовать для подключения к собранию по телефону.</span><span class="sxs-lookup"><span data-stu-id="91e46-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="91e46-105">Когда пользователь наберет этот телефонный номер, автосекретарь собрания попросит его ввести идентификатор конференции, чтобы присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="91e46-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="91e46-106">Если вашим поставщиком услуг конференц-связи является корпорация Майкрософт, для идентификаторов конференции ваших пользователей по умолчанию задано значение Dynamic Only (Только динамические).</span><span class="sxs-lookup"><span data-stu-id="91e46-106">If your conferencing provider is Microsoft, your users' conference IDs are set to Dynamic Only by default.</span></span> <span data-ttu-id="91e46-107">К сожалению, нет никакой возможности сделать их статическими, так как сейчас эта функция не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="91e46-107">Unfortunately, there's no ability to change it to become static, as this is now unsupported.</span></span> <span data-ttu-id="91e46-108">Идентификаторы конференции автоматически задаются только для пользователей Microsoft Teams, для которых включена поддержка аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="91e46-108">Conference IDs are only automatically set for Microsoft Teams users enabled for Audio Conferencing.</span></span> 


## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="91e46-109">Сброс идентификатора конференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="91e46-109">Resetting the conference ID for a user</span></span>

<span data-ttu-id="91e46-110">![команды логотип 30x30.png](media/teams-logo-30x30.png) **с помощью центра администрирования группами Майкрософт**</span><span class="sxs-lookup"><span data-stu-id="91e46-110">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="91e46-111">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="91e46-111">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="91e46-112">Нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="91e46-112">Click **Edit**.</span></span>

3. <span data-ttu-id="91e46-113">В разделе **Аудиоконференции** щелкните **Сброс идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="91e46-113">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="91e46-114">В окне **сбросить идентификатор конференции** нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="91e46-114">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="91e46-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span><span class="sxs-lookup"><span data-stu-id="91e46-115">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="91e46-116">По умолчанию по электронной почте отправляются пользователям, но это может быть отключена.</span><span class="sxs-lookup"><span data-stu-id="91e46-116">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="91e46-117">После сброса идентификатора конференции на электронную почту пользователя отправляется сообщение с новым идентификатором конференции.</span><span class="sxs-lookup"><span data-stu-id="91e46-117">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="91e46-118">В большинстве случаев это сообщение электронной почты отправляется на основной адрес электронной почты, которым, как правило, является почтовый ящик Office 365.</span><span class="sxs-lookup"><span data-stu-id="91e46-118">This email will be sent to the primary email address, in many cases, their Office 365 mailbox.</span></span> <span data-ttu-id="91e46-119">Сообщение электронной почты содержит новый идентификатор конференции, номера телефона-связи по умолчанию и инструкции по обновлению существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="91e46-119">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="91e46-120">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="91e46-120">What else should I know?</span></span>

- <span data-ttu-id="91e46-121">Можно отправить все сведения конференц-связи для пользователя в сообщение электронной почты, включая идентификатор конференции и телефонные номера телефонов, нажав кнопку **Отправить конференции сведения в электронной почты** для пользователя в разделе **Audio конференц-связи** .</span><span class="sxs-lookup"><span data-stu-id="91e46-121">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="91e46-122">ПИН-код не отправляется.</span><span class="sxs-lookup"><span data-stu-id="91e46-122">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="91e46-123">Идентификатор конференции будет содержать 7 символов, а длина его изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="91e46-123">A conference ID will contain 7 digits, and you can't change its length.</span></span>
    
- <span data-ttu-id="91e46-124">После сброса новый идентификатор конференции будет отображаться в поле **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="91e46-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="91e46-125">После создания нового идентификатора конференции старый идентификатор не может использоваться для выполнения вызовов.</span><span class="sxs-lookup"><span data-stu-id="91e46-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="91e46-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="91e46-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="91e46-127">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="91e46-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="91e46-p107">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="91e46-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="91e46-131">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="91e46-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="91e46-132">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91e46-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="91e46-133">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="91e46-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="91e46-134">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="91e46-134">Related topics</span></span>

[<span data-ttu-id="91e46-135">Сброс ПИН-кода для аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="91e46-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
