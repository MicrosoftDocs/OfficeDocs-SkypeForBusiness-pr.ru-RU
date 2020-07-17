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
description: Выполните указанные ниже действия, чтобы создать телефонный номер по умолчанию для абонентов, которые могут присоединиться к собранию Microsoft Teams.
ms.openlocfilehash: bd8ca4729a991582588f09e8c230e57983cd1a87
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021767"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="965b5-103">Настройка телефонных номеров, включаемых в приглашения в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="965b5-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="965b5-104">Голосовой Конференц-связь в Microsoft 365 и Office 365 позволяет пользователям в организации создавать собрания Microsoft Teams, а затем разрешать пользователям подключаться к этим собраниям с помощью телефона.</span><span class="sxs-lookup"><span data-stu-id="965b5-104">Audio Conferencing in Microsoft 365 and Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="965b5-p101">Мост конференц-связи предоставляет вашей организации ряд телефонных номеров для подключения. Все эти номера могут быть использованы для подключения к собраниям, созданным организаторами, однако вы можете выбрать, какие номера будут указаны в приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="965b5-p101">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="965b5-107">Организатор собрания может использовать не более одного платного и одного бесплатного телефонного номера в приглашении на собрание, однако также имеется ссылка в нижней части приглашения на собрания, по которой открывается список всех телефонных номеров для подключения к собранию.</span><span class="sxs-lookup"><span data-stu-id="965b5-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="965b5-108">Начальное назначение телефонных номеров, включенных в приглашения на собрания для новых пользователей</span><span class="sxs-lookup"><span data-stu-id="965b5-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="965b5-109">Номера телефонов, которые будут включены в приглашения на собрания пользователей, для которых разрешено звуковое сопровождение, определяются с помощью телефонного номера конференц-связи по умолчанию, а также с помощью параметров по умолчанию для бесплатных телефонных номеров.</span><span class="sxs-lookup"><span data-stu-id="965b5-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="965b5-110">Каждый параметр указывает, какой платный и бесплатный номер будет включен в приглашение на собрание определенного пользователя.</span><span class="sxs-lookup"><span data-stu-id="965b5-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="965b5-111">Как указано выше, каждое приглашение на собрание содержало один платный номер, один опциональный бесплатный номер и ссылку, которая открывает полный список всех телефонных номеров для подключения, которые можно использовать для присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="965b5-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="965b5-112">Для нового пользователя телефонные номера конференц-связи по умолчанию назначаются в зависимости от места использования, которое задается в центре администрирования Microsoft 365, когда пользователь включает службу голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="965b5-112">For a new user, the default conferencing toll numbers is assigned based on the Usage Location that is set in the Microsoft 365 administration center of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="965b5-113">Если в Мосте Конференции есть платный номер, который соответствует стране пользователя, этот номер будет автоматически назначаться в качестве номера по умолчанию для пользователя.</span><span class="sxs-lookup"><span data-stu-id="965b5-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="965b5-114">Если это не так, номер, который определен как платный номер моста конференции, будет назначен в качестве номера по умолчанию для телефонной связи пользователя.</span><span class="sxs-lookup"><span data-stu-id="965b5-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="965b5-115">После того как пользователь сможет пользоваться службой голосовой связи, администратор клиента может в любой момент изменить значения по умолчанию для платных и бесплатных телефонных номеров пользователя.</span><span class="sxs-lookup"><span data-stu-id="965b5-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="965b5-116">Установка или изменение номера телефона для конференц-связи по умолчанию для организатора собрания или пользователя</span><span class="sxs-lookup"><span data-stu-id="965b5-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

<span data-ttu-id="965b5-117">![Значок с логотипом Microsoft Teams](media/teams-logo-30x30.png) **Использование центра администрирования Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="965b5-117">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="965b5-118">Вы должны быть администратором, чтобы внести эти изменения.</span><span class="sxs-lookup"><span data-stu-id="965b5-118">You must be an admin to make these changes.</span></span>

1. <span data-ttu-id="965b5-119">Войдите в центр администрирования Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="965b5-119">Log in to the Microsoft Teams admin center.</span></span>

2. <span data-ttu-id="965b5-120">На панели навигации слева выберите пункт **Пользователи**.</span><span class="sxs-lookup"><span data-stu-id="965b5-120">In the left navigation, click **Users**.</span></span>

    ![Показывает, как выбрать пользователей в центре администрирования Microsoft Teams](media/Admin-users.png)

3. <span data-ttu-id="965b5-122">Щелкните имя пользователя в списке доступных пользователей.</span><span class="sxs-lookup"><span data-stu-id="965b5-122">Click the user name from the list of available users.</span></span>

4. <span data-ttu-id="965b5-123">Рядом с пунктом **Аудиоконференции** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="965b5-123">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Нажмите кнопку "Изменить" рядом с кнопкой "звуковые конференции"](media/teams-set-phone-numbers-on-invites-image3.png)

5. <span data-ttu-id="965b5-125">Чтобы ввести номера для пользователя, используйте поля **платный номер** или бесплатный **номер** .</span><span class="sxs-lookup"><span data-stu-id="965b5-125">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="965b5-126">Когда вы изменяете настройки голосовой конференции пользователя, повторяющиеся и будущие собрания Microsoft Teams должны быть обновлены и отправлены участникам.</span><span class="sxs-lookup"><span data-stu-id="965b5-126">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="965b5-127">Хотите использовать Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="965b5-127">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="965b5-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="965b5-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="965b5-129">С помощью Windows PowerShell можно управлять Microsoft 365 или Office 365, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач.</span><span class="sxs-lookup"><span data-stu-id="965b5-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="965b5-130">Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="965b5-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="965b5-131">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="965b5-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="965b5-132">Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="965b5-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="965b5-133">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="965b5-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="965b5-134">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="965b5-134">Related topics</span></span>

[<span data-ttu-id="965b5-135">Попробуйте или купите голосовую конференцию в Microsoft 365 или Office 365</span><span class="sxs-lookup"><span data-stu-id="965b5-135">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)

[<span data-ttu-id="965b5-136">Изменение номеров телефонов для моста аудиоконференций</span><span class="sxs-lookup"><span data-stu-id="965b5-136">Change the phone numbers on your Audio Conferencing bridge</span></span>](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)
