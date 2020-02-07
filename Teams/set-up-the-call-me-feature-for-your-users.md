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
description: Сведения о том, как настроить функцию "позвонить мне" в Teams, чтобы пользователи могли присоединиться к звуковому каналу в сценариях, где использование компьютера для звука может быть невозможным.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe895fee4f3bc0872d277429289b5d04d6c9161d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837999"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="359b3-103">Настройка функции "Позвонить мне" для пользователей</span><span class="sxs-lookup"><span data-stu-id="359b3-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="359b3-104">В Microsoft Teams функция " **позвонить мне** " дает пользователям возможность присоединиться к звуковой части собрания по телефону.</span><span class="sxs-lookup"><span data-stu-id="359b3-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="359b3-105">Это удобно в сценариях, если использование компьютера для звука может быть невозможным.</span><span class="sxs-lookup"><span data-stu-id="359b3-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="359b3-106">Пользователи получают звуковое сопровождение собрания с помощью сотового телефона или земли, а также части собрания&mdash;, например, для другого участника собрания, который предоставляет доступ к своему экрану или&mdash;воспроизводит видео с помощью своего компьютера.</span><span class="sxs-lookup"><span data-stu-id="359b3-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

## <a name="the-user-experience"></a><span data-ttu-id="359b3-107">Взаимодействие с пользователем</span><span class="sxs-lookup"><span data-stu-id="359b3-107">The user experience</span></span>

### <a name="join-a-meeting-by-using-phone-for-audio"></a><span data-ttu-id="359b3-108">Присоединение к собранию с помощью телефона для звукового сопровождения</span><span class="sxs-lookup"><span data-stu-id="359b3-108">Join a meeting by using phone for audio</span></span>

<span data-ttu-id="359b3-109">Нажмите кнопку **присоединиться** , чтобы присоединиться к собранию, а затем на экране **выберите параметры звука и видео** нажмите кнопку **звук телефона** .</span><span class="sxs-lookup"><span data-stu-id="359b3-109">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="359b3-110">Отсюда пользователи могут звонить на собрание и присоединиться к ним или самостоятельно звонить в собрании.</span><span class="sxs-lookup"><span data-stu-id="359b3-110">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Снимок экрана с параметром "звук телефона"](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="359b3-112">**Присоединение к собранию Teams**</span><span class="sxs-lookup"><span data-stu-id="359b3-112">**Let the Teams meeting call**</span></span>

<span data-ttu-id="359b3-113">На экране **использовать телефон для звука** пользователь вводит свой номер телефона, а затем щелкает " **позвонить мне**".</span><span class="sxs-lookup"><span data-stu-id="359b3-113">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="359b3-114">Собрание вызывает пользователя и присоединяется к собранию.</span><span class="sxs-lookup"><span data-stu-id="359b3-114">The meeting calls the user and joins them to the meeting.</span></span>

![Снимок экрана с параметром "позвонить мне" на экране "Использование телефона для звука"](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="359b3-116">**Ручной набор номера**</span><span class="sxs-lookup"><span data-stu-id="359b3-116">**Dial in manually**</span></span>

<span data-ttu-id="359b3-117">Чтобы присоединиться к собранию, вы также можете набрать номер прямо так.</span><span class="sxs-lookup"><span data-stu-id="359b3-117">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="359b3-118">На экране " **Использование телефона для звука** " нажмите кнопку " **набрать номер" вручную** , чтобы получить список номеров телефонов, которые нужно использовать для подключения к собранию.</span><span class="sxs-lookup"><span data-stu-id="359b3-118">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Снимок экрана с параметром "набрать номер вручную"](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

### <a name="get-a-call-back-when-something-goes-wrong-with-audio-during-a-meeting"></a><span data-ttu-id="359b3-120">Получение обратного вызова, когда что-то пошло не так со звуком во время собрания</span><span class="sxs-lookup"><span data-stu-id="359b3-120">Get a call back when something goes wrong with audio during a meeting</span></span>

<span data-ttu-id="359b3-121">При возникновении проблем со звуком при использовании компьютера во время собрания пользователь может легко переключиться на использование телефона для звукового сопровождения.</span><span class="sxs-lookup"><span data-stu-id="359b3-121">If a user experiences audio issues when using their computer during a meeting, the user can easily switch to using their phone for audio.</span></span> <span data-ttu-id="359b3-122">В Teams обнаружена проблема, связанная с аудио-или устройством, и перенаправляет пользователя на использование своего телефона, отображая параметр " **позвонить мне назад** ".</span><span class="sxs-lookup"><span data-stu-id="359b3-122">Teams detects when an audio or device issue occurs and redirects the user to use their phone by displaying a **Call me back** option.</span></span>

<span data-ttu-id="359b3-123">Вот пример сообщения и параметр " **обратная звонок мне** ", который отображается, когда команды не обнаруживают микрофон.</span><span class="sxs-lookup"><span data-stu-id="359b3-123">Here's an example of the message and the **Call me back** option that's displayed when Teams doesn't detect a microphone.</span></span>

![Снимок экрана с параметром "Обратная звонок мне"](media/set-up-the-call-me-feature-for-your-users-no-mic.PNG)

<span data-ttu-id="359b3-125">Пользователь нажимает кнопку " **позвонить мне назад**", что приводит к экрану " **Использование телефона для звука** ".</span><span class="sxs-lookup"><span data-stu-id="359b3-125">The user clicks **Call me back**, which brings up the **Use phone for audio** screen.</span></span> <span data-ttu-id="359b3-126">В этой статье они могут ввести номер телефона, а также присоединиться к собранию или вручную войти в собрание.</span><span class="sxs-lookup"><span data-stu-id="359b3-126">From here, they can enter their phone number and have the Teams meeting call and join them to the meeting or dial in manually to the meeting.</span></span>

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="359b3-127">Настройка функции "позвонить мне"</span><span class="sxs-lookup"><span data-stu-id="359b3-127">Set up the Call me feature</span></span>

<span data-ttu-id="359b3-128">Чтобы включить функцию "позвонить мне" для пользователей в вашей организации, необходимо настроить следующее:</span><span class="sxs-lookup"><span data-stu-id="359b3-128">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="359b3-129">Голосовая Конференция включена для пользователей в вашей организации, которые запланируют собрания (организаторов собраний).</span><span class="sxs-lookup"><span data-stu-id="359b3-129">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="359b3-130">Дополнительные сведения можно найти в разделе [Настройка голосовой конференции для Teams](set-up-audio-conferencing-in-teams.md) и [Управление параметрами голосовой конференции для пользователя в Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="359b3-130">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="359b3-131">Пользователи могут звонить с собраний.</span><span class="sxs-lookup"><span data-stu-id="359b3-131">Users can dial out from meetings.</span></span> <span data-ttu-id="359b3-132">Дополнительные сведения можно найти в разделе [Управление параметрами голосовой конференции для пользователя в Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="359b3-132">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="359b3-133">Если пользователь не набирает звонок из включенных собраний, функция " **позвонить мне** " недоступна, и пользователь не получит звонок, чтобы присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="359b3-133">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="359b3-134">Вместо этого пользователь видит список номеров телефонов на экране " **Телефон** ", который можно использовать для подключения к собранию на телефоне вручную.</span><span class="sxs-lookup"><span data-stu-id="359b3-134">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>
