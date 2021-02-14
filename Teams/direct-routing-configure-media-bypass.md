---
title: Настройка обхода сервера-посредника с прямой маршрутизацией
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
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
description: Узнайте, как настроить обход мультимедиа с помощью прямой маршрутии телефонной системы для Microsoft Teams, выключив всех пользователей одновременно или реализуя поэтапный подход (рекомендуется).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41e5aae3f91c13653119b04fb88364ce93a4d90c
ms.sourcegitcommit: 1e7bc16969db01317ee482cabf681febae0ef51f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2020
ms.locfileid: "44416899"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="d092a-103">Настройка обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="d092a-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="d092a-104">Перед настройкой обхода мультимедиа с помощью прямой маршрутирования убедитесь, что вы прочитали "План обхода мультимедиа" [при прямой маршрутии.](direct-routing-plan-media-bypass.md)</span><span class="sxs-lookup"><span data-stu-id="d092a-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="d092a-105">Чтобы включить обход мультимедиа, должны быть выполнены следующие условия:</span><span class="sxs-lookup"><span data-stu-id="d092a-105">To turn on media bypass, the following conditions must be met:</span></span>

1.    <span data-ttu-id="d092a-106">Убедитесь, что поставщик граничного контроллера сеанса (SBC) поддерживает обход мультимедиа и предоставляет инструкции по настройке обхода в SBC.</span><span class="sxs-lookup"><span data-stu-id="d092a-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="d092a-107">На странице сертификации вы узнаете о SBCs, которые поддерживают обход мультимедиа, и инструкции.</span><span class="sxs-lookup"><span data-stu-id="d092a-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.    <span data-ttu-id="d092a-108">Необходимо включить обход мультимедиа на линии с помощью следующей команды: **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true.**</span><span class="sxs-lookup"><span data-stu-id="d092a-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.    <span data-ttu-id="d092a-109">Откройте необходимые порты.</span><span class="sxs-lookup"><span data-stu-id="d092a-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="d092a-110">Переход с неисключаемой магистрали на обойденные</span><span class="sxs-lookup"><span data-stu-id="d092a-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="d092a-111">Вы можете переключить всех пользователей одновременно или внедрить поэтапный подход (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="d092a-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="d092a-112">**Одновременное переключение всех пользователей.**</span><span class="sxs-lookup"><span data-stu-id="d092a-112">**Switch all users at once.**</span></span> <span data-ttu-id="d092a-113">Если все условия выполнены, можно включить режим обхода.</span><span class="sxs-lookup"><span data-stu-id="d092a-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="d092a-114">Однако все производственные пользователи будут одновременно переключения.</span><span class="sxs-lookup"><span data-stu-id="d092a-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="d092a-115">Поскольку первоначально при настройке магистральных и портов могут возникнуть некоторые проблемы, это может повлиять на пользовательский процесс в вашей компании.</span><span class="sxs-lookup"><span data-stu-id="d092a-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="d092a-116">**Поэтапный подход. (Рекомендуется).**</span><span class="sxs-lookup"><span data-stu-id="d092a-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="d092a-117">Создайте новую магистраль для того же SBC (с другим портом), протестйте ее и измените политику маршрутинга голосовой связи в Сети, чтобы пользователи навести указатель на новую.</span><span class="sxs-lookup"><span data-stu-id="d092a-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="d092a-118">Это рекомендуемый подход, так как он обеспечивает более плавный переход и непрерывный пользовательский интерфейс.</span><span class="sxs-lookup"><span data-stu-id="d092a-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="d092a-119">Для этого подхода требуется конфигурация SBC, новое имя FQDN и конфигурация брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="d092a-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="d092a-120">Обратите внимание, что ваш сертификат должен поддерживать обе службы.</span><span class="sxs-lookup"><span data-stu-id="d092a-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="d092a-121">В САН у вас должны быть два имена **(sbc1.contoso.com** и **sbc2.contoso.com)** или поддиавный сертификат.</span><span class="sxs-lookup"><span data-stu-id="d092a-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Переход с без обхода на обойденные и неинтегрирующие](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="d092a-123">Инструкции по настройке и переносу см. в документации поставщика SBC:</span><span class="sxs-lookup"><span data-stu-id="d092a-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="d092a-124">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="d092a-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="d092a-125">Документация по развертыванию Oracle</span><span class="sxs-lookup"><span data-stu-id="d092a-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="d092a-126">Документация по развертыванию информационного сообщения на ленте</span><span class="sxs-lookup"><span data-stu-id="d092a-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="d092a-127">Документация по развертыванию TE-Systems (anynode)</span><span class="sxs-lookup"><span data-stu-id="d092a-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="d092a-128">Список граничных геймпадов сеансов, сертифицированных для прямой маршрутики, см. в списке контроллеров [Broder Session Broder,](direct-routing-border-controllers.md)сертифицированных для прямой маршрутики.</span><span class="sxs-lookup"><span data-stu-id="d092a-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="related-topics"></a><span data-ttu-id="d092a-129">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d092a-129">Related topics</span></span>

[<span data-ttu-id="d092a-130">Обход мультимедиа с прямой маршрутией</span><span class="sxs-lookup"><span data-stu-id="d092a-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



