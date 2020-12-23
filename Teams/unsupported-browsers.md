---
title: Собрания Microsoft Teams в неподтверченных браузерах
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
MS.collection:
- M365-collaboration
ms.reviewer: nakulm
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как Teams поддерживает звук и видео в неподдержках браузеров.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 51d19affd962b396af42f4efaec707388b186094
ms.sourcegitcommit: 27fb021e46d775652a99d862b19d94f3fc020594
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778051"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="5c22d-103">Собрания Microsoft Teams в неподтверченных браузерах</span><span class="sxs-lookup"><span data-stu-id="5c22d-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="5c22d-104">Некоторые браузеры, такие как Internet Explorer 11, Safari и Firefox, поддерживают веб-приложение Microsoft Teams, но не поддерживают некоторые функции звонков и собраний Teams.</span><span class="sxs-lookup"><span data-stu-id="5c22d-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="5c22d-105">Чтобы обойти это ограничение, веб-приложение Teams позволяет пользователям получать звук через подключение по STN и просматривать содержимое (демонстрацию экрана) с уменьшенной скоростью отображения.</span><span class="sxs-lookup"><span data-stu-id="5c22d-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

> [!Note]
> <span data-ttu-id="5c22d-106">С 17 августа 2021 г. приложения и службы Microsoft 365 не будут поддерживать Internet Explorer 11 (Microsoft Teams не будет поддерживать Internet Explorer 11 ранее, начиная с 30 ноября 2020 г.).</span><span class="sxs-lookup"><span data-stu-id="5c22d-106">Microsoft 365 apps and services will not support Internet Explorer 11 starting August 17, 2021 (Microsoft Teams will not support Internet Explorer 11 earlier, starting  November 30, 2020).</span></span> <span data-ttu-id="5c22d-107">[Подробнее](https://aka.ms/AA97tsw).</span><span class="sxs-lookup"><span data-stu-id="5c22d-107">[Learn more](https://aka.ms/AA97tsw).</span></span> <span data-ttu-id="5c22d-108">Обратите внимание, что Internet Explorer 11 останется поддерживаемым браузером.</span><span class="sxs-lookup"><span data-stu-id="5c22d-108">Please note that Internet Explorer 11 will remain a supported browser.</span></span> <span data-ttu-id="5c22d-109">Internet Explorer 11 — это компонент [](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) операционной системы Windows, который следует политике жизненного цикла продукта, на который она установлена.</span><span class="sxs-lookup"><span data-stu-id="5c22d-109">Internet Explorer 11 is a component of the Windows operating system and [follows the Lifecycle Policy](https://docs.microsoft.com/lifecycle/faq/internet-explorer-microsoft-edge) for the product on which it is  installed.</span></span>

<span data-ttu-id="5c22d-110">Когда Teams обнаруживает неподписаный браузер, оно автоматически отображает сообщение с объяснением проблемы и ограничениями сеанса.</span><span class="sxs-lookup"><span data-stu-id="5c22d-110">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="5c22d-111">В сообщении содержатся дополнительные инструкции по доступу к звуковому сопровождению собрания, например поречение пользователю оставить номер обратного звонка, чтобы Teams могли позвонить пользователю, или проинструкции пользователю позвонить на номер конференции, включенный в приглашение на собрание.</span><span class="sxs-lookup"><span data-stu-id="5c22d-111">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="5c22d-112">Это сообщение также побуждает пользователя скачать и использовать настольный [клиент Teams](https://teams.microsoft.com/downloads) для полной работы с Teams.</span><span class="sxs-lookup"><span data-stu-id="5c22d-112">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="5c22d-113">Если ДНР недоступна, пользователь не увидит инструкции по доступу к собранию и не сможет присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="5c22d-113">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="5c22d-114">Ограничения браузера</span><span class="sxs-lookup"><span data-stu-id="5c22d-114">Browser limitations</span></span>

<span data-ttu-id="5c22d-115">Пользователи, которые используют веб-приложение Teams в неподтверченных браузерах, будут пользоваться следующими ограничениями:</span><span class="sxs-lookup"><span data-stu-id="5c22d-115">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="5c22d-116">Звук доступен только через подключение по ННР.</span><span class="sxs-lookup"><span data-stu-id="5c22d-116">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="5c22d-117">Пользователи не могут использовать микрофон.</span><span class="sxs-lookup"><span data-stu-id="5c22d-117">Users can't use their microphone.</span></span>
- <span data-ttu-id="5c22d-118">Пользователи не могут делиться камерой или просматривать видео других участников, но могут просматривать содержимое с помощью изображения.</span><span class="sxs-lookup"><span data-stu-id="5c22d-118">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="5c22d-119">Пользователи не могут делиться своим экраном, хотя они видят экран, который может видеть другой участник собрания.</span><span class="sxs-lookup"><span data-stu-id="5c22d-119">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="5c22d-120">Пользователи не могут управлять во время сеанса совместного доступа к экрану.</span><span class="sxs-lookup"><span data-stu-id="5c22d-120">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="5c22d-121">Пользователи не будут получать уведомления о входящих звонках.</span><span class="sxs-lookup"><span data-stu-id="5c22d-121">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="5c22d-122">Если звонок прерывается, подключение к собранию автоматически не происходит.</span><span class="sxs-lookup"><span data-stu-id="5c22d-122">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="5c22d-123">Пользователи не могут начинать собрания.</span><span class="sxs-lookup"><span data-stu-id="5c22d-123">Users can't start meetings.</span></span>

<span data-ttu-id="5c22d-124">Дополнительные сведения о поддержке браузеров в Teams см. в ограничениях и [спецификациях Teams.](/microsoftteams/limits-specifications-teams#browsers)</span><span class="sxs-lookup"><span data-stu-id="5c22d-124">For more information about browser support in Teams, see [Limits and specifications for Teams](/microsoftteams/limits-specifications-teams#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="5c22d-125">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="5c22d-125">Related topics</span></span>

- [<span data-ttu-id="5c22d-126">Присоединяйтесь к собранию Teams в неподтверченном браузере</span><span class="sxs-lookup"><span data-stu-id="5c22d-126">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
