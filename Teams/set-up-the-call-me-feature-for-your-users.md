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
description: Узнайте, как настроить функцию "Звонок на мой номер" в Teams, чтобы пользователи могли присоединяться к звуковому сигналу по телефону, используя компьютер для аудиосвязи.
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
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="e3d59-103">Настройка функции "Позвонить мне" для пользователей</span><span class="sxs-lookup"><span data-stu-id="e3d59-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="e3d59-104">В Microsoft Teams функция **"Звонок на мой** номер" позволяет пользователям присоединиться к звуковому фрагменту собрания по телефону.</span><span class="sxs-lookup"><span data-stu-id="e3d59-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="e3d59-105">Это удобно в сценариях, когда использовать компьютер для аудиосвязи может быть невозможно.</span><span class="sxs-lookup"><span data-stu-id="e3d59-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="e3d59-106">Пользователи получают звуковой сигнал собрания через мобильный или мобильный телефон, а также часть содержимого собрания, например, когда другой участник собрания делится своим экраном или воспроизводит видео на своем &mdash; &mdash; компьютере.</span><span class="sxs-lookup"><span data-stu-id="e3d59-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="e3d59-107">В периоды высокой загруженности собраний (которая наблюдается в связи со вспышкой COVID-19) мы рекомендуем пользователям присоединяться к собраниям, нажимая кнопку <strong>Присоединиться к собранию Teams</strong>, а не звонить по номеру конференции ТСОП и не использовать функцию <strong>Позвонить мне на номер</strong>.</span><span class="sxs-lookup"><span data-stu-id="e3d59-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="e3d59-108">Это помогает обеспечить высокое качество звука, когда высокая громкость собрания вызывает перегрузку в сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="e3d59-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="e3d59-109">Во время вспышки COVID-19 мы рекомендуем пользователям присоединяться к собраниям, нажимая кнопку **Присоединиться к собранию Teams**, а не звонить по номеру конференции ТСОП и не использовать функцию **Позвонить мне на номер**</strong>.</span><span class="sxs-lookup"><span data-stu-id="e3d59-109">During the duration of the COVID-19 outbreak, we recommend that users join meetings by clicking the **Join Teams Meeting** button rather than dialing in by using the PSTN conference numbers or by using **Call me at**</strong>.</span></span> <span data-ttu-id="e3d59-110">В основном это связано с нагрузкой на телефонную инфраструктуру в странах, пострадавших от эпидемии COVID-19.</span><span class="sxs-lookup"><span data-stu-id="e3d59-110">This is primarily because of congestion in the telephony infrastructures of countries impacted by COVID-19.</span></span> <span data-ttu-id="e3d59-111">Избегая звонков по ТСОП, вы повысите качество звука.</span><span class="sxs-lookup"><span data-stu-id="e3d59-111">By avoiding PSTN calls, you'll likely experience better audio quality.</span></span> 

## <a name="the-user-experience"></a><span data-ttu-id="e3d59-112">Пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="e3d59-112">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="e3d59-113">Присоединиться к собранию с помощью телефона для аудиосвязи</span><span class="sxs-lookup"><span data-stu-id="e3d59-113">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="e3d59-114">Нажмите **кнопку** "Присоединиться", чтобы присоединиться к собранию, а затем нажмите кнопку "Телефон" на экране "Выбор параметров звука и **видео".** </span><span class="sxs-lookup"><span data-stu-id="e3d59-114">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="e3d59-115">Здесь пользователи могут присоединиться к собранию по телефону или присоединиться к собранию вручную.</span><span class="sxs-lookup"><span data-stu-id="e3d59-115">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Снимок экрана: параметр звука телефона](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="e3d59-117">**Звонок на собрание Teams**</span><span class="sxs-lookup"><span data-stu-id="e3d59-117">**Let the Teams meeting call**</span></span>

<span data-ttu-id="e3d59-118">На экране **"Использовать телефон для звука"** пользователь вводит свой номер телефона и нажимает кнопку "Позвонить **мне".**</span><span class="sxs-lookup"><span data-stu-id="e3d59-118">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="e3d59-119">Собрание звонит пользователю и присоединяется к собранию.</span><span class="sxs-lookup"><span data-stu-id="e3d59-119">The meeting calls the user and joins them to the meeting.</span></span>

![Снимок экрана: параметр "Позвонить мне" на экране "Использовать телефон для звука"](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="e3d59-121">**Набор номера вручную**</span><span class="sxs-lookup"><span data-stu-id="e3d59-121">**Dial in manually**</span></span>

<span data-ttu-id="e3d59-122">Еще один способ присоединиться к собранию — позвонить прямо на собрание.</span><span class="sxs-lookup"><span data-stu-id="e3d59-122">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="e3d59-123">На экране **"Использовать телефон**  для звука" нажмите кнопку "Набрать номер вручную", чтобы получить список номеров телефонов для телефонного звонка на собрание.</span><span class="sxs-lookup"><span data-stu-id="e3d59-123">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Снимок экрана: параметр "Набрать номер вручную"](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="e3d59-125">Ответ на звонок, если во время собрания что-то пошло не так со звуком</span><span class="sxs-lookup"><span data-stu-id="e3d59-125">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="e3d59-126">Если у пользователя во время собрания проблемы со звуком, он может легко переключиться на телефон.</span><span class="sxs-lookup"><span data-stu-id="e3d59-126">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="e3d59-127">Teams определяет, когда возникает проблема со звуком или устройством, и перенаправляет пользователя на телефон, отображая параметр **"Перезвонить мне".**</span><span class="sxs-lookup"><span data-stu-id="e3d59-127">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="e3d59-128">Вот пример сообщения и параметра  "Перезвонить мне", отображаемого, когда Teams не обнаруживает микрофон.</span><span class="sxs-lookup"><span data-stu-id="e3d59-128">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Снимок экрана: параметр "Перезвонить мне"](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="e3d59-130">Пользователь нажимает кнопку **"Перезвонить мне",** что приводит к экрану **"Использовать телефон для звука".**</span><span class="sxs-lookup"><span data-stu-id="e3d59-130">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="e3d59-131">Здесь он может ввести свой номер телефона, получить звонок на собрание Teams и присоединиться к собранию или присоединиться к собранию по телефону вручную.</span><span class="sxs-lookup"><span data-stu-id="e3d59-131">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="e3d59-132">Настройка функции "Звонок на мой звонок"</span><span class="sxs-lookup"><span data-stu-id="e3d59-132">Set up the Call me feature</span></span>

<span data-ttu-id="e3d59-133">Чтобы включить функцию "Звонок на мой телефон" для пользователей в организации, необходимо настроить следующее:</span><span class="sxs-lookup"><span data-stu-id="e3d59-133">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="e3d59-134">Аудиоконференция включена для пользователей в организации, планющих собрания (организаторов собраний).</span><span class="sxs-lookup"><span data-stu-id="e3d59-134">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="e3d59-135">Дополнительные данные см. в настройках аудиоконференций для [Teams](set-up-audio-conferencing-in-teams.md) и управлении настройками аудиоконференции для пользователя [в Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e3d59-135">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="e3d59-136">Пользователи могут звонить из собраний по телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="e3d59-136">Users can dial out from meetings.</span></span> <span data-ttu-id="e3d59-137">Дополнительные данные см. в настройках аудиоконференции для [пользователя в Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e3d59-137">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="e3d59-138">Если для пользователя не включен звонок из собраний, параметр "Звонок на мой номер" будет не доступен, а пользователь не получит звонок, чтобы присоединиться к собранию. </span><span class="sxs-lookup"><span data-stu-id="e3d59-138">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="e3d59-139">Вместо этого на экране "Использование телефона  для аудио" пользователь видит список номеров, которые можно использовать для телефонного звонка к собранию вручную.</span><span class="sxs-lookup"><span data-stu-id="e3d59-139">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
