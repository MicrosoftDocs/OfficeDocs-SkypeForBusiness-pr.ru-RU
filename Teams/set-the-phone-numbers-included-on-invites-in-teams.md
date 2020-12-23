---
title: Указание номеров телефонов, которые можно включать в приглашения
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
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
description: Выполните эти действия, чтобы создать номер телефона по умолчанию для участников собрания Microsoft Teams.
ms.openlocfilehash: 7dd59950403543074d8428d35270ab963ca824e3
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372188"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="0fa0e-103">Настройка телефонных номеров, включаемых в приглашения в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0fa0e-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="0fa0e-104">Аудиоконференция в Microsoft 365 и Office 365 позволяет пользователям в вашей организации создавать собрания Microsoft Teams, а затем позволять пользователям звонить на эти собрания по телефону.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-104">Audio Conferencing in Microsoft 365 and Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="0fa0e-p101">Мост конференц-связи предоставляет вашей организации ряд телефонных номеров для подключения. Все эти номера могут быть использованы для подключения к собраниям, созданным организаторами, однако вы можете выбрать, какие номера будут указаны в приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-p101">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0fa0e-107">Организатор собрания может использовать не более одного платного и одного бесплатного телефонного номера в приглашении на собрание, однако также имеется ссылка в нижней части приглашения на собрания, по которой открывается список всех телефонных номеров для подключения к собранию.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="0fa0e-108">Начальное назначение номеров телефонов, включенных в приглашения на собрание для новых пользователей</span><span class="sxs-lookup"><span data-stu-id="0fa0e-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="0fa0e-109">Номера телефонов, которые включаются в приглашения пользователей, включенных в аудиоконференцию, определяются платным номером для аудиоконференции по умолчанию и его настройками.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="0fa0e-110">Каждый параметр определяет, какой платный и бесплатный номер будет включен в приглашение на собрание данного пользователя.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="0fa0e-111">Как было отмечено выше, каждое приглашение на собрание содержит один платный номер, один необязательный бесплатный номер и ссылку, которая открывает полный список всех телефонных номеров для звонков, которые можно использовать для звонков на собрание.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="0fa0e-112">Для нового пользователя платные номера для аудиоконференции по умолчанию устанавливаются на основе расположения использования, заного в Центре администрирования Microsoft 365 пользователя, если для пользователя включена служба аудиоконференации.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Microsoft 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="0fa0e-113">Если на мосте конференц-залов есть платный номер, соответствующий стране пользователя, он будет автоматически назначен в качестве платного номера по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="0fa0e-114">Если такой учетной записи нет, платный номер моста конференц-залов по умолчанию будет назначен как платный номер по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="0fa0e-115">После включения службы аудиоконференций администратор клиента в любой момент может изменить платные и бесплатные номера телефонов пользователя по умолчанию с исходными значениями.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="0fa0e-116">Настройка или изменение номера аудиоконференции по умолчанию для организатора или пользователя собрания</span><span class="sxs-lookup"><span data-stu-id="0fa0e-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="0fa0e-117">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="0fa0e-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="0fa0e-118">Вносить эти изменения может только администратор служб Teams.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-118">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="0fa0e-119">См. [статью "Использование](https://docs.microsoft.com/microsoftteams/using-admin-roles) ролей администратора Teams для управления Teams", чтобы ознакомиться с получением ролей и разрешений администраторов.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-119">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="0fa0e-120">Войдите в Центр администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-120">Log in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="0fa0e-121">В области навигации слева выберите **"Пользователи".**</span><span class="sxs-lookup"><span data-stu-id="0fa0e-121">In the left navigation, click **Users**.</span></span>

    ![Выбор пользователей в Центре администрирования Microsoft Teams](media/Admin-users.png)

3. <span data-ttu-id="0fa0e-123">Щелкните имя пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-123">Click the user name from the list of available users.</span></span>

4. <span data-ttu-id="0fa0e-124">Рядом с пунктом **Аудиоконференции** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-124">Next to **Audio Conferencing**, click **Edit**.</span></span>

    ![Нажмите кнопку "Изменить" рядом с аудиоконференцией](media/teams-set-phone-numbers-on-invites-image3.png)

5. <span data-ttu-id="0fa0e-126">Используйте поля **"Платный"** или **"Бесплатный номер",** чтобы ввести номера для пользователя.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-126">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0fa0e-127">При изменении параметров аудиоконференции необходимо обновить и отправить участникам повторяющиеся и будущие собрания Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-127">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span>

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="0fa0e-128">Хотите использовать Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0fa0e-128">Want to use Windows PowerShell</span></span>

<span data-ttu-id="0fa0e-129">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-129">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="0fa0e-130">С Windows PowerShell вы можете управлять Microsoft 365 или Office 365, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-130">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="0fa0e-131">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="0fa0e-131">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="0fa0e-132">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="0fa0e-132">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- [<span data-ttu-id="0fa0e-133">Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0fa0e-133">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="0fa0e-134">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="0fa0e-134">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="0fa0e-135">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="0fa0e-135">Related topics</span></span>

[<span data-ttu-id="0fa0e-136">Попробуйте или приобретйте аудиоконференцию в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="0fa0e-136">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="0fa0e-137">Изменение номеров телефонов для моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="0fa0e-137">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
