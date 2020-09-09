---
title: Настройка Ringback Bot для прямой маршрутизации
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: В этой статье объясняется, как использовать Ringback Bot для прямой маршрутизации, чтобы предотвратить неожиданные тишины, которые могут возникать при установке звонка.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: ec1500d9e7d5896d1b4cd2414355602d7400591a
ms.sourcegitcommit: 207c58563b7b2aba274b067cf64242abd7a33c2c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405786"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="eb7bd-103">Настройка Ringback Bot для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="eb7bd-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="eb7bd-104">В этой статье описывается программа Ringback Bot, с помощью которой можно избежать неожиданного замыкания, которое может возникнуть, если для установки звонков требуется больше времени.</span><span class="sxs-lookup"><span data-stu-id="eb7bd-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="eb7bd-105">Ringback Bot доступен для прямой маршрутизации в режиме обхода файлов, не являющихся мультимедийными.</span><span class="sxs-lookup"><span data-stu-id="eb7bd-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="eb7bd-106">Иногда входящие звонки из телефонной сети общего пользования (КТСОП) для клиентов Teams могут занять больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="eb7bd-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="eb7bd-107">Это может быть вызвано различными причинами.</span><span class="sxs-lookup"><span data-stu-id="eb7bd-107">This can occur for various reasons.</span></span> <span data-ttu-id="eb7bd-108">В этом случае абонент может не слышать ничего, так как клиент Teams не позвонит, и звонок может быть прерван некоторыми поставщиками телекоммуникационных услуг.</span><span class="sxs-lookup"><span data-stu-id="eb7bd-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and the call might be canceled by some telecommunications providers.</span></span>

<span data-ttu-id="eb7bd-109">Ringback Bot помогает избежать неожиданного тишины, которое может возникнуть в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="eb7bd-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="eb7bd-110">Для входящих звонков от КТСОП к клиентам Teams в Ringback Bot воспроизводится Специальный звуковой сигнал для вызывающего абонента, указывающий на то, что команды находятся в процессе установки звонка.</span><span class="sxs-lookup"><span data-stu-id="eb7bd-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="eb7bd-111">Ringback Bot создает ранний носитель из серверной части Teams.</span><span class="sxs-lookup"><span data-stu-id="eb7bd-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="eb7bd-112">В некоторых странах и регионах вам может взиматься плата за звонок, когда вы начнете перетекание материала.</span><span class="sxs-lookup"><span data-stu-id="eb7bd-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="eb7bd-113">Настройка Ringback Bot</span><span class="sxs-lookup"><span data-stu-id="eb7bd-113">Configure the Ringback bot</span></span>

<span data-ttu-id="eb7bd-114">Используйте командлеты [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) и [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) вместе с параметром **GenerateRingingWhileLocatingUser** , чтобы настроить робот Ringback.</span><span class="sxs-lookup"><span data-stu-id="eb7bd-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) and [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlets together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot.</span></span>

<span data-ttu-id="eb7bd-115">Чтобы включить Ringback Bot, задайте для параметра **GenerateRingingWhileLocatingUser** значение " **$true**".</span><span class="sxs-lookup"><span data-stu-id="eb7bd-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="eb7bd-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="eb7bd-116">This is the default value.</span></span> 

<span data-ttu-id="eb7bd-117">Чтобы отключить Ringback Bot, задайте для параметра **GenerateRingingWhileLocatingUser** значение " **$false**".</span><span class="sxs-lookup"><span data-stu-id="eb7bd-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="eb7bd-118">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="eb7bd-118">Related topics</span></span>

- [<span data-ttu-id="eb7bd-119">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="eb7bd-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
