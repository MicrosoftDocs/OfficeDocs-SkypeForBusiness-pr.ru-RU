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
ms.openlocfilehash: 26738002ab333d2490ef0dac5674a1f7cdc19efd
ms.sourcegitcommit: 8974cd7a693bc879fed8222f551fd7ce3205dd65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420959"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="0723c-103">Настройка Ringback Bot для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="0723c-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="0723c-104">В этой статье описывается программа Ringback Bot, с помощью которой можно избежать неожиданного замыкания, которое может возникнуть, если для установки звонков требуется больше времени.</span><span class="sxs-lookup"><span data-stu-id="0723c-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="0723c-105">Ringback Bot доступен для прямой маршрутизации в режиме обхода файлов, не являющихся мультимедийными.</span><span class="sxs-lookup"><span data-stu-id="0723c-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="0723c-106">Иногда входящие звонки из телефонной сети общего пользования (КТСОП) для клиентов Teams могут занять больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="0723c-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="0723c-107">Это может быть вызвано различными причинами.</span><span class="sxs-lookup"><span data-stu-id="0723c-107">This can occur for various reasons.</span></span> <span data-ttu-id="0723c-108">В этом случае абонент может не слышать ничего, так как клиент Teams не позвонит, а некоторые поставщики телекоммуникационных услуг могут отменить звонок.</span><span class="sxs-lookup"><span data-stu-id="0723c-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="0723c-109">Ringback Bot помогает избежать неожиданного тишины, которое может возникнуть в этом сценарии.</span><span class="sxs-lookup"><span data-stu-id="0723c-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="0723c-110">Для входящих звонков от КТСОП к клиентам Teams в Ringback Bot воспроизводится Специальный звуковой сигнал для вызывающего абонента, указывающий на то, что команды находятся в процессе установки звонка.</span><span class="sxs-lookup"><span data-stu-id="0723c-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="0723c-111">Ringback Bot создает ранний носитель из серверной части Teams.</span><span class="sxs-lookup"><span data-stu-id="0723c-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="0723c-112">В некоторых странах и регионах вам может взиматься плата за звонок, когда вы начнете перетекание материала.</span><span class="sxs-lookup"><span data-stu-id="0723c-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="0723c-113">Настройка Ringback Bot</span><span class="sxs-lookup"><span data-stu-id="0723c-113">Configure the Ringback bot</span></span>

<span data-ttu-id="0723c-114">Используйте командлет [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) , чтобы изменить ранее определенную конфигурацию (SBC) или командлет [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) , чтобы создать новую конфигурацию SBC вместе с параметром **GenerateRingingWhileLocatingUser** для настройки Ringback Bot.</span><span class="sxs-lookup"><span data-stu-id="0723c-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="0723c-115">Чтобы включить Ringback Bot, задайте для параметра **GenerateRingingWhileLocatingUser** значение " **$true**".</span><span class="sxs-lookup"><span data-stu-id="0723c-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="0723c-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0723c-116">This is the default value.</span></span> 

- <span data-ttu-id="0723c-117">Чтобы отключить Ringback Bot, задайте для параметра **GenerateRingingWhileLocatingUser** значение " **$false**".</span><span class="sxs-lookup"><span data-stu-id="0723c-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="0723c-118">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="0723c-118">Related topics</span></span>

- [<span data-ttu-id="0723c-119">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="0723c-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
