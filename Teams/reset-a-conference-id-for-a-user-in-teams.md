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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Описание шагов по сбросу идентификатора конференции для пользователя в Microsoft Teams, а также получения ссылок на средства для изменения и переноса собраний.
ms.openlocfilehash: 52b547fee5bf027bcef21914e3ba3aa79b0e4e08
ms.sourcegitcommit: 7a9c63ee790108eaa61950ce28ae8027311039d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662129"
---
# <a name="reset-a-conference-id-for-a-user-in-microsoft-teams"></a><span data-ttu-id="75c6a-103">Сброс идентификатора конференции для пользователя в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="75c6a-103">Reset a conference ID for a user in Microsoft Teams</span></span>

<span data-ttu-id="75c6a-104">Динамический идентификатор конференции указан в нижней части приглашений на собрания вместе с телефонными номерами, которые вызывающие абоненты могут использовать для подключения к собранию по телефону.</span><span class="sxs-lookup"><span data-stu-id="75c6a-104">A dynamic conference ID is included at the bottom of meeting invitations along with the dial-in phone numbers that can be used by callers to call in to a meeting.</span></span> <span data-ttu-id="75c6a-105">Когда пользователь наберет этот телефонный номер, автосекретарь собрания попросит его ввести идентификатор конференции, чтобы присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="75c6a-105">When the user dials the phone number, the auto attendant for the meeting will ask the caller to enter this conference ID so they can attend the meeting.</span></span>
  
> [!NOTE]
> <span data-ttu-id="75c6a-106">Коды конференций создаются автоматически, от 7 до 9 цифр и задаются при включке аудиоконференции для пользователя.</span><span class="sxs-lookup"><span data-stu-id="75c6a-106">Conference IDs are generated automatically, will be between 7-9 digits, and are set when you enable Audio Conferencing for a user.</span></span> <span data-ttu-id="75c6a-107">**Статические ИД конференции не поддерживаются.**</span><span class="sxs-lookup"><span data-stu-id="75c6a-107">**Static conference IDs aren't supported.**</span></span> 

## <a name="resetting-the-conference-id-for-a-user"></a><span data-ttu-id="75c6a-108">Сброс ИД конференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="75c6a-108">Resetting the conference ID for a user</span></span>

<span data-ttu-id="75c6a-109">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="75c6a-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="75c6a-110">В левой области навигации щелкните на элементе **Пользователи** и выберите пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="75c6a-110">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="75c6a-111">Нажмите **кнопку "Изменить".**</span><span class="sxs-lookup"><span data-stu-id="75c6a-111">Click **Edit**.</span></span>

3. <span data-ttu-id="75c6a-112">В области **Аудиоконференции** щелкните на элементе **Сбросить идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="75c6a-112">Under **Audio Conferencing** click **Reset conference ID**.</span></span>

2. <span data-ttu-id="75c6a-113">В окне **Сбросить идентификатор конференции** нажмите кнопку **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="75c6a-113">In the **Reset conference ID** window, click **Reset**.</span></span> <span data-ttu-id="75c6a-114">Автоматически создается идентификатор конференции, после чего пользователю отправляется сообщение электронной почты с новым идентификатором.</span><span class="sxs-lookup"><span data-stu-id="75c6a-114">A conference ID will be automatically created and an email sent to the user with the new conference ID.</span></span> <span data-ttu-id="75c6a-115">По умолчанию сообщения пользователям отправляются, но это можно отключить.</span><span class="sxs-lookup"><span data-stu-id="75c6a-115">By default, emails are sent to users, but this can be turned off.</span></span>   

    
> [!NOTE]
> <span data-ttu-id="75c6a-116">После сброса идентификатора конференции на электронную почту пользователя отправляется сообщение с новым идентификатором конференции.</span><span class="sxs-lookup"><span data-stu-id="75c6a-116">After you reset the conference ID, an email with the new conference ID will be sent to the user.</span></span> <span data-ttu-id="75c6a-117">Во многих случаях это сообщение электронной почты отправляется на основной адрес электронной почты их почтового ящика Microsoft 365 или Office 365.</span><span class="sxs-lookup"><span data-stu-id="75c6a-117">This email will be sent to the primary email address, in many cases, their Microsoft 365 or Office 365 mailbox.</span></span> <span data-ttu-id="75c6a-118">Сообщение электронной почты содержит новый идентификатор конференции, номера для телефонного подключения по умолчанию и инструкции по изменению существующих собраний.</span><span class="sxs-lookup"><span data-stu-id="75c6a-118">The email contains the new conference ID, default dial-in phone number(s) and instructions for updating existing meetings.</span></span> 
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="what-else-should-i-know"></a><span data-ttu-id="75c6a-119">Что еще мне нужно знать?</span><span class="sxs-lookup"><span data-stu-id="75c6a-119">What else should I know?</span></span>

- <span data-ttu-id="75c6a-120">Всю информацию о конференц-связи, включая идентификатор конференции и номера для телефонного подключения, можно отправить пользователю по электронной почте, щелкнув элемент **Отправить сведения о конференции по эл. почте** в разделе **Аудиоконференции**.</span><span class="sxs-lookup"><span data-stu-id="75c6a-120">You can send all of the conferencing information to the user in an email that includes the conference ID and dial-in phone numbers by clicking **Send conference info in email** for the user in the **Audio Conferencing** section.</span></span> <span data-ttu-id="75c6a-121">При этом ПИН-код не отправляется.</span><span class="sxs-lookup"><span data-stu-id="75c6a-121">It doesn't send the PIN.</span></span>
    
- <span data-ttu-id="75c6a-122">Служба Teams создает 7–9-значный код конференции.</span><span class="sxs-lookup"><span data-stu-id="75c6a-122">A 7- 9 digit conference ID is created by the Teams service.</span></span> <span data-ttu-id="75c6a-123">Длину этой области изменить нельзя.</span><span class="sxs-lookup"><span data-stu-id="75c6a-123">You can't change its length.</span></span>
    
- <span data-ttu-id="75c6a-124">После сброса новый идентификатор конференции будет отображаться в поле **Идентификатор конференции**.</span><span class="sxs-lookup"><span data-stu-id="75c6a-124">After it has been reset, you can see the new conference ID listed under **Conference ID**.</span></span>
    
- <span data-ttu-id="75c6a-125">После создания нового идентификатора конференции старый идентификатор не может использоваться для выполнения вызовов.</span><span class="sxs-lookup"><span data-stu-id="75c6a-125">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="75c6a-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="75c6a-126">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> 

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="75c6a-127">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="75c6a-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="75c6a-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="75c6a-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="75c6a-129">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="75c6a-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="75c6a-130">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="75c6a-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="75c6a-131">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="75c6a-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="75c6a-132">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="75c6a-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="75c6a-133">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="75c6a-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="75c6a-134">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="75c6a-134">Related topics</span></span>

[<span data-ttu-id="75c6a-135">Сброс ПИН-кода для аудиоконференции</span><span class="sxs-lookup"><span data-stu-id="75c6a-135">Reset the Audio Conferencing PIN</span></span>](reset-the-audio-conferencing-pin-in-teams.md)
