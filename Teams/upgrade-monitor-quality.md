---
title: Качество взаимодействия руководство по решению для-группами Майкрософт
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Задачи и действия, необходимые для отслеживания качества и использования групп Microsoft
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6049dc1a3bbaf29b9f6b678731e2bf3d3b73b7b4
ms.sourcegitcommit: a20a9a7d0797e3e01afa1cf13957f10dad61cdf4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2018
ms.locfileid: "20398023"
---
<span data-ttu-id="130d3-103">![Этапы обновления пути с акцентом на стадии высокий уровень работоспособности] (media/upgrade-banner-op-excellence.png "Этапы обновления пути с акцентом на стадии высокий уровень работоспособности")</span><span class="sxs-lookup"><span data-stu-id="130d3-103">![Stages of the upgrade journey, with emphasis on the Operational Excellence stage](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="130d3-104">В этой статье является частью высокий уровень этапа поездке обновления, который начинается сразу после выполнения обновления Скайп для бизнеса в группы.</span><span class="sxs-lookup"><span data-stu-id="130d3-104">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="130d3-105">Качество взаимодействия руководство по решению</span><span class="sxs-lookup"><span data-stu-id="130d3-105">Quality of Experience Review Guide</span></span>

<span data-ttu-id="130d3-106">[Качество из взаимодействия руководство по решению](https://aka.ms/qerguide) включают набор действий, которые оценки и даются рекомендации по исправлению в ключевых областях, которые имеют наибольшее влияние на улучшение взаимодействия с пользователем, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="130d3-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="130d3-107">![Ключевые области для проверки во время проверки качества Quality of: аудио-, надежности и результатах опроса пользователя.] (media/plan-my-service-management-image2.png "Ключевые области для проверки во время проверки качества Quality of: аудио-, надежности и результатах опроса пользователя.")</span><span class="sxs-lookup"><span data-stu-id="130d3-107">![The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="130d3-108">Постоянно вызов и устранению области, описанные в руководстве по, позволит сократить их потенциально может отрицательно сказаться на взаимодействие с пользователем.</span><span class="sxs-lookup"><span data-stu-id="130d3-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="130d3-109">Большинство взаимодействие с пользователем проблем, возникающих при развертывании, можно разбить на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="130d3-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

-   <span data-ttu-id="130d3-110">Неполный конфигурации брандмауэр или прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="130d3-110">Incomplete firewall or proxy configuration</span></span>

-   <span data-ttu-id="130d3-111">Низкий покрытия Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="130d3-111">Poor Wi-Fi coverage</span></span>

-   <span data-ttu-id="130d3-112">Недостаточно пропускной способности</span><span class="sxs-lookup"><span data-stu-id="130d3-112">Insufficient bandwidth</span></span>

-   <span data-ttu-id="130d3-113">VPN</span><span class="sxs-lookup"><span data-stu-id="130d3-113">VPN</span></span>

-   <span data-ttu-id="130d3-114">Использование неоптимизированном или встроенных звуковых устройств</span><span class="sxs-lookup"><span data-stu-id="130d3-114">Use of unoptimized or built-in audio devices</span></span>

-   <span data-ttu-id="130d3-115">Инспектором подсетей и сетевых устройств</span><span class="sxs-lookup"><span data-stu-id="130d3-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="130d3-116">В центре внимания использование Online вызова панели мониторинга качества (CQD) в качестве основного средства для регистрации и исследовать каждой области, описанного с фокусом на аудио для обеспечения максимальной воздействия и внедрения рекомендациями, изложенными в Quality of качества руководство по решению.</span><span class="sxs-lookup"><span data-stu-id="130d3-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="130d3-117">Оптимизация внесенные в сети для улучшения качества звука также непосредственно преобразует для улучшения в общий доступ к рабочему столу и видео.</span><span class="sxs-lookup"><span data-stu-id="130d3-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="130d3-118">Мы настоятельно рекомендуем на раннем этапе используют известный качества.</span><span class="sxs-lookup"><span data-stu-id="130d3-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="130d3-119">После назначить им следует запустить ознакомиться с содержимым в [Quality of качества руководство по решению](https://aka.ms/qerguide).</span><span class="sxs-lookup"><span data-stu-id="130d3-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->