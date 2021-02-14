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
description: Узнайте, как настроить прямую маршрутику microsoft Phone System для подключения локальной инфраструктуры телефонии к Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5388c93e741323d3dc9eda0fc51968b8b344d2cb
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701297"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="53273-103">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="53273-103">Configure Direct Routing</span></span>

<span data-ttu-id="53273-104">Прямая маршрутия в телефонной системе Майкрософт позволяет подключить к Microsoft Teams свою локальное инфраструктуру телефонии.</span><span class="sxs-lookup"><span data-stu-id="53273-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="53273-105">В этой статье перечислены высокоуровневые действия, необходимые для подключения поддерживаемого локального граничного контроллера сеанса (SBC) к прямой маршрутике, а также настройка использования прямой маршрутии пользователями Teams для подключения к телефонной сети общего пользования (STN).</span><span class="sxs-lookup"><span data-stu-id="53273-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="53273-106">Эта статья ссылок на статьи со ссылками на подробные сведения.</span><span class="sxs-lookup"><span data-stu-id="53273-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="53273-107">Сведения о том, является ли прямая маршрутизации правильным решением для вашей организации, см. в подсистеме телефонной [системы.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="53273-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="53273-108">Сведения о необходимых предварительных условиях и планировании развертывания см. в [подмносях "Прямая маршрутия по плану".](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="53273-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="53273-109">Вы также можете посмотреть этот сеанс, чтобы узнать о преимуществах прямой маршрутинга, планировании и развертывании: [Direct Routing в Microsoft Teams.](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="53273-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="53273-110">Для выполнения действий, которые объясняются в этой статье, администраторам необходимо ознакомиться с помощью cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="53273-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="53273-111">Дополнительные сведения об использовании PowerShell см. в [Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="53273-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="53273-112">Прежде чем выполнять действия, указанные в этих статьях, корпорация Майкрософт рекомендует подтвердить, что ваш поставщик SBC уже настроил SBC:</span><span class="sxs-lookup"><span data-stu-id="53273-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="53273-113">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="53273-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="53273-114">Документация по развертыванию Oracle</span><span class="sxs-lookup"><span data-stu-id="53273-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="53273-115">Документация по развертыванию информационного сообщения на ленте</span><span class="sxs-lookup"><span data-stu-id="53273-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="53273-116">Документация по развертыванию TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="53273-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="53273-117">Документация по развертыванию Metasw deployment</span><span class="sxs-lookup"><span data-stu-id="53273-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="53273-118">Полный список поддерживаемых SBCs см. в списке граничных контроллеров сеанса, сертифицированных для [прямой маршрутики.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="53273-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="53273-119">Чтобы настроить телефонную систему Майкрософт и позволить пользователям использовать прямую маршрутику, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="53273-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="53273-120">**Шаг 1.**</span><span class="sxs-lookup"><span data-stu-id="53273-120">**Step 1.**</span></span> [<span data-ttu-id="53273-121">Подключение SBC к телефонной системе Майкрософт и проверка подключения</span><span class="sxs-lookup"><span data-stu-id="53273-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="53273-122">**Шаг 2.**</span><span class="sxs-lookup"><span data-stu-id="53273-122">**Step 2.**</span></span> [<span data-ttu-id="53273-123">Включить для пользователей прямую маршрутику, голосовую и голосовую почту</span><span class="sxs-lookup"><span data-stu-id="53273-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="53273-124">**Шаг 3.**</span><span class="sxs-lookup"><span data-stu-id="53273-124">**Step 3.**</span></span> [<span data-ttu-id="53273-125">Настройка голосовой маршрутии</span><span class="sxs-lookup"><span data-stu-id="53273-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="53273-126">**Шаг 4.**</span><span class="sxs-lookup"><span data-stu-id="53273-126">**Step 4.**</span></span> [<span data-ttu-id="53273-127">Перевод чисел в альтернативный формат</span><span class="sxs-lookup"><span data-stu-id="53273-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="53273-128">Если вы настраивает SBC для нескольких клиентов, также необходимо прочитать статью "Настройка [SBC для нескольких клиентов".](direct-routing-sbc-multiple-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="53273-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="53273-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="53273-129">Related topics</span></span>

[<span data-ttu-id="53273-130">Прямая маршрутизация телефонной системы</span><span class="sxs-lookup"><span data-stu-id="53273-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="53273-131">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="53273-131">Plan Direct Routing</span></span>](direct-routing-plan.md)

