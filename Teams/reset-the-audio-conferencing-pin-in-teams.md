---
title: Сброс аудиоконференций ПИН-кода в группах Майкрософт
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Узнайте, что должен знать о ПИН-коды и сброс их в группах Майкрософт. '
ms.openlocfilehash: 4570c96ab529c114f2d0bb8708eb145650de18b1
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23866469"
---
# <a name="reset-the-audio-conferencing-pin-in-microsoft-teams"></a><span data-ttu-id="c14a8-103">Сброс аудиоконференций ПИН-кода в группах Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c14a8-103">Reset the Audio Conferencing PIN in Microsoft Teams</span></span>

<span data-ttu-id="c14a8-104">ПИН-кода представляет собой код, состоящих из номера, который создается для каждого пользователя группами Майкрософт, который включен для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="c14a8-104">A PIN is a code made up of numbers that is created for each Microsoft Teams user who is enabled for audio conferencing.</span></span> <span data-ttu-id="c14a8-105">ПИН-коды аудиоконференций используются Организаторы собраний для идентификации, что они Организатор собрания и запускать собрание по телефону.</span><span class="sxs-lookup"><span data-stu-id="c14a8-105">Audio conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="c14a8-106">При использовании приложения группами Майкрософт для начать собрание, ПИН-код не требуется.</span><span class="sxs-lookup"><span data-stu-id="c14a8-106">If they use the Microsoft Teams app to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="c14a8-107">Если пользователи забыли свой ПИН-код, и они не удается найти в сообщение электронной почты, которое было отправлено им, когда они были включены для аудиоконференций, администратор может сбросить свой ПИН-код или они могут изменять свои собственные ПИН-кода.</span><span class="sxs-lookup"><span data-stu-id="c14a8-107">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for audio conferencing, an administrator can reset their PIN, or they can reset their own PIN.</span></span>
  
<span data-ttu-id="c14a8-108">Собрания может запускаться при присоединении прошедшего проверку подлинности пользователя с помощью приложения Microsoft группами или когда Организатор соединения с свой ПИН-код по телефону.</span><span class="sxs-lookup"><span data-stu-id="c14a8-108">Meetings can be started when an authenticated user joins using the Microsoft Teams app or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="c14a8-109">Если для участия в телефонном собрании требуется ПИН-код, то все пользователи, подключившиеся к этому собранию по телефону, перенаправляются в зал ожидания и могут прослушивать музыку до начала собрания.</span><span class="sxs-lookup"><span data-stu-id="c14a8-109">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="c14a8-110">Если организатор собрания не запрашивает ПИН-код при открытии собрания по телефону, то при подключении к собранию участникам не потребуется вводить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="c14a8-110">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>

## <a name="reset-a-users-pin"></a><span data-ttu-id="c14a8-111">Сброс ПИН-код пользователя</span><span class="sxs-lookup"><span data-stu-id="c14a8-111">Reset a user's PIN</span></span>

1. <span data-ttu-id="c14a8-112">На панели навигации слева щелкните **Пользователи**и затем выберите пользователя в списке Доступные пользователи.</span><span class="sxs-lookup"><span data-stu-id="c14a8-112">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="c14a8-113">В верхней части страницы нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="c14a8-113">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="c14a8-114">В разделе **Audio конференц-связи**щелкните **Сброс ПИН-кода**.</span><span class="sxs-lookup"><span data-stu-id="c14a8-114">Under **Audio Conferencing**, click **Reset PIN**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="c14a8-115">У пользователя сбросить свой ПИН-кода</span><span class="sxs-lookup"><span data-stu-id="c14a8-115">Have a user reset his or her own PIN</span></span>

1. <span data-ttu-id="c14a8-116">Пользователь должен перейти к [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span><span class="sxs-lookup"><span data-stu-id="c14a8-116">Have the user go to [https://admin0m.online.lync.com/lscp/usp/pstnconferencing](https://admin0m.online.lync.com/lscp/usp/pstnconferencing).</span></span>
2. <span data-ttu-id="c14a8-117">Нажмите кнопку **сбросить ПИН-код**.</span><span class="sxs-lookup"><span data-stu-id="c14a8-117">Click **Reset PIN**.</span></span> 


## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="c14a8-118">Что еще необходимо знать о ПИН-кодах?</span><span class="sxs-lookup"><span data-stu-id="c14a8-118">What else should you know about PINs?</span></span>

- <span data-ttu-id="c14a8-119">В целях безопасности ПИН-код отображается однократно и только для администратора, выполняющего сброс.</span><span class="sxs-lookup"><span data-stu-id="c14a8-119">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="c14a8-120">После сброса ПИН-кода, администратор ПИН-код будет отображаться как \*\*\*.</span><span class="sxs-lookup"><span data-stu-id="c14a8-120">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\*.</span></span>
    
- <span data-ttu-id="c14a8-121">Автоматически отправлять сообщения электронной почты для пользователей включена по умолчанию, и пользователи будут получать сообщения электронной почты с свой ПИН-код, когда они будет включена поддержка аудиоконференций или когда сбросить ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="c14a8-121">Automatically sending emails to users is enabled by default, and users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="c14a8-122">Но если вы отключили автоматически отправка по электронной почте, электронной почты сброс ПИН-код не будут отправляться на пользователя и необходимо вручную отправлять сведения о ПИН пользователя.</span><span class="sxs-lookup"><span data-stu-id="c14a8-122">But if you have disabled automatically sending emails, a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="c14a8-p105">Когда начинается собрание, к нему автоматически присоединяются все пользователи, находящиеся в зале ожидания. Пример: если два участника попытаются присоединиться к собранию, когда оно еще не началось, эти участники будут перенаправлены в зал ожидания. Когда с телефона присоединяется организатор собрания под собственным ПИН-кодом, собрание начинается, и к нему подключаются все участники, находящиеся в зале ожидания.</span><span class="sxs-lookup"><span data-stu-id="c14a8-p105">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="c14a8-125">Значение по умолчанию — запретить собрания для работы с анонимных абонентов.</span><span class="sxs-lookup"><span data-stu-id="c14a8-125">The default setting is to not allow a meeting to be started by anonymous callers.</span></span>
    
- <span data-ttu-id="c14a8-126">При включении пользователя для аудиоконференций, по умолчанию они отправляются по электронной почте, которая содержит сведения о конференц-связи и свой ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="c14a8-126">When you enable a user for audio conferencing, by default they are sent emails that include conferencing information and their PIN.</span></span> <span data-ttu-id="c14a8-127">Пользователь должен иметь почтовый ящик Office 365, так как при сбросе ПИН-код новый ПИН-код будет отправляться пользователя по электронной почте для своих основной SMTP-адрес (псевдоним), который имеет значение для пользователя.</span><span class="sxs-lookup"><span data-stu-id="c14a8-127">The user must have an Office 365 mailbox, because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="c14a8-128">При настройке аудиоконференций задайте цифры, которые необходимы для контактов в организации.</span><span class="sxs-lookup"><span data-stu-id="c14a8-128">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="c14a8-129">ПИН-коды может составлять от 4 до 12 цифр — значение по умолчанию — 5.</span><span class="sxs-lookup"><span data-stu-id="c14a8-129">PINs can be from 4 to 12 digits - the default is 5.</span></span> <span data-ttu-id="c14a8-130">Если изменить параметр длина ПИН-кода, параметр применяется только на недавно созданный контакты и не применяется к параметру ПИН-кода для существующих пользователей, которые разрешены для аудиоконференций.</span><span class="sxs-lookup"><span data-stu-id="c14a8-130">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="c14a8-131">В разделе [задать длину ПИН-кода для собраний аудио конференц-связи](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c14a8-131">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams.md).</span></span>
    
- <span data-ttu-id="c14a8-132">Сообщение электронной почты по умолчанию будет иметь значение Office 365 основной SMTP-адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="c14a8-132">The email by default will be set to the Office 365 primary SMTP address of the user.</span></span> <span data-ttu-id="c14a8-133">Можно отправить сообщение электронной почты в Office 365 адрес, например Hotmail или адрес электронной почты MSN.</span><span class="sxs-lookup"><span data-stu-id="c14a8-133">You can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="c14a8-134">Адрес электронной почты по умолчанию можно переопределить с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c14a8-134">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="c14a8-135">Это полезно, если у пользователей нет почтового ящика Exchange в Office 365.</span><span class="sxs-lookup"><span data-stu-id="c14a8-135">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>

    

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="c14a8-136">Хотите узнать больше о Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c14a8-136">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="c14a8-p109">Windows PowerShell дает возможность управлять пользователями, предоставляя им права на определенные действия. С его помощью вы можете управлять Office 365, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.</span><span class="sxs-lookup"><span data-stu-id="c14a8-p109">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c14a8-140">Шесть причин использовать Windows PowerShell для управления Office 365</span><span class="sxs-lookup"><span data-stu-id="c14a8-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="c14a8-141">Лучшие способы управления Office 365 с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c14a8-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="c14a8-142">Дополнительные сведения о Windows PowerShell, [Справочник по Microsoft команды PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) для получения дополнительных сведений см.</span><span class="sxs-lookup"><span data-stu-id="c14a8-142">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c14a8-143">См. также:</span><span class="sxs-lookup"><span data-stu-id="c14a8-143">Related topics</span></span>

[<span data-ttu-id="c14a8-144">Сброс идентификатора конференции для пользователя</span><span class="sxs-lookup"><span data-stu-id="c14a8-144">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user-in-teams.md)
