---
title: Качество работы с пользователем | Microsoft Teams | QoS | Качество звонка
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
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="dc05b-103">Руководство по анализу качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="dc05b-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="dc05b-104">![Схема, на диаграмме выделен этап обновления](media/upgrade-banner-op-excellence.png "Этапы пути обновления с акцентом на этапе "Рабочие связи"")</span><span class="sxs-lookup"><span data-stu-id="dc05b-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="dc05b-105">Эта статья является частью этапа обновления с Skype для бизнеса до Teams.</span><span class="sxs-lookup"><span data-stu-id="dc05b-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="dc05b-106">Улучшение и отслеживание качества звонка</span><span class="sxs-lookup"><span data-stu-id="dc05b-106">Improve and monitor call quality</span></span>

<span data-ttu-id="dc05b-107">[Улучшение и отслеживание](monitor-call-quality-qos.md) качества звонка для Teams включает в себя набор действий по оценке и исправлению в ключевых областях, которые оказывают наибольшее влияние на улучшение пользовательского интерфейса, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="dc05b-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="dc05b-108">![Изображение ключевых областей, которые нужно изучить во время проверки.](media/plan-my-service-management-image2.png "Основные области, которые необходимо изучить во время проверки качества обслуживания: качество звука, надежность и результаты опроса пользователей.")</span><span class="sxs-lookup"><span data-stu-id="dc05b-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="dc05b-109">Постоянная оценка и исправление областей, описанных в руководстве, снижает их вероятность негативного влияния на работу пользователей.</span><span class="sxs-lookup"><span data-stu-id="dc05b-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="dc05b-110">Большинство встречающихся в развертывании проблем с взаимодействием с пользователем можно разделить на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="dc05b-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="dc05b-111">Неполная настройка брандмауэра или прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="dc05b-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="dc05b-112">Слабый охват сети Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="dc05b-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="dc05b-113">Недостаточная пропускная способность</span><span class="sxs-lookup"><span data-stu-id="dc05b-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="dc05b-114">VPN;</span><span class="sxs-lookup"><span data-stu-id="dc05b-114">VPN</span></span>

- <span data-ttu-id="dc05b-115">Использование неоптимальных или встроенных звуковых устройств</span><span class="sxs-lookup"><span data-stu-id="dc05b-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="dc05b-116">Проблемы с подсетями или сетевыми устройствами</span><span class="sxs-lookup"><span data-stu-id="dc05b-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="dc05b-117">В руководстве по улучшению и мониторингу качества звонка в [Teams](monitor-call-quality-qos.md) основное внимание уделяется использованию панели мониторинга качества звонка (CQD) Online в качестве основного средства для создания отчетов и изучения описанных в них области с акцентом на звуковых системах для максимально эффективного внедрения и влияния.</span><span class="sxs-lookup"><span data-stu-id="dc05b-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="dc05b-118">Любые оптимизации для сети, направленные на улучшение звукового взаимодействия, также вносят вклад в улучшение видеосвязи и совместного доступа к рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="dc05b-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="dc05b-119">Настоятельно рекомендуем на ранней стадии поодвинуться на эту стадию.</span><span class="sxs-lookup"><span data-stu-id="dc05b-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="dc05b-120">После того как он будет назначен в качестве кандидата, он должен ознакомиться с содержимым в области "Улучшить качество содержимого" и отслеживать качество [содержимого для Teams.](monitor-call-quality-qos.md)</span><span class="sxs-lookup"><span data-stu-id="dc05b-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->
