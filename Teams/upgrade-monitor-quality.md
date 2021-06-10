---
title: Качество обслуживания пользователей | Microsoft Teams | QoS | Качество звонка
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: d57f01887961ad0c458b13db20ba79023272bcdf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808999"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="84795-103">Руководство по анализу качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="84795-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="84795-104">![Схема, на диаграмме выделен этап обновления](media/upgrade-banner-op-excellence.png "Этапы пути обновления с акцентом на этапе &quot;Эксплуатация&quot;")</span><span class="sxs-lookup"><span data-stu-id="84795-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="84795-105">Эта статья является частью этапа обновления с Skype для бизнеса до Teams.</span><span class="sxs-lookup"><span data-stu-id="84795-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="84795-106">Улучшение и отслеживание качества звонка</span><span class="sxs-lookup"><span data-stu-id="84795-106">Improve and monitor call quality</span></span>

<span data-ttu-id="84795-107">[Улучшение и](monitor-call-quality-qos.md) отслеживание Teams включает в себя набор действий, которые оценивают и предоставляют рекомендации по исправлению в ключевых областях, которые оказывают наибольшее влияние на улучшение работы пользователей, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="84795-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="84795-108">![Иллюстрация ключевых областей, которые нужно изучить во время проверки.](media/plan-my-service-management-image2.png "Основные области, которые необходимо изучить во время проверки качества интерфейса: качество звука, надежность и результаты опроса.")</span><span class="sxs-lookup"><span data-stu-id="84795-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="84795-109">Постоянная оценка и исправление областей, описанных в руководстве, позволяет снизить риск негативного влияния на пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="84795-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="84795-110">Большинство встречающихся в развертывании проблем с взаимодействием с пользователем можно разделить на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="84795-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="84795-111">Неполная настройка брандмауэра или прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="84795-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="84795-112">Слабый охват сети Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="84795-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="84795-113">Недостаточная пропускная способность</span><span class="sxs-lookup"><span data-stu-id="84795-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="84795-114">VPN;</span><span class="sxs-lookup"><span data-stu-id="84795-114">VPN</span></span>

- <span data-ttu-id="84795-115">Использование неоптимальных или встроенных звуковых устройств</span><span class="sxs-lookup"><span data-stu-id="84795-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="84795-116">Проблемы с подсетями или сетевыми устройствами</span><span class="sxs-lookup"><span data-stu-id="84795-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="84795-117">В руководстве [](monitor-call-quality-qos.md) по улучшению и мониторингу качества звонка для Teams основное внимание уделяется использованию панели мониторинга качества звонка (CQD) Online в качестве основного средства для создания отчетов и изучения каждой описанной области с фокусом на звуке для максимального внедрения и влияния.</span><span class="sxs-lookup"><span data-stu-id="84795-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="84795-118">Любые оптимизации для сети, направленные на улучшение звукового взаимодействия, также вносят вклад в улучшение видеосвязи и совместного доступа к рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="84795-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="84795-119">Настоятельно рекомендуем на ранней стадии назначать защитника качества.</span><span class="sxs-lookup"><span data-stu-id="84795-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="84795-120">После того как они будут назначены, они должны начать знакомьться с содержимым в окно Улучшить и отслеживать качество звонка [для](monitor-call-quality-qos.md)Teams.</span><span class="sxs-lookup"><span data-stu-id="84795-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->
