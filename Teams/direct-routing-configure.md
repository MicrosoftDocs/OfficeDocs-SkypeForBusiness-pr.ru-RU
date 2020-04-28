---
title: Настройка прямой маршрутизации
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: В этой статье объясняется, как настроить прямую маршрутизацию Microsoft Phone System для подключения локальной инфраструктуры телефонной связи с Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f12eb67fd63a3d1bbed3ddcd0c4fadce16529083
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904831"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="8917d-103">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="8917d-103">Configure Direct Routing</span></span>

<span data-ttu-id="8917d-104">Прямая маршрутизация Microsoft Phone System позволяет подключать локальную инфраструктуру телефонной связи с Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8917d-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="8917d-105">В этой статье перечислены общие действия, которые необходимо выполнить, чтобы подключить поддерживаемый локальный контроллер рабочего места (SBC) для прямой маршрутизации и настроить пользователей Teams прямо на использование прямой маршрутизации для подключения к коммутируемой телефонной сети с открытым коммутируемым подключением (КТСОП).</span><span class="sxs-lookup"><span data-stu-id="8917d-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="8917d-106">В этой статье приведены ссылки на статьи с подробными сведениями о ней.</span><span class="sxs-lookup"><span data-stu-id="8917d-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="8917d-107">Сведения о том, является ли прямая маршрутизация подходящего решения для вашей организации, можно найти в разделе [Прямая маршрутизация телефонной системы](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="8917d-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="8917d-108">Сведения о предварительных требованиях и планировании развертывания можно найти в разделе [Планирование прямого маршрутизации](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="8917d-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="8917d-109">Вы также можете узнать о преимуществах прямой маршрутизации, о том, как ее планировать и развертывать в следующем сеансе: [Прямая маршрутизация в Microsoft Teams](https://aka.ms/teams-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="8917d-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="8917d-110">Чтобы выполнить шаги, описанные в этой статье, администраторы должны ознакомиться с командлетами PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8917d-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="8917d-111">Дополнительные сведения об использовании PowerShell можно найти в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="8917d-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="8917d-112">Перед выполнением действий, описанных в этой статье, корпорация Microsoft рекомендует подтвердить, что ваш SBC уже настроен в соответствии с рекомендациями вашего поставщика SBC.</span><span class="sxs-lookup"><span data-stu-id="8917d-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="8917d-113">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="8917d-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="8917d-114">Документация по развертыванию Oracle</span><span class="sxs-lookup"><span data-stu-id="8917d-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="8917d-115">Документация по развертыванию связи с лентой</span><span class="sxs-lookup"><span data-stu-id="8917d-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="8917d-116">Документация по развертыванию системы TE (anynode)</span><span class="sxs-lookup"><span data-stu-id="8917d-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="8917d-117">Документация по развертыванию Metaswitch</span><span class="sxs-lookup"><span data-stu-id="8917d-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="8917d-118">Полный список поддерживаемых SBCs можно найти в разделе [список контроллеров границ сеансов, сертифицированных для прямого маршрутизации](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="8917d-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="8917d-119">Чтобы настроить телефонную систему Microsoft и разрешить пользователям использовать прямую маршрутизацию, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8917d-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="8917d-120">**Шаг 1.**</span><span class="sxs-lookup"><span data-stu-id="8917d-120">**Step 1.**</span></span> [<span data-ttu-id="8917d-121">Соединение SBC с телефонной системой Microsoft и проверка соединения</span><span class="sxs-lookup"><span data-stu-id="8917d-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="8917d-122">**Шаг 2.**</span><span class="sxs-lookup"><span data-stu-id="8917d-122">**Step 2.**</span></span> [<span data-ttu-id="8917d-123">Предоставление пользователям прямой маршрутизации, голоса и голосовой почты</span><span class="sxs-lookup"><span data-stu-id="8917d-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="8917d-124">**Шаг 3.**</span><span class="sxs-lookup"><span data-stu-id="8917d-124">**Step 3.**</span></span> [<span data-ttu-id="8917d-125">Настройка голосовой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="8917d-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="8917d-126">**Шаг 4.**</span><span class="sxs-lookup"><span data-stu-id="8917d-126">**Step 4.**</span></span> [<span data-ttu-id="8917d-127">Перевод чисел в альтернативный формат</span><span class="sxs-lookup"><span data-stu-id="8917d-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="8917d-128">Если вы настраиваете SBC для нескольких клиентов, вы также захотите прочитать [настройку SBC для нескольких клиентов](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="8917d-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="8917d-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8917d-129">Related topics</span></span>

[<span data-ttu-id="8917d-130">Прямая маршрутизация телефонной системы</span><span class="sxs-lookup"><span data-stu-id="8917d-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="8917d-131">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="8917d-131">Plan Direct Routing</span></span>](direct-routing-plan.md)

