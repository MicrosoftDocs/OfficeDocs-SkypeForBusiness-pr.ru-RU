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
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Узнайте, как настроить Телефон (Майкрософт) маршрутику System Direct Routing для подключения к локальной инфраструктуре телефонии Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ecd8579ccd092e6b82deb06aa670901cdfc3b023
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122243"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="1e3a8-103">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="1e3a8-103">Configure Direct Routing</span></span>

<span data-ttu-id="1e3a8-104">Телефон (Майкрософт) С помощью system Direct Routing вы можете подключить к своей локальной инфраструктуре телефонии Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1e3a8-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="1e3a8-105">В этой статье перечислены шаги высокого уровня, необходимые для подключения поддерживаемого локального пограничного контроллера сеанса (SBC) к прямой маршрутике, а также как настроить для пользователей Teams использование прямой маршрутии для подключения к телефонной сети общего пользования (STN).</span><span class="sxs-lookup"><span data-stu-id="1e3a8-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="1e3a8-106">Подробные сведения в этой статье можно найти в связанных статьях.</span><span class="sxs-lookup"><span data-stu-id="1e3a8-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="1e3a8-107">Сведения о том, является ли direct Routing правильным решением для вашей организации, см. в телефонная система [Direct Routing](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="1e3a8-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="1e3a8-108">Сведения о предварительных условия и планировании развертывания см. в этой [ссылке.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="1e3a8-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="1e3a8-109">Вы также можете посмотреть следующий сеанс, чтобы узнать о преимуществах прямой маршрутии, планировании и развертывании: Прямая маршрутная маршрутия [в](https://aka.ms/teams-direct-routing)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1e3a8-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="1e3a8-110">Для выполнения действий, которые объясняются в этой статье, администраторам требуется некоторое знакомство с помощью powerShell-выполнения.</span><span class="sxs-lookup"><span data-stu-id="1e3a8-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="1e3a8-111">Дополнительные сведения об использовании PowerShell см. в этой [Windows PowerShell.](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="1e3a8-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="1e3a8-112">Прежде чем выполнять действия, указанные в этих статьях, корпорация Майкрософт рекомендует подтвердить, что ваш поставщик SBC уже настроил SBC:</span><span class="sxs-lookup"><span data-stu-id="1e3a8-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="1e3a8-113">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="1e3a8-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="1e3a8-114">Документация по развертыванию Oracle</span><span class="sxs-lookup"><span data-stu-id="1e3a8-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="1e3a8-115">Документация по развертыванию коммуникаций на ленте</span><span class="sxs-lookup"><span data-stu-id="1e3a8-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="1e3a8-116">Документация по развертыванию TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="1e3a8-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="1e3a8-117">Документация по развертыванию Metaswitch</span><span class="sxs-lookup"><span data-stu-id="1e3a8-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="1e3a8-118">Полный список поддерживаемых SBCs см. в списке контроллеров границ сеанса, сертифицированных для [прямой маршрутики.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="1e3a8-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="1e3a8-119">Чтобы настроить Телефон (Майкрософт) и позволить пользователям использовать прямую маршрутику, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="1e3a8-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="1e3a8-120">**Шаг 1.**</span><span class="sxs-lookup"><span data-stu-id="1e3a8-120">**Step 1.**</span></span> [<span data-ttu-id="1e3a8-121">Подключение SBC с Телефон (Майкрософт) и проверьте подключение</span><span class="sxs-lookup"><span data-stu-id="1e3a8-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="1e3a8-122">**Шаг 2.**</span><span class="sxs-lookup"><span data-stu-id="1e3a8-122">**Step 2.**</span></span> [<span data-ttu-id="1e3a8-123">Включить для пользователей прямую маршрутику, голосовую и голосовую почту</span><span class="sxs-lookup"><span data-stu-id="1e3a8-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="1e3a8-124">**Шаг 3.**</span><span class="sxs-lookup"><span data-stu-id="1e3a8-124">**Step 3.**</span></span> [<span data-ttu-id="1e3a8-125">Настройка перенастройки голосовой маршрутии</span><span class="sxs-lookup"><span data-stu-id="1e3a8-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="1e3a8-126">**Шаг 4.**</span><span class="sxs-lookup"><span data-stu-id="1e3a8-126">**Step 4.**</span></span> [<span data-ttu-id="1e3a8-127">Перевод чисел в альтернативный формат</span><span class="sxs-lookup"><span data-stu-id="1e3a8-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="1e3a8-128">Если вы настраивает SBC для нескольких клиентов, также необходимо прочитать статью Настройка [SBC для нескольких клиентов.](direct-routing-sbc-multiple-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="1e3a8-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="1e3a8-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="1e3a8-129">Related topics</span></span>

[<span data-ttu-id="1e3a8-130">Прямая маршрутизация телефонной системы</span><span class="sxs-lookup"><span data-stu-id="1e3a8-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="1e3a8-131">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="1e3a8-131">Plan Direct Routing</span></span>](direct-routing-plan.md)