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
ms.openlocfilehash: 25b356d171ee8c1a66de2f69b0b0525c24220755
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2020
ms.locfileid: "44522562"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="29518-103">Руководство по анализу качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="29518-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="29518-104">![Схема, на которой работает подсветка этап обновления](media/upgrade-banner-op-excellence.png "Этапы путешествия по обновлению, с акцентом на этапе непрерывности работы")</span><span class="sxs-lookup"><span data-stu-id="29518-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="29518-105">Эта статья относится к этапу непрерывной работы по обновлению, который начинается сразу же после того, как вы закончите переход с Skype для бизнеса на Teams.</span><span class="sxs-lookup"><span data-stu-id="29518-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

<span data-ttu-id="29518-106">[Руководство по пересмотру опыта работы](https://aka.ms/qerguide) включает набор действий, которые оценивают и предоставляют руководство по исправлению в ключевых областях, которые значительно влияют на улучшение взаимодействия с пользователем, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="29518-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="29518-107">![Основные области проверки.](media/plan-my-service-management-image2.png "Основные области, которые нужно изучить во время проверки качества: звук, надежность и результаты опроса пользователей.")</span><span class="sxs-lookup"><span data-stu-id="29518-107">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="29518-108">Непрерывно оценивая и исправление области, описанные в руководстве, вы можете уменьшить их потенциал, чтобы негативно повлиять на взаимодействие с пользователем.</span><span class="sxs-lookup"><span data-stu-id="29518-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="29518-109">Большинство встречающихся в развертывании проблем с взаимодействием с пользователем можно разделить на следующие категории:</span><span class="sxs-lookup"><span data-stu-id="29518-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="29518-110">Неполная настройка брандмауэра или прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="29518-110">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="29518-111">Слабый охват сети Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="29518-111">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="29518-112">Недостаточная пропускная способность</span><span class="sxs-lookup"><span data-stu-id="29518-112">Insufficient bandwidth</span></span>

- <span data-ttu-id="29518-113">VPN;</span><span class="sxs-lookup"><span data-stu-id="29518-113">VPN</span></span>

- <span data-ttu-id="29518-114">Использование неоптимальных или встроенных звуковых устройств</span><span class="sxs-lookup"><span data-stu-id="29518-114">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="29518-115">Проблемы с подсетями или сетевыми устройствами</span><span class="sxs-lookup"><span data-stu-id="29518-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="29518-116">Рекомендации, предоставленные в руководстве по расширению качества работы, задаются с помощью панели мониторинга качества звонков (CQD) в качестве основного средства для создания отчетов и изучения каждой из описанных областей с фокусом на звуковой канал для максимизации внедрения и воздействия.</span><span class="sxs-lookup"><span data-stu-id="29518-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="29518-117">Любые оптимизации для сети, направленные на улучшение звукового взаимодействия, также вносят вклад в улучшение видеосвязи и совместного доступа к рабочему столу.</span><span class="sxs-lookup"><span data-stu-id="29518-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="29518-118">Мы настоятельно рекомендуем вам назначить качество лидера на раннем этапе.</span><span class="sxs-lookup"><span data-stu-id="29518-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="29518-119">После того как они будут присвоены, они должны начать знакомство с содержимым в [руководстве по обзору качества работы](https://aka.ms/qerguide).</span><span class="sxs-lookup"><span data-stu-id="29518-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->
