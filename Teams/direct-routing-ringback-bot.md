---
title: Настройка бота Ringback для прямой маршрутки
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Узнайте, как использовать бот Ringback для прямой маршрутки, чтобы предотвратить неожиданные тишины, которые могут возникать при звонках.
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
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="3e224-103">Настройка бота Ringback для прямой маршрутки</span><span class="sxs-lookup"><span data-stu-id="3e224-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="3e224-104">В этой статье описан бот Ringback, с помощью которого можно предотвратить неожиданные тишины, которые могут возникать, когда звонки устанавливаются дольше.</span><span class="sxs-lookup"><span data-stu-id="3e224-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="3e224-105">Он доступен для прямой маршрутации в режиме обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="3e224-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="3e224-106">Иногда входящие звонки из телефонной сети общего звонков (STN) на клиенты Teams могут занять больше времени, чем ожидалось.</span><span class="sxs-lookup"><span data-stu-id="3e224-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="3e224-107">Это может произойти по разным причинам.</span><span class="sxs-lookup"><span data-stu-id="3e224-107">This can occur for various reasons.</span></span> <span data-ttu-id="3e224-108">В этом случае звонок может ничего не слышать, клиент Teams не звонит, а некоторые поставщики телекоммуникаций могут отменить звонок.</span><span class="sxs-lookup"><span data-stu-id="3e224-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="3e224-109">В этом сценарии бот Ringback помогает избежать неожиданного тишины.</span><span class="sxs-lookup"><span data-stu-id="3e224-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="3e224-110">Для входящие вызовы из PSTN в клиенты Teams, бот Ringback воспроизводит характерный звуковой сигнал для вызываемого звонка, чтобы показать, что Teams находится в процессе установления звонка.</span><span class="sxs-lookup"><span data-stu-id="3e224-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="3e224-111">Бот Ringback создает мультимедиа на ранних стадиях из backend Teams.</span><span class="sxs-lookup"><span data-stu-id="3e224-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="3e224-112">В некоторых странах и регионах с вас может взиматься плата за звонок, когда начнется поток мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="3e224-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="3e224-113">Настройка бота Ringback</span><span class="sxs-lookup"><span data-stu-id="3e224-113">Configure the Ringback bot</span></span>

<span data-ttu-id="3e224-114">Используйте cmdlet [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) для изменения ранее определенной конфигурации граничного контроллера сеанса (SBC) или для создания новой конфигурации SBC с параметром GenerateRingingWhileLocatingUser(New-CsOnlinePSTNGateway), чтобы создать новую конфигурацию SBC, а также параметр **GenerateRingingWhileLocatingUser** для настройки бота Ringback: [](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway)</span><span class="sxs-lookup"><span data-stu-id="3e224-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="3e224-115">Чтобы включить бот Ringback, установите для параметра **GenerateRingingWhileLocatingUser** **$True.**</span><span class="sxs-lookup"><span data-stu-id="3e224-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="3e224-116">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="3e224-116">This is the default value.</span></span> 

- <span data-ttu-id="3e224-117">Чтобы отключить бот Ringback, установите для параметра **GenerateRingingWhileLocatingUser** **$False.**</span><span class="sxs-lookup"><span data-stu-id="3e224-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="3e224-118">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3e224-118">Related topics</span></span>

- [<span data-ttu-id="3e224-119">Обзор PowerShell в Teams</span><span class="sxs-lookup"><span data-stu-id="3e224-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
