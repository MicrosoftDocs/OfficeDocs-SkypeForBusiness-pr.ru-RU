---
title: Собрания Microsoft Teams для неподдерживаемых браузеров
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
description: Сведения о том, как команды поддерживают звук и видео в неподдерживаемых браузерах.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1dfd2ba704aa2428555dd126c506e1673a120b72
ms.sourcegitcommit: 46b15a11755a89526be2a0b20befad61c628cdb4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955718"
---
# <a name="microsoft-teams-meetings-on-unsupported-browsers"></a><span data-ttu-id="b5a78-103">Собрания Microsoft Teams для неподдерживаемых браузеров</span><span class="sxs-lookup"><span data-stu-id="b5a78-103">Microsoft Teams meetings on unsupported browsers</span></span>

<span data-ttu-id="b5a78-104">Некоторые браузеры, например Internet Explorer 11, Safari и Firefox, поддерживают приложение Microsoft Teams Web App, но не поддерживают некоторые функции звонков и собраний в Teams.</span><span class="sxs-lookup"><span data-stu-id="b5a78-104">Some browsers, such as Internet Explorer 11, Safari, and Firefox, support the Microsoft Teams web app but don't support some of the Teams calling and meeting features.</span></span> <span data-ttu-id="b5a78-105">Чтобы обойти это ограничение, веб-приложение Teams позволяет пользователям получать звук через КОММУТИРУЕМое соединение и позволяет им просматривать представленное содержимое (демонстрация экрана) с уменьшенной частотой отображения.</span><span class="sxs-lookup"><span data-stu-id="b5a78-105">To work around this limitation, the Teams web app lets users receive audio through a PSTN connection and lets them view presented content (screen share) at a reduced display rate.</span></span>

<span data-ttu-id="b5a78-106">Если Teams обнаруживает неподдерживаемый браузер, он автоматически отображает сообщение, объясняющее ошибку, и ограничения сеанса.</span><span class="sxs-lookup"><span data-stu-id="b5a78-106">When Teams detects an unsupported browser, it automatically displays a message explaining the issue and the session limitations.</span></span> <span data-ttu-id="b5a78-107">Это сообщение содержит дополнительные инструкции по доступу к звуковому каналу собрания, например предписывает пользователю оставить номер для выхода из нее, чтобы участники команды могли позвонить пользователю или дать ему возможность позвонить по номеру конференции, указанному в приглашении на собрание.</span><span class="sxs-lookup"><span data-stu-id="b5a78-107">The message provides further instructions for accessing the meeting audio, such as advising the user to leave a call back number so that Teams can call the user, or instructing the user to call the conference number included in the meeting invitation.</span></span> <span data-ttu-id="b5a78-108">Это сообщение также способствует скачиванию и использованию [настольного клиента Teams](https://teams.microsoft.com/downloads) для полноценной работы с Teams.</span><span class="sxs-lookup"><span data-stu-id="b5a78-108">The message also encourages the user to download and use the [Teams desktop client](https://teams.microsoft.com/downloads) for the full Teams experience.</span></span>

<span data-ttu-id="b5a78-109">Если PSTN недоступна, пользователь не увидит инструкции для доступа к собранию и не сможет присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="b5a78-109">If PSTN is unavailable, the user won't see the instructions for accessing the meeting and won't be able to join the meeting.</span></span>

## <a name="browser-limitations"></a><span data-ttu-id="b5a78-110">Ограничения браузера</span><span class="sxs-lookup"><span data-stu-id="b5a78-110">Browser limitations</span></span>

<span data-ttu-id="b5a78-111">Пользователи, работающие с веб-приложением Teams в неподдерживаемых браузерах, могут столкнуться с приведенными ниже ограничениями.</span><span class="sxs-lookup"><span data-stu-id="b5a78-111">People who use the Teams web app on unsupported browsers will experience the following limitations:</span></span>

- <span data-ttu-id="b5a78-112">Звук доступен только по коммутируемой телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="b5a78-112">Audio is available through a PSTN connection only.</span></span> <span data-ttu-id="b5a78-113">Пользователи не могут использовать свой микрофон.</span><span class="sxs-lookup"><span data-stu-id="b5a78-113">Users can't use their microphone.</span></span>
- <span data-ttu-id="b5a78-114">Пользователи не могут предоставлять доступ к своим камерам и просматривать видео других участников, но могут просматривать предоставленный контент с помощью демонстрации экрана с использованием изображений.</span><span class="sxs-lookup"><span data-stu-id="b5a78-114">Users can't share their camera or see other participants' videos but can view presented content through image-based screen sharing.</span></span>
- <span data-ttu-id="b5a78-115">Пользователи не могут демонстрировать свои экраны, но могут видеть экран, общий доступ к которому предоставлен другим участникам собрания.</span><span class="sxs-lookup"><span data-stu-id="b5a78-115">Users can't share their screen, although they can see a screen that another meeting participant shares.</span></span>
- <span data-ttu-id="b5a78-116">Пользователи не могут получить управление во время сеанса демонстрации экрана.</span><span class="sxs-lookup"><span data-stu-id="b5a78-116">Users can't take control during a screen sharing session.</span></span>
- <span data-ttu-id="b5a78-117">Пользователи не будут получать уведомления о входящих звонках.</span><span class="sxs-lookup"><span data-stu-id="b5a78-117">Users won't receive incoming call notifications.</span></span>
- <span data-ttu-id="b5a78-118">Если Звонок прерван, собрание не будет восстановлено автоматически.</span><span class="sxs-lookup"><span data-stu-id="b5a78-118">If the call is interrupted, the meeting won't automatically reconnect.</span></span>
- <span data-ttu-id="b5a78-119">Пользователи не могут начать собрание.</span><span class="sxs-lookup"><span data-stu-id="b5a78-119">Users can't start meetings.</span></span>

<span data-ttu-id="b5a78-120">Дополнительные сведения о поддержке браузеров в Teams можно найти в разделе [ограничения и спецификации для Teams](/microsoftteams/limits-specifications-teams#browsers).</span><span class="sxs-lookup"><span data-stu-id="b5a78-120">For more information about browser support in Teams, see [Limits and specifications for Teams](/microsoftteams/limits-specifications-teams#browsers).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b5a78-121">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b5a78-121">Related topics</span></span>

- [<span data-ttu-id="b5a78-122">Присоединение к собранию Teams в неподдерживаемом браузере</span><span class="sxs-lookup"><span data-stu-id="b5a78-122">Join a Teams meeting on an unsupported browser</span></span>](https://support.office.com/article/daafdd3c-ac7a-4855-871b-9113bad15907)
