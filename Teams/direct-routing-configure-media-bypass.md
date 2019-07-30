---
title: Настройка обхода сервера-посредника с прямой маршрутизацией
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: article
ms.service: msteams
ms.prod: skype-for-business-itpro
localization_priority: Normal
search.appverid: MET150
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: В этой статье рассказывается, как настроить обход мультимедиа с прямой маршрутизацией телефонной системы.
ms.openlocfilehash: 47b537a9feff22a24b97fa5c54669359992b8a31
ms.sourcegitcommit: a78fee3cad5b58bf41dd014a79f4316cf310c8d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/29/2019
ms.locfileid: "35925475"
---
# <a name="configure-media-bypass-with-direct-routing"></a><span data-ttu-id="a799f-103">Настройка обхода сервера-посредника с прямой маршрутизацией</span><span class="sxs-lookup"><span data-stu-id="a799f-103">Configure media bypass with Direct Routing</span></span>

<span data-ttu-id="a799f-104">Перед настройкой обхода мультимедиа с помощью прямой маршрутизации убедитесь, что у вас есть [план обхода мультимедийных файлов с прямой маршрутизацией](direct-routing-plan-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="a799f-104">Before configuring media bypass with Direct Routing, be sure you have read [Plan for media bypass with Direct Routing](direct-routing-plan-media-bypass.md).</span></span>

<span data-ttu-id="a799f-105">Чтобы включить обход мультимедиа, должны быть выполнены следующие условия:</span><span class="sxs-lookup"><span data-stu-id="a799f-105">To turn on media bypass, the following conditions must be met:</span></span>

1.  <span data-ttu-id="a799f-106">Убедитесь в том, что вендором, используемым для выбора вашего сеанса связи (SBC), поддерживается обход мультимедиа, и инструкции по настройке параметров "пропустить" для SBC.</span><span class="sxs-lookup"><span data-stu-id="a799f-106">Make sure that your Session Border Controller (SBC) vendor of choice supports media bypass and provides instructions on how to configure bypass on the SBC.</span></span> <span data-ttu-id="a799f-107">Ознакомьтесь со статьей "сертификация", чтобы узнать о том, какие из них поддерживают обход мультимедиа, а также о каких-либо инструкциях.</span><span class="sxs-lookup"><span data-stu-id="a799f-107">Please refer to the certification page to learn about SBCs, which ones support media bypass, and for instructions.</span></span>

2.  <span data-ttu-id="a799f-108">Необходимо включить обход мультимедиа на магистральной сети с помощью следующей команды: **Set-ксонлинепстнгатевай-Identity <сбк_фкдн>-медиабипасс $true**.</span><span class="sxs-lookup"><span data-stu-id="a799f-108">You need to turn on media bypass on the trunk using the following command:  **Set-CSOnlinePSTNGateway -Identity <sbc_FQDN> -MediaBypass $true**.</span></span>

3.  <span data-ttu-id="a799f-109">Убедитесь в том, что нужные порты открыты.</span><span class="sxs-lookup"><span data-stu-id="a799f-109">Make sure that the required ports are opened.</span></span> 


## <a name="migrate-from-non-bypassed-trunks-to-bypass-enabled-trunks"></a><span data-ttu-id="a799f-110">Переход с необходных каналов на магистральные и недоступные для обхода</span><span class="sxs-lookup"><span data-stu-id="a799f-110">Migrate from non-bypassed trunks to bypass-enabled trunks</span></span>

<span data-ttu-id="a799f-111">Вы можете переключить всех пользователей за один раз или реализовать поэтапный подход (рекомендуется).</span><span class="sxs-lookup"><span data-stu-id="a799f-111">You can switch all users at once or you can implement a phased approached (recommended).</span></span>

- <span data-ttu-id="a799f-112">**Одновременное переключение всех пользователей.**</span><span class="sxs-lookup"><span data-stu-id="a799f-112">**Switch all users at once.**</span></span> <span data-ttu-id="a799f-113">Если все условия выполнены, вы можете включить режим обхода.</span><span class="sxs-lookup"><span data-stu-id="a799f-113">If all conditions are met, you can turn bypass mode on.</span></span> <span data-ttu-id="a799f-114">Однако все ваши производственные пользователи будут переключаться одновременно.</span><span class="sxs-lookup"><span data-stu-id="a799f-114">However, all your production users will be switched at the same time.</span></span> <span data-ttu-id="a799f-115">Из-за того, что при настройке магистральных каналов и портов могут возникнуть некоторые проблемы, это может повлиять на работу пользователя.</span><span class="sxs-lookup"><span data-stu-id="a799f-115">Because you might experience some issues initially when you configure trunks and ports, your production user experience might be affected.</span></span> 

- <span data-ttu-id="a799f-116">**Поэтапный подход. (Рекомендуемый вариант)**.</span><span class="sxs-lookup"><span data-stu-id="a799f-116">**Phased approach. (Recommended)**.</span></span>  <span data-ttu-id="a799f-117">Создание новой магистрали для одного и того же SBC (с другим портом), проверка и изменение политики голосовой маршрутизации в сети для пользователей, чтобы они указывали на новую магистраль.</span><span class="sxs-lookup"><span data-stu-id="a799f-117">Create a new trunk for the same SBC (with a different port), test it, and change the online voice routing policy for the users to point to the new trunk.</span></span> 

  <span data-ttu-id="a799f-118">Этот подход является рекомендуемым, так как он обеспечивает более плавный переход и бесперебойную работу пользователей.</span><span class="sxs-lookup"><span data-stu-id="a799f-118">This is the recommended approach because it allows for a smoother transition and uninterrupted user experience.</span></span> <span data-ttu-id="a799f-119">Этот подход требует настройки SBC, нового полного доменного имени и конфигурации брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="a799f-119">This approach requires configuration of the SBC, a new FQDN name, and configuration of the firewall.</span></span> <span data-ttu-id="a799f-120">Примечание. необходимо убедиться, что ваш сертификат поддерживает обе магистральные линии.</span><span class="sxs-lookup"><span data-stu-id="a799f-120">Note you will need to make sure that your certificate supports both trunks.</span></span> <span data-ttu-id="a799f-121">В сети SAN необходимо иметь два имени (**sbc1.contoso.com** и **sbc2.contoso.com**) или использовать подстановочный сертификат.</span><span class="sxs-lookup"><span data-stu-id="a799f-121">In SAN, you need to have two names (**sbc1.contoso.com** and **sbc2.contoso.com**) or have a wildcard certificate.</span></span>

![Переход с необходных каналов в магистральы с поддержкой обхода](media/direct-routing-media-bypass-8.png)

<span data-ttu-id="a799f-123">Инструкции по настройке магистральных каналов и выполнению миграции можно найти в документации, предоставленной поставщиком SBC.</span><span class="sxs-lookup"><span data-stu-id="a799f-123">For instructions on how to configure the trunks and perform migration, see the documentation from your SBC vendor:</span></span>

- [<span data-ttu-id="a799f-124">Документация по развертыванию AudioCodes</span><span class="sxs-lookup"><span data-stu-id="a799f-124">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="a799f-125">Документация по развертыванию Oracle</span><span class="sxs-lookup"><span data-stu-id="a799f-125">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="a799f-126">Документация по развертыванию связи с лентой</span><span class="sxs-lookup"><span data-stu-id="a799f-126">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="a799f-127">Документация по развертыванию системы TE (аниноде)</span><span class="sxs-lookup"><span data-stu-id="a799f-127">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="a799f-128">Список контроллеров границ сеансов (SBCs), сертифицированных для прямой маршрутизации, можно найти в разделе [список контроллеров границами сеансов, сертифицированных для прямой маршрутизации](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="a799f-128">For a list of Session Border Controllers (SBCs) certified for Direct Routing, see [List of Session Broder Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>



## <a name="see-also"></a><span data-ttu-id="a799f-129">См. также</span><span class="sxs-lookup"><span data-stu-id="a799f-129">See also</span></span>

[<span data-ttu-id="a799f-130">Планирование обхода мультимедиа с помощью прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="a799f-130">Plan media bypass with Direct Routing</span></span>](direct-routing-plan-media-bypass.md)



