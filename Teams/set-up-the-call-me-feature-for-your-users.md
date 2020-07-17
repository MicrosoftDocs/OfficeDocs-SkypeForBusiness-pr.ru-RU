---
title: Настройка функции "Позвонить мне" для пользователей
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: В этой статье объясняется, как настроить функцию "позвонить мне" в Teams, чтобы пользователи могли присоединиться к звуковому каналу на телефоне, если не удается использовать компьютер для звукового сигнала.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d29a517b8df194fe19b9e16554f7c57964177c90
ms.sourcegitcommit: 70b80892a152f86a6d596f0f5b58cf391bc29098
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/15/2020
ms.locfileid: "45138019"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="b9c3b-103">Настройка функции "Позвонить мне" для пользователей</span><span class="sxs-lookup"><span data-stu-id="b9c3b-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="b9c3b-104">В Microsoft Teams функция " **позвонить мне** " дает пользователям возможность присоединиться к звуковой части собрания по телефону.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="b9c3b-105">Это удобно в сценариях, если использование компьютера для звука может быть невозможным.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="b9c3b-106">Пользователи получают звуковое сопровождение собрания с помощью сотового телефона или земли, а также части собрания, &mdash; например, если у другого участника собрания есть общий доступ к экрану или воспроизведение видео &mdash; через компьютер.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="b9c3b-107">В течение периодов с большим объемом собраний, которые мы использовали в сочетании с COVID-19), мы рекомендуем пользователям присоединяться к собраниям, нажимая кнопку <strong>присоединиться</strong> к собранию, а не звонить с помощью номеров конференций PSTN или <strong>позвоните мне по телефону</strong>.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="b9c3b-108">Это помогает обеспечить качественный звук во время, когда высокая громкость собрания вызывает перегрузку в сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b9c3b-109">Во время вспышки COVID-19 мы рекомендуем пользователям присоединяться к собраниям, нажимая кнопку **Присоединиться к собранию Teams**, а не звонить по номеру конференции ТСОП и не использовать функцию **Позвонить мне на номер**</strong>.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-109">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="b9c3b-110">В основном это связано с нагрузкой на телефонную инфраструктуру в странах, пострадавших от эпидемии COVID-19.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-110">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="b9c3b-111">Избегая звонков по ТСОП, вы повысите качество звука.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-111">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="b9c3b-112">Взаимодействие с пользователем</span><span class="sxs-lookup"><span data-stu-id="b9c3b-112">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="b9c3b-113">Присоединение к собранию с помощью телефона для звукового сопровождения</span><span class="sxs-lookup"><span data-stu-id="b9c3b-113">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="b9c3b-114">Нажмите кнопку **присоединиться** , чтобы присоединиться к собранию, а затем на экране **выберите параметры звука и видео** нажмите кнопку **звук телефона** .</span><span class="sxs-lookup"><span data-stu-id="b9c3b-114">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="b9c3b-115">Отсюда пользователи могут звонить на собрание и присоединиться к ним или самостоятельно звонить в собрании.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-115">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Снимок экрана с параметром "звук телефона"](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="b9c3b-117">**Присоединение к собранию Teams**</span><span class="sxs-lookup"><span data-stu-id="b9c3b-117">**Let the Teams meeting call**</span></span>

<span data-ttu-id="b9c3b-118">На экране **использовать телефон для звука** пользователь вводит свой номер телефона, а затем щелкает " **позвонить мне**".</span><span class="sxs-lookup"><span data-stu-id="b9c3b-118">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="b9c3b-119">Собрание вызывает пользователя и присоединяется к собранию.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-119">The meeting calls the user and joins them to the meeting.</span></span>

![Снимок экрана с параметром "позвонить мне" на экране "Использование телефона для звука"](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="b9c3b-121">**Ручной набор номера**</span><span class="sxs-lookup"><span data-stu-id="b9c3b-121">**Dial in manually**</span></span>

<span data-ttu-id="b9c3b-122">Чтобы присоединиться к собранию, вы также можете набрать номер прямо так.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-122">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="b9c3b-123">На экране " **Использование телефона для звука** " нажмите кнопку " **набрать номер" вручную** , чтобы получить список номеров телефонов, которые нужно использовать для подключения к собранию.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-123">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Снимок экрана с параметром "набрать номер вручную"](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="b9c3b-125">Получение обратного вызова, когда что-то пошло не так со звуком во время собрания</span><span class="sxs-lookup"><span data-stu-id="b9c3b-125">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="b9c3b-126">При возникновении проблем со звуком при использовании компьютера во время собрания пользователь может легко переключиться на использование телефона для звукового сопровождения.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-126">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="b9c3b-127">В Teams обнаружена проблема, связанная с аудио-или устройством, и перенаправляет пользователя на использование своего телефона, отображая параметр " **позвонить мне назад** ".</span><span class="sxs-lookup"><span data-stu-id="b9c3b-127">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="b9c3b-128">Вот пример сообщения и параметр " **обратная звонок мне** ", который отображается, когда команды не обнаруживают микрофон.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-128">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Снимок экрана с параметром "Обратная звонок мне"](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="b9c3b-130">Пользователь нажимает кнопку " **позвонить мне назад**", что приводит к экрану " **Использование телефона для звука** ".</span><span class="sxs-lookup"><span data-stu-id="b9c3b-130">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="b9c3b-131">В этой статье они могут ввести номер телефона, а также присоединиться к собранию или вручную войти в собрание.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-131">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="b9c3b-132">Настройка функции "позвонить мне"</span><span class="sxs-lookup"><span data-stu-id="b9c3b-132">Set up the Call me feature</span></span>

<span data-ttu-id="b9c3b-133">Чтобы включить функцию "позвонить мне" для пользователей в вашей организации, необходимо настроить следующее:</span><span class="sxs-lookup"><span data-stu-id="b9c3b-133">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="b9c3b-134">Голосовая Конференция включена для пользователей в вашей организации, которые запланируют собрания (организаторов собраний).</span><span class="sxs-lookup"><span data-stu-id="b9c3b-134">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="b9c3b-135">Дополнительные сведения можно найти в разделе [Настройка голосовой конференции для Teams](set-up-audio-conferencing-in-teams.md) и [Управление параметрами голосовой конференции для пользователя в Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b9c3b-135">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="b9c3b-136">Пользователи могут звонить с собраний.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-136">Users can dial out from meetings.</span></span> <span data-ttu-id="b9c3b-137">Дополнительные сведения можно найти в разделе [Управление параметрами голосовой конференции для пользователя в Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b9c3b-137">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="b9c3b-138">Если пользователь не набирает звонок из включенных собраний, функция " **позвонить мне** " недоступна, и пользователь не получит звонок, чтобы присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-138">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="b9c3b-139">Вместо этого пользователь видит список номеров телефонов на экране " **Телефон** ", который можно использовать для подключения к собранию на телефоне вручную.</span><span class="sxs-lookup"><span data-stu-id="b9c3b-139">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
