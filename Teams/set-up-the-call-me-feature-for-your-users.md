---
title: Настройка функции "Позвонить мне" для пользователей
author: cichur
ms.author: v-cichur
ms.reviewer: macai, phedry
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
description: Узнайте, как настроить функцию "Звонок на мой номер" в Teams, чтобы пользователи могли присоединяться к звуковому сигналу по телефону при использовании компьютера для аудиосвязи, возможно, будет невозможно.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 04510a827e9343010c756b14590e9800354c71e9
ms.sourcegitcommit: f979c491af5210e6ceb1d1c00e000767f1a8311d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/07/2021
ms.locfileid: "51623137"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="64783-103">Настройка функции "Позвонить мне" для пользователей</span><span class="sxs-lookup"><span data-stu-id="64783-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="64783-104">В Microsoft Teams функция **"Звонок** на мой номер" позволяет пользователям присоединяться к звуковому фрагменту собрания по телефону.</span><span class="sxs-lookup"><span data-stu-id="64783-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="64783-105">Это удобно в сценариях, когда использовать компьютер для аудиосвязи может быть невозможно.</span><span class="sxs-lookup"><span data-stu-id="64783-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="64783-106">Пользователи получают звуковой сигнал собрания с помощью мобильного или мобильного телефона или мобильной связи, а также части содержимого собрания, например, когда другой участник собрания делится своим экраном или воспроизводит видео на своем &mdash; &mdash; компьютере.</span><span class="sxs-lookup"><span data-stu-id="64783-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="64783-107">В периоды высокой загруженности собраний (которая наблюдается в связи со вспышкой COVID-19) мы рекомендуем пользователям присоединяться к собраниям, нажимая кнопку <strong>Присоединиться к собранию Teams</strong>, а не звонить по номеру конференции ТСОП и не использовать функцию <strong>Позвонить мне на номер</strong>.</span><span class="sxs-lookup"><span data-stu-id="64783-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="64783-108">Это помогает обеспечить высокое качество звука, когда высокая громкость собрания вызывает перегрузку в сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="64783-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a><span data-ttu-id="64783-109">Пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="64783-109">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="64783-110">Присоединиться к собранию с помощью телефона для аудиосвязи</span><span class="sxs-lookup"><span data-stu-id="64783-110">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="64783-111">Нажмите **кнопку "Присоединиться",** чтобы  присоединиться к собранию, **а** затем выберите "Присоединиться сейчас" на экране "Выбор параметров звука и видео" и "Присоединиться **сейчас".**</span><span class="sxs-lookup"><span data-stu-id="64783-111">Click **Join** to join a meeting, then **Phone audio** on the **Choose your video and audio options** screen, and click **Join now**.</span></span> <span data-ttu-id="64783-112">Здесь пользователи могут присоединиться к собранию по телефону или присоединиться к собранию вручную.</span><span class="sxs-lookup"><span data-stu-id="64783-112">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Снимок экрана: параметр звука "Телефон"](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="64783-114">**Звонок на собрание Teams**</span><span class="sxs-lookup"><span data-stu-id="64783-114">**Let the Teams meeting call**</span></span>

<span data-ttu-id="64783-115">На экране **"Использовать телефон для звука"** пользователь вводит свой номер телефона и нажимает кнопку "Позвонить **мне".**</span><span class="sxs-lookup"><span data-stu-id="64783-115">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="64783-116">Собрание звонит пользователю и присоединяется к собранию.</span><span class="sxs-lookup"><span data-stu-id="64783-116">The meeting calls the user and joins them to the meeting.</span></span>

![Снимок экрана: параметр "Позвонить мне" на экране "Использовать телефон для звука"](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="64783-118">**Набор номера вручную**</span><span class="sxs-lookup"><span data-stu-id="64783-118">**Dial in manually**</span></span>

<span data-ttu-id="64783-119">Еще один способ присоединиться к собранию — позвонить прямо на собрание.</span><span class="sxs-lookup"><span data-stu-id="64783-119">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="64783-120">На экране **"Использовать телефон**  для звука" нажмите кнопку "Набрать номер вручную", чтобы получить список номеров телефонов для телефонного звонка.</span><span class="sxs-lookup"><span data-stu-id="64783-120">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Снимок экрана: параметр "Позвонить вручную"](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="64783-122">Звонок обратно, если во время собрания что-то пошло не так со звуком</span><span class="sxs-lookup"><span data-stu-id="64783-122">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="64783-123">Если у пользователя во время собрания проблемы со звуком, он может легко переключиться на телефон.</span><span class="sxs-lookup"><span data-stu-id="64783-123">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="64783-124">Teams определяет, когда возникает проблема со звуком или устройством, и перенаправляет пользователя на телефон, отображая параметр **"Перезвонить мне".**</span><span class="sxs-lookup"><span data-stu-id="64783-124">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="64783-125">Вот пример сообщения и параметра  "Перезвонить мне", отображаемого, когда Teams не обнаруживает микрофон.</span><span class="sxs-lookup"><span data-stu-id="64783-125">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Снимок экрана: параметр "Перезвонить мне"](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="64783-127">Пользователь нажимает кнопку **"Перезвонить мне",** что приводит к экрану **"Использовать телефон для звука".**</span><span class="sxs-lookup"><span data-stu-id="64783-127">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="64783-128">Здесь он может ввести свой номер телефона, получить звонок на собрание Teams и присоединиться к собранию или присоединиться к собранию по телефону вручную.</span><span class="sxs-lookup"><span data-stu-id="64783-128">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="64783-129">Настройка функции "Звонок на мой звонок"</span><span class="sxs-lookup"><span data-stu-id="64783-129">Set up the Call me feature</span></span>

<span data-ttu-id="64783-130">Чтобы включить функцию "Звонок на мой телефон" для пользователей в организации, необходимо настроить следующее:</span><span class="sxs-lookup"><span data-stu-id="64783-130">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="64783-131">Аудиоконференция включена для пользователей в организации, планющих собрания (организаторов собраний).</span><span class="sxs-lookup"><span data-stu-id="64783-131">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="64783-132">Дополнительные данные см. в настройках аудиоконференций для [Teams](set-up-audio-conferencing-in-teams.md) и управлении настройками аудиоконференции для пользователя [в Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="64783-132">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="64783-133">Организатор собрания может звонить из собраний по номерам.</span><span class="sxs-lookup"><span data-stu-id="64783-133">Meeting organizer can dial-out from meetings.</span></span> <span data-ttu-id="64783-134">Дополнительные данные см. в управлении настройками аудиоконференции [для пользователя в Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="64783-134">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="64783-135">Если у организатора собрания не включен звонок из  собраний, параметр  "Телефон" на экране "Выбрать параметры видео- и аудиосвязи" будет недоступным для всех, а другие пользователи не смогут принимать звонки, чтобы присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="64783-135">If the meeting organizer doesn't have dial-out from meetings enabled, the **Phone audio** option on the **Choose your video and audio options** screen isn't available to anyone, and other users can't receive a call to join them to the meeting.</span></span> <span data-ttu-id="64783-136">Если для пользователей включена возможность телефонного набора, после присоединиться к собранию они могут присоединиться к другим пользователям, набрав свой номер с помощью значка **"Показать участников".**</span><span class="sxs-lookup"><span data-stu-id="64783-136">For users with dial-out enabled, once they have joined the meeting, they can join others dialing their number from the **Show participants** icon.</span></span>
