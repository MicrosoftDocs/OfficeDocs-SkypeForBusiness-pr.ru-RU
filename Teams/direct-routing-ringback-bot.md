---
title: Настройка Рингбакк Bot для прямой маршрутизации
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: В этой статье объясняется, как использовать Рингбакк Bot для прямой маршрутизации, чтобы предотвратить неожиданные тишины, которые могут возникать при установке звонка.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2a9ee3f227faa736d7fdda3ebedc755c8ac5049d
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41834999"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="c5c42-103">Настройка Рингбакк Bot для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="c5c42-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="c5c42-104">В этой статье описывается программа Рингбакк Bot, с помощью которой можно избежать неожиданного замыкания, которое может возникнуть, если для установки звонков требуется больше времени.</span><span class="sxs-lookup"><span data-stu-id="c5c42-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="c5c42-105">Рингбакк Bot доступен для прямой маршрутизации в режиме обхода файлов, не являющихся мультимедийными.</span><span class="sxs-lookup"><span data-stu-id="c5c42-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="c5c42-106">Иногда входящие звонки из телефонной сети общего пользования (КТСОП) для клиентов Teams могут занять больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="c5c42-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="c5c42-107">Это может быть вызвано различными причинами.</span><span class="sxs-lookup"><span data-stu-id="c5c42-107">This can occur for various reasons.</span></span> <span data-ttu-id="c5c42-108">В этом случае абонент может не слышать ничего, так как клиент Teams не позвонит, и звонок может быть прерван некоторыми поставщиками телекоммуникационных услуг.</span><span class="sxs-lookup"><span data-stu-id="c5c42-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and the call might be canceled by some telecommunications providers.</span></span>

<span data-ttu-id="c5c42-109">Рингбакк Bot помогает избежать неожиданного тишины, которое может возникнуть в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="c5c42-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="c5c42-110">Для входящих звонков от КТСОП к клиентам Teams в Рингбакк Bot воспроизводится Специальный звуковой сигнал для вызывающего абонента, указывающий на то, что команды находятся в процессе установки звонка.</span><span class="sxs-lookup"><span data-stu-id="c5c42-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="c5c42-111">Рингбакк Bot создает ранний носитель из серверной части Teams.</span><span class="sxs-lookup"><span data-stu-id="c5c42-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="c5c42-112">В некоторых странах и регионах вам может взиматься плата за звонок, когда вы начнете перетекание материала.</span><span class="sxs-lookup"><span data-stu-id="c5c42-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="c5c42-113">Настройка Рингбакк Bot</span><span class="sxs-lookup"><span data-stu-id="c5c42-113">Configure the Ringback bot</span></span>

<span data-ttu-id="c5c42-114">Используйте командлеты [Set-ксонлинегатевай](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) и [New-ксонлинепстнгатевай](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) вместе с параметром **Женератерингингвхилелокатингусер** , чтобы настроить робот рингбакк.</span><span class="sxs-lookup"><span data-stu-id="c5c42-114">Use the [Set-CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) and [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlets together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot.</span></span>

<span data-ttu-id="c5c42-115">Чтобы включить Рингбакк Bot, задайте для параметра **женератерингингвхилелокатингусер** значение " **$true**".</span><span class="sxs-lookup"><span data-stu-id="c5c42-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="c5c42-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c5c42-116">This is the default value.</span></span> 

<span data-ttu-id="c5c42-117">Чтобы отключить Рингбакк Bot, задайте для параметра **женератерингингвхилелокатингусер** значение " **$false**".</span><span class="sxs-lookup"><span data-stu-id="c5c42-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="c5c42-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c5c42-118">Related topics</span></span>

- [<span data-ttu-id="c5c42-119">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="c5c42-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)