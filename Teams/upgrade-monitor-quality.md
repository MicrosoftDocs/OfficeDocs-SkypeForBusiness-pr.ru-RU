---
title: Качество работы с пользователем | Microsoft Teams | QoS | Качество звонка
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Администратор может узнать о задачах и действиях, необходимых для мониторинга качества и использования Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 843acff0dafc7cd5ad2b3fd63ccc009c64716b03
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085925"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="74e5f-103">Руководство по анализу качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="74e5f-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="74e5f-104">![Схема, на диаграмме выделен этап обновления](media/upgrade-banner-op-excellence.png "Этапы пути обновления с акцентом на этапе "Рабочие связи"")</span><span class="sxs-lookup"><span data-stu-id="74e5f-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="74e5f-105">Эта статья является частью этапа обновления с Skype для бизнеса до Teams.</span><span class="sxs-lookup"><span data-stu-id="74e5f-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="74e5f-106">Улучшение качества звонка и его отслеживание</span><span class="sxs-lookup"><span data-stu-id="74e5f-106">Improve and monitor call quality</span></span>

<span data-ttu-id="74e5f-107">[Улучшение и отслеживание](monitor-call-quality-qos.md) качества звонка для Teams включает в себя набор действий по оценке и исправлению в ключевых областях, которые оказывают наибольшее влияние на улучшение пользовательского интерфейса, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="74e5f-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="74e5f-108">![Изображение ключевых областей, которые нужно изучить во время проверки.](media/plan-my-service-management-image2.png "Основные области, которые необходимо изучить во время проверки качества интерфейса: качество звука, надежность и результаты опроса пользователей.")</span><span class="sxs-lookup"><span data-stu-id="74e5f-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="74e5f-109">Постоянная оценка и исправление областей, описанных в руководстве, позволяет снизить риск негативного влияния на работу пользователей.</span><span class="sxs-lookup"><span data-stu-id="74e5f-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="74e5f-110">Большинство встречающихся в развертывании проблем с взаимодействием с пользователем можно разделить на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="74e5f-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="74e5f-111">Неполная настройка брандмауэра или прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="74e5f-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="74e5f-112">Слабый охват сети Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="74e5f-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="74e5f-113">Недостаточная пропускная способность</span><span class="sxs-lookup"><span data-stu-id="74e5f-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="74e5f-114">VPN;</span><span class="sxs-lookup"><span data-stu-id="74e5f-114">VPN</span></span>

- <span data-ttu-id="74e5f-115">Использование неоптимальных или встроенных звуковых устройств</span><span class="sxs-lookup"><span data-stu-id="74e5f-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="74e5f-116">Проблемы с подсетями или сетевыми устройствами</span><span class="sxs-lookup"><span data-stu-id="74e5f-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="74e5f-117">В руководстве по улучшению и мониторингу качества вызовов в [Teams](monitor-call-quality-qos.md) основное внимание уделяется использованию панели мониторинга качества звонка (CQD) Online в качестве основного средства для создания отчетов и изучения описанных в них области с акцентом на звуке для максимального внедрения и влияния.</span><span class="sxs-lookup"><span data-stu-id="74e5f-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="74e5f-118">Любые оптимизации для сети, направленные на улучшение звукового взаимодействия, также вносят вклад в улучшение видеосвязи и совместного доступа к рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="74e5f-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="74e5f-119">Настоятельно рекомендуем заранее выдвигать в качестве защитника нужное время.</span><span class="sxs-lookup"><span data-stu-id="74e5f-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="74e5f-120">После того как они будут назначены, они должны приступить к ознакомлению с содержимым в улучшение и отслеживание качества [содержимого для Teams.](monitor-call-quality-qos.md)</span><span class="sxs-lookup"><span data-stu-id="74e5f-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->
