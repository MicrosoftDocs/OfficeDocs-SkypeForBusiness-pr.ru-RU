---
title: Установка телефона, номера, находящимся на приглашает в группами Майкрософт
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
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Получите инструкции по созданию номер телефона по умолчанию для абонентов, чтобы присоединиться к собранию группами Майкрософт. '
ms.openlocfilehash: 20dfd4255cd41e9f5aebf419f77307b30fe40042
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "26533297"
---
# <a name="set-the-phone-numbers-included-on-invites-in-microsoft-teams"></a><span data-ttu-id="75d87-103">Настройка телефонных номеров, включаемых в приглашения в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="75d87-103">Set the phone numbers included on invites in Microsoft Teams</span></span>

<span data-ttu-id="75d87-104">Аудиоконференций в Office 365 позволяет пользователям в вашей организации для создания групп Майкрософт собраний и разрешить пользователям по телефонной линии к собраниям с помощью телефона.</span><span class="sxs-lookup"><span data-stu-id="75d87-104">Audio Conferencing in Office 365 enables users in your organization to create Microsoft Teams meetings, and then allow users to dial in to those meetings using a phone.</span></span>
  
<span data-ttu-id="75d87-p101">Мост конференц-связи предоставляет вашей организации ряд телефонных номеров для подключения. Все эти номера могут быть использованы для подключения к собраниям, созданным организаторами, однако вы можете выбрать, какие номера будут указаны в приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="75d87-p101">A conferencing bridge gives you a set of dial-in phone numbers for your organization. All of them can be used to join the meetings that a meeting organizer has created, but you can select which ones will be included on their meeting invites.</span></span>
  
> [!NOTE]
> <span data-ttu-id="75d87-107">Организатор собрания может использовать не более одного платного и одного бесплатного телефонного номера в приглашении на собрание, однако также имеется ссылка в нижней части приглашения на собрания, по которой открывается список всех телефонных номеров для подключения к собранию.</span><span class="sxs-lookup"><span data-stu-id="75d87-107">There can be a maximum of one toll and one toll-free phone number on the meeting invite for a meeting organizer, but there is also a link located at the bottom of each meeting invite that opens the full list of all dial-in phone numbers that can be used to join a meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="initial-assignment-of-phone-numbers-that-are-included-in-the-meeting-invites-for-new-users"></a><span data-ttu-id="75d87-108">Начальное назначение телефонных номеров, которые включены в собрание приглашает для новых пользователей</span><span class="sxs-lookup"><span data-stu-id="75d87-108">Initial assignment of phone numbers that are included in the meeting invites for new users</span></span>

<span data-ttu-id="75d87-109">Номера телефонов, включаются в собрание приглашает пользователей для определенных звук конференц-связи с номером телефона международную конференц-связи по умолчанию и параметры по умолчанию конференц-связи бесплатных телефонных номеров пользователя.</span><span class="sxs-lookup"><span data-stu-id="75d87-109">The phone numbers that get included in the meeting invites of users enabled for Audio Conferencing are defined by the default conferencing toll phone number and the default conferencing toll-free phone number user's settings.</span></span> <span data-ttu-id="75d87-110">Каждый параметр указывает, международную и телефоны, которые будут включены в приглашении на собрание указанного пользователя.</span><span class="sxs-lookup"><span data-stu-id="75d87-110">Each setting specifies which toll and toll-free number will be included in the meeting invite of a given user.</span></span> <span data-ttu-id="75d87-111">Как указано выше, каждый приглашение содержит один бесплатный номер, один необязательный телефоны и ссылку, которая открывает полный список всех телефонные номера телефонов, которые можно использовать для данного собранием.</span><span class="sxs-lookup"><span data-stu-id="75d87-111">As noted above, each meeting invite contains one toll number, one optional toll-free number and a link that opens the full list of all dial-in phone numbers that can be used to join a given meeting.</span></span>

<span data-ttu-id="75d87-112">Для нового пользователя платные номера конференц-связи по умолчанию назначается для страны, заданное в Office 365 профиля пользователя, если пользователя включена поддержка службы аудио конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="75d87-112">For a new user, the default conferencing toll numbers is assigned based on the country that is set in the Office 365 profile of the user when the user is enabled for the Audio Conferencing service.</span></span> <span data-ttu-id="75d87-113">Если в bridge конференции, которая соответствует страны пользователя бесплатный номер, этот номер автоматически назначается как номер счета по умолчанию пользователя.</span><span class="sxs-lookup"><span data-stu-id="75d87-113">If there is a toll number in the conference bridge that matches the country of the user, that number will be automatically assigned as the default toll number of the user.</span></span> <span data-ttu-id="75d87-114">Если нет, как номер счета по умолчанию пользователя будет назначен номер, который определяется как количество bridge конференции счета по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="75d87-114">If there isn't one, the number that is defined as the default toll number of the conference bridge will be assigned as the default toll number of the user.</span></span>  

<span data-ttu-id="75d87-115">После того как пользователь включен для службы аудио конференц-связи, международную по умолчанию и бесплатные номера телефонов пользователя можно менять администратор клиента из исходные значения в любой момент.</span><span class="sxs-lookup"><span data-stu-id="75d87-115">Once the user is enabled for the Audio Conferencing service, the default toll and toll-free phone numbers of the user can be changed by the tenant administrator from their initial values at any moment.</span></span>

## <a name="set-or-change-the-default-audio-conferencing-phone-number-for-a-meeting-organizer-or-user"></a><span data-ttu-id="75d87-116">Установить или изменить номер телефона по умолчанию аудиоконференций для организатора собрания или пользователя</span><span class="sxs-lookup"><span data-stu-id="75d87-116">Set or change the default audio conferencing phone number for a meeting organizer or user</span></span>

![команды логотип 30x30.png](media/teams-logo-30x30.png) <span data-ttu-id="75d87-118">Использование групп Майкрософт и Скайп по центру администрирования бизнеса</span><span class="sxs-lookup"><span data-stu-id="75d87-118">Using the Microsoft Teams and Skype for Business Admin Center</span></span>

1. <span data-ttu-id="75d87-119">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="75d87-119">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

    ![Показывает, Выбор пользователей в группы Microsoft и Скайп по центру администрирования Business](media/teamsselectusers.png)

2. <span data-ttu-id="75d87-121">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="75d87-121">At the top of the page, click **Edit**.</span></span>

    ![Нажмите кнопку Изменить в Microsoft групп и Скайп по центру администрирования Business](media/teamsedituser.png)

3. <span data-ttu-id="75d87-123">Рядом с пунктом **Аудиоконференции** нажмите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="75d87-123">Next to **Audio Conferencing**, click **Edit**.</span></span> 
    
    ![Нажмите кнопку Изменить рядом с пунктом аудиоконференции](media/teamseditaudioconf.png)

4. <span data-ttu-id="75d87-125">Использование полей **бесплатный номер** или **бесплатный номер** для ввода цифр для пользователя.</span><span class="sxs-lookup"><span data-stu-id="75d87-125">Use the **Toll number** or **Toll-free number** fields to enter the numbers for the user.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="75d87-126">При изменении параметров аудиоконференций пользователя повторяющиеся и будущих собраний группами Майкрософт должен быть обновлено и отправлены участникам.</span><span class="sxs-lookup"><span data-stu-id="75d87-126">When you change a user's audio conferencing settings, recurring and future Microsoft Teams meetings must be updated and sent to attendees.</span></span> 

## <a name="want-to-use-windows-powershell"></a><span data-ttu-id="75d87-127">Хотите использовать Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="75d87-127">Want to use Windows PowerShell?</span></span>

<span data-ttu-id="75d87-p104">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="75d87-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="75d87-131">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="75d87-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="75d87-132">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="75d87-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="75d87-133">Дополнительные сведения о Windows PowerShell см. в [справочнике по Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="75d87-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span> 
  
    
## <a name="related-topics"></a><span data-ttu-id="75d87-134">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="75d87-134">Related topics</span></span>

[<span data-ttu-id="75d87-135">Пробная и платная аудиоконференции в Office 365</span><span class="sxs-lookup"><span data-stu-id="75d87-135">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
