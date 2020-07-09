---
title: Качество взаимодействия с пользователем | Microsoft Teams | QoS | Качество связи
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Администратор может узнать о задачах и действиях, необходимых для отслеживания качества и использования Microsoft Teams.
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
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="70cff-103">Руководство по анализу качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="70cff-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="70cff-104">![Схема, на которой работает подсветка этап обновления](media/upgrade-banner-op-excellence.png "Этапы путешествия по обновлению, с акцентом на этапе непрерывности работы")</span><span class="sxs-lookup"><span data-stu-id="70cff-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="70cff-105">Эта статья относится к этапу непрерывной работы по обновлению, который начинается сразу же после того, как вы закончите переход с Skype для бизнеса на Teams.</span><span class="sxs-lookup"><span data-stu-id="70cff-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="70cff-106">Улучшение и мониторинг качества связи</span><span class="sxs-lookup"><span data-stu-id="70cff-106">Improve and monitor call quality</span></span>

<span data-ttu-id="70cff-107">[Улучшение и мониторинг качества связи для Teams](monitor-call-quality-qos.md) включает набор действий, которые оценивают и предоставляют руководство по исправлениям в ключевых областях, которые значительно влияют на улучшение взаимодействия с пользователем, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="70cff-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="70cff-108">![Основные области проверки.](media/plan-my-service-management-image2.png "Основные области, которые нужно изучить во время проверки качества: звук, надежность и результаты опроса пользователей.")</span><span class="sxs-lookup"><span data-stu-id="70cff-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="70cff-109">Непрерывно оценивая и исправление области, описанные в руководстве, вы можете уменьшить их потенциал, чтобы негативно повлиять на взаимодействие с пользователем.</span><span class="sxs-lookup"><span data-stu-id="70cff-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="70cff-110">Большинство встречающихся в развертывании проблем с взаимодействием с пользователем можно разделить на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="70cff-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="70cff-111">Неполная настройка брандмауэра или прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="70cff-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="70cff-112">Слабый охват сети Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="70cff-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="70cff-113">Недостаточная пропускная способность</span><span class="sxs-lookup"><span data-stu-id="70cff-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="70cff-114">VPN;</span><span class="sxs-lookup"><span data-stu-id="70cff-114">VPN</span></span>

- <span data-ttu-id="70cff-115">Использование неоптимальных или встроенных звуковых устройств</span><span class="sxs-lookup"><span data-stu-id="70cff-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="70cff-116">Проблемы с подсетями или сетевыми устройствами</span><span class="sxs-lookup"><span data-stu-id="70cff-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="70cff-117">Рекомендации, предоставленные в разделе [повышение качества и контроль за качеством звонков в Teams](monitor-call-quality-qos.md) , сосредоточены на использовании панели мониторинга качества звонков (CQD) в качестве основного средства для создания отчетов и изучения каждой из описанных областей, с фокусом на звуковой канал для максимизации внедрения и воздействия.</span><span class="sxs-lookup"><span data-stu-id="70cff-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="70cff-118">Любые оптимизации для сети, направленные на улучшение звукового взаимодействия, также вносят вклад в улучшение видеосвязи и совместного доступа к рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="70cff-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="70cff-119">Мы настоятельно рекомендуем вам назначить качество лидера на раннем этапе.</span><span class="sxs-lookup"><span data-stu-id="70cff-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="70cff-120">После того как они будут присвоены, они должны начать знакомство с содержимым в [целях улучшения и контроля качества связи для Teams](monitor-call-quality-qos.md).</span><span class="sxs-lookup"><span data-stu-id="70cff-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->
