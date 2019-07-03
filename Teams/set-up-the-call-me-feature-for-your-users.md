---
title: Настройка функции "позвонить мне" для пользователей
author: LanaChin
ms.author: v-lanac
ms.reviewer: macai
manager: serdars
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Сведения о том, как настроить функцию "позвонить мне" в Teams, чтобы пользователи могли присоединиться к звуковому каналу в сценариях, где использование компьютера для звука может быть невозможным.
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3f1ffee416b1d5674e831fda4c5bb15a89c510f4
ms.sourcegitcommit: 1ddd29e3839e50387efb4ec7b9d2154991bb2642
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "35432145"
---
# <a name="set-up-the-call-me-feature-for-your-users"></a><span data-ttu-id="c4481-103">Настройка функции "позвонить мне" для пользователей</span><span class="sxs-lookup"><span data-stu-id="c4481-103">Set up the Call me feature for your users</span></span>

<span data-ttu-id="c4481-104">В Microsoft Teams функция " **позвонить мне** " дает пользователям возможность присоединиться к звуковой части собрания по телефону.</span><span class="sxs-lookup"><span data-stu-id="c4481-104">In Microsoft Teams, the **Call me** feature gives users a way to join the audio portion of a meeting by phone.</span></span> <span data-ttu-id="c4481-105">Это удобно в сценариях, если использование компьютера для звука может быть невозможным.</span><span class="sxs-lookup"><span data-stu-id="c4481-105">This is handy in scenarios when using a computer for audio might not be possible.</span></span> <span data-ttu-id="c4481-106">Пользователи получают звуковое сопровождение собрания с помощью сотового телефона или земли, а также части собрания&mdash;, например, для другого участника собрания, который предоставляет доступ к своему экрану или&mdash;воспроизводит видео с помощью своего компьютера.</span><span class="sxs-lookup"><span data-stu-id="c4481-106">Users get the audio portion of the meeting through their cell phone or land line and the content portion of the meeting&mdash;such when another meeting participant shares their screen or plays a video&mdash;through their computer.</span></span>

## <a name="the-user-experience"></a><span data-ttu-id="c4481-107">Взаимодействие с пользователем</span><span class="sxs-lookup"><span data-stu-id="c4481-107">The user experience</span></span>

<span data-ttu-id="c4481-108">Нажмите \*\*\*\* кнопку присоединиться, чтобы присоединиться к собранию, а затем на экране **выберите параметры звука и видео** нажмите кнопку **звук телефона** .</span><span class="sxs-lookup"><span data-stu-id="c4481-108">Click **Join** to join a meeting, and then click **Phone audio** on the  **Choose your audio and video settings** screen.</span></span> <span data-ttu-id="c4481-109">Отсюда пользователи могут звонить на собрание и присоединиться к ним или самостоятельно звонить в собрании.</span><span class="sxs-lookup"><span data-stu-id="c4481-109">From here, users can have the meeting call and join them or dial in manually to the meeting.</span></span>

![Снимок экрана с параметром "звук телефона"](media/set-up-the-call-me-feature-for-your-users-phone-audio.png)

<span data-ttu-id="c4481-111">**Присоединение к собранию Teams**</span><span class="sxs-lookup"><span data-stu-id="c4481-111">**Let the Teams meeting call**</span></span>

<span data-ttu-id="c4481-112">На экране **использовать телефон для звука** пользователь вводит свой номер телефона, а затем щелкает " **позвонить мне**".</span><span class="sxs-lookup"><span data-stu-id="c4481-112">On the **Use phone for audio** screen, the user enters their phone number, and then clicks **Call me**.</span></span> <span data-ttu-id="c4481-113">Собрание вызывает пользователя и присоединяется к собранию.</span><span class="sxs-lookup"><span data-stu-id="c4481-113">The meeting calls the user and joins them to the meeting.</span></span>

![Снимок экрана с параметром "позвонить мне" на экране "Использование телефона для звука"](media/set-up-the-call-me-feature-for-your-users-call-me.png)

<span data-ttu-id="c4481-115">**Ручной набор номера**</span><span class="sxs-lookup"><span data-stu-id="c4481-115">**Dial in manually**</span></span>

<span data-ttu-id="c4481-116">Чтобы присоединиться к собранию, вы также можете набрать номер прямо так.</span><span class="sxs-lookup"><span data-stu-id="c4481-116">Another way to join is to dial in directly to the meeting.</span></span> <span data-ttu-id="c4481-117">На экране " **Использование телефона для звука** " нажмите кнопку "набрать **номер" вручную** , чтобы получить список номеров телефонов, которые нужно использовать для подключения к собранию.</span><span class="sxs-lookup"><span data-stu-id="c4481-117">On the **Use phone for audio** screen, click **Dial in manually** to get a list of phone numbers to use to dial in to the meeting.</span></span>

![Снимок экрана с параметром "набрать номер вручную"](media/set-up-the-call-me-feature-for-your-users-dial-in.png)

## <a name="set-up-the-call-me-feature"></a><span data-ttu-id="c4481-119">Настройка функции "позвонить мне"</span><span class="sxs-lookup"><span data-stu-id="c4481-119">Set up the Call me feature</span></span>

<span data-ttu-id="c4481-120">Чтобы включить функцию "позвонить мне" для пользователей в вашей организации, необходимо настроить следующее:</span><span class="sxs-lookup"><span data-stu-id="c4481-120">To enable the Call me feature for users in your organization, the following must be configured:</span></span>

- <span data-ttu-id="c4481-121">Голосовая Конференция включена для пользователей в вашей организации, которые запланируют собрания (организаторов собраний).</span><span class="sxs-lookup"><span data-stu-id="c4481-121">Audio Conferencing is enabled for users in your organization who schedule meetings (meeting organizers).</span></span> <span data-ttu-id="c4481-122">Дополнительные сведения можно найти в разделе [Настройка голосовой конференции для Teams](set-up-audio-conferencing-in-teams.md) и [Управление параметрами голосовой конференции для пользователя в Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c4481-122">To learn more, see [Set up Audio Conferencing for Teams](set-up-audio-conferencing-in-teams.md) and [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

- <span data-ttu-id="c4481-123">Пользователи могут звонить с собраний.</span><span class="sxs-lookup"><span data-stu-id="c4481-123">Users can dial out from meetings.</span></span> <span data-ttu-id="c4481-124">Дополнительные сведения можно найти в разделе [Управление параметрами голосовой конференции для пользователя в Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c4481-124">To learn more, see [Manage the Audio Conferencing settings for a user in Teams](manage-the-audio-conferencing-settings-for-a-user-in-teams.md).</span></span>

<span data-ttu-id="c4481-125">Если пользователь не набирает звонок из включенных собраний, функция " **позвонить мне** " недоступна, и пользователь не получит звонок, чтобы присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="c4481-125">If a user doesn't have dial out from meetings enabled, the **Call me** option isn't available and the user won't receive a call to join them to the meeting.</span></span> <span data-ttu-id="c4481-126">Вместо этого пользователь видит список номеров телефонов на экране " **Телефон** ", который можно использовать для подключения к собранию на телефоне вручную.</span><span class="sxs-lookup"><span data-stu-id="c4481-126">Instead, the user sees a list of phone numbers on the **Use phone for audio** screen that they can use to dial in manually to the meeting on their phone.</span></span>

