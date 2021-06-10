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
description: Узнайте, как настроить функцию "Звонок на мой номер" в Teams, чтобы пользователи могли присоединяться к звуковому экрану по телефону при использовании компьютера для аудиосвязи, возможно, будет невозможно.
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
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="0bd06-103">Настройка функции "Позвонить мне" для пользователей</span><span class="sxs-lookup"><span data-stu-id="0bd06-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="0bd06-104">В Microsoft Teams с помощью  функции Звонок на мой номер пользователи могут присоединяться к звуковому собранию по телефону.</span><span class="sxs-lookup"><span data-stu-id="0bd06-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="0bd06-105">Это удобно в сценариях, когда использовать компьютер для аудиосвязи может быть невозможно.</span><span class="sxs-lookup"><span data-stu-id="0bd06-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="0bd06-106">Пользователи получают звуковой сигнал собрания по мобильному или мобильному телефону, а также содержимое собрания, например, когда другой участник собрания делится экраном или воспроизводит видео на своем &mdash; &mdash; компьютере.</span><span class="sxs-lookup"><span data-stu-id="0bd06-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such as when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="0bd06-107">В периоды высокой загруженности собраний (которая наблюдается в связи со вспышкой COVID-19) мы рекомендуем пользователям присоединяться к собраниям, нажимая кнопку <strong>Присоединиться к собранию Teams</strong>, а не звонить по номеру конференции ТСОП и не использовать функцию <strong>Позвонить мне на номер</strong>.</span><span class="sxs-lookup"><span data-stu-id="0bd06-107">During periods of high meeting volume (which we've been experiencing in conjunction with the COVID-19 outbreak), we recommend that users join meetings by clicking the <strong>Join Teams Meeting</strong> button rather than dialing in by using the PSTN conference numbers or by using <strong>Call me at</strong>.</span></span> <span data-ttu-id="0bd06-108">Это помогает обеспечить высокое качество звука, когда высокая громкость собрания вызывает перегрузку в сети ТСОП.</span><span class="sxs-lookup"><span data-stu-id="0bd06-108">This helps ensure quality audio during times when high meeting volume is causing congestion on the PSTN network.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="the-user-experience"></a><span data-ttu-id="0bd06-109">Пользовательский интерфейс</span><span class="sxs-lookup"><span data-stu-id="0bd06-109">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="0bd06-110">Присоединиться к собранию с помощью телефона для аудиосвязи</span><span class="sxs-lookup"><span data-stu-id="0bd06-110">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="0bd06-111">Нажмите **присоединиться,** чтобы присоединиться к **собранию,**  Телефон звук на экране Выберите параметры видео и звука, а затем нажмите **Присоединиться сейчас**.</span><span class="sxs-lookup"><span data-stu-id="0bd06-111">Click **Join** to join a meeting, then **Phone audio** on the **Choose your video and audio options** screen, and click **Join now**.</span></span> <span data-ttu-id="0bd06-112">Здесь пользователи могут присоединиться к собранию и присоединиться к нему или присоединиться к собранию вручную.</span><span class="sxs-lookup"><span data-stu-id="0bd06-112">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Снимок экрана: параметр Телефон звука](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="0bd06-114">**Звонок Teams собрания**</span><span class="sxs-lookup"><span data-stu-id="0bd06-114">**Let the Teams meeting call**</span></span>

<span data-ttu-id="0bd06-115">На экране **Использовать телефон для звука** пользователь вводит свой номер телефона и нажимает звонок на мой **номер**.</span><span class="sxs-lookup"><span data-stu-id="0bd06-115">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="0bd06-116">Собрание вызывает пользователя и присоединяет его к собранию.</span><span class="sxs-lookup"><span data-stu-id="0bd06-116">The meeting calls the user and joins them to the meeting.</span></span>

![Снимок экрана: параметр "Позвонить мне" на экране "Использовать телефон для звука"](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="0bd06-118">**Набор номера вручную**</span><span class="sxs-lookup"><span data-stu-id="0bd06-118">**Dial in manually**</span></span>

<span data-ttu-id="0bd06-119">Кроме того, можно присоединиться к собранию по телефонной телефонии.</span><span class="sxs-lookup"><span data-stu-id="0bd06-119">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="0bd06-120">На экране Использовать телефон для  **звука** щелкните Позвонить вручную, чтобы получить список номеров телефонов, которые нужно использовать для телефонного звонка к собранию.</span><span class="sxs-lookup"><span data-stu-id="0bd06-120">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Снимок экрана: параметр "Позвонить вручную"](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="0bd06-122">Вернуть звонок, если во время собрания что-то пошло не так со звуком</span><span class="sxs-lookup"><span data-stu-id="0bd06-122">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="0bd06-123">Если во время собрания у пользователя проблемы со звуком, он может легко переключиться на использование телефона для аудиосвязи.</span><span class="sxs-lookup"><span data-stu-id="0bd06-123">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="0bd06-124">Teams обнаруживает, когда возникают проблемы со звуком или устройством, и перенаправляет пользователя на использование телефона с помощью параметра **Перезвонить мне.**</span><span class="sxs-lookup"><span data-stu-id="0bd06-124">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="0bd06-125">Вот пример сообщения и параметра  Перезвонить мне, который отображается, когда Teams не обнаруживает микрофон.</span><span class="sxs-lookup"><span data-stu-id="0bd06-125">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Снимок экрана: параметр "Перезвонить мне"](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="0bd06-127">Пользователь щелкнуть **Перезвонить** мне , чтобы отозвать экран Использовать **телефон для звука.**</span><span class="sxs-lookup"><span data-stu-id="0bd06-127">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="0bd06-128">Здесь он может ввести свой номер телефона, Teams присоединиться к собранию или присоединиться к собранию по телефону вручную.</span><span class="sxs-lookup"><span data-stu-id="0bd06-128">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="0bd06-129">Настройка функции "Позвонить мне"</span><span class="sxs-lookup"><span data-stu-id="0bd06-129">Set up the Call me feature</span></span>

<span data-ttu-id="0bd06-130">Чтобы включить функцию Звонок на мой звонок для пользователей в организации, необходимо настроить следующие настройки:</span><span class="sxs-lookup"><span data-stu-id="0bd06-130">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="0bd06-131">Аудиоконференция включена для пользователей в организации, планющих собрания (организаторов собраний).</span><span class="sxs-lookup"><span data-stu-id="0bd06-131">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="0bd06-132">Дополнительные данные [](set-up-audio-conferencing-in-teams.md) см. в настройках аудиоконференций для Teams и Управление настройками аудиоконференции для пользователя в [Teams.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="0bd06-132">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="0bd06-133">Организатор собрания может звонить из собраний по номеру.</span><span class="sxs-lookup"><span data-stu-id="0bd06-133">Meeting organizer can dial-out from meetings.</span></span> <span data-ttu-id="0bd06-134">Дополнительные данные [см.](manage-the-audio-conferencing-settings-for-a-user-in-teams.md)в этой Teams.</span><span class="sxs-lookup"><span data-stu-id="0bd06-134">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="0bd06-135">Если у организатора собрания не включен звонок из  собраний, параметр аудио  Телефон на экране Выберите параметры видео и звука не доступен ни для кого, а другие пользователи не могут принимать звонок, чтобы присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="0bd06-135">If the meeting organizer doesn't have dial-out from meetings enabled, the **Phone audio** option on the **Choose your video and audio options** screen isn't available to anyone, and other users can't receive a call to join them to the meeting.</span></span> <span data-ttu-id="0bd06-136">Если у пользователей включена возможность телефонного связи, после присоединившись к собранию, они могут присоединиться к другим пользователям, набрав свой номер с помощью значка **Показать** участников.</span><span class="sxs-lookup"><span data-stu-id="0bd06-136">For users with dial-out enabled, once they have joined the meeting, they can join others dialing their number from the **Show participants** icon.</span></span>
