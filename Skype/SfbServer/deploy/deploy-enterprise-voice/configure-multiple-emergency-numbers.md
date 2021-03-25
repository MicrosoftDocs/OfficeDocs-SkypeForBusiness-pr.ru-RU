---
title: Настройка нескольких номеров экстренных служб в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Ознакомьтесь с этой темой, чтобы узнать, как настроить несколько номеров экстренных служб в Skype для бизнеса Server.
ms.openlocfilehash: dc05e94e88b371bb9ee22568eff567e758311233
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111895"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="7463b-103">Настройка нескольких номеров экстренных служб в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7463b-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="7463b-104">Ознакомьтесь с этой темой, чтобы узнать, как настроить несколько номеров экстренных служб в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7463b-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="7463b-105">Skype для бизнеса Server теперь поддерживает несколько номеров экстренных служб для клиента.</span><span class="sxs-lookup"><span data-stu-id="7463b-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="7463b-106">Несколько номеров экстренных служб — это новая функция, представленная в накопительном обновлении за июнь 2016 г.</span><span class="sxs-lookup"><span data-stu-id="7463b-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="7463b-107">Перед настройкой среды для поддержки нескольких номеров экстренных служб обязательно ознакомьтесь с планом для нескольких номеров экстренных служб [в Skype для бизнеса Server.](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="7463b-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7463b-108">Если вы еще не обновились до накопительного обновления за ноябрь 2016 г., см. в рублях [Updates to Skype for Business Server 2015.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="7463b-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="7463b-109">С накопительным обновлением за ноябрь 2016 г. число номеров экстренных служб поддержки увеличивается с 5 до 100.</span><span class="sxs-lookup"><span data-stu-id="7463b-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="7463b-110">Настройка нескольких номеров экстренных служб</span><span class="sxs-lookup"><span data-stu-id="7463b-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="7463b-111">Чтобы настроить несколько номеров аварийной ситуации, используйте New-CsEmergencyNumber, а затем укажите параметр EmergencyNumbers с помощью cmdlets [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) и [Set-CsLocationPolicy.](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="7463b-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="7463b-112">Полное описание всех параметров политики расположения, таких как использование PSTN и требуемое расположение, см. [в инструкции Set-CsLocationPolicy.](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="7463b-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="7463b-113">Следующая команда создает новый номер аварийной ситуации со строкой 911 с помощью командлета New-CsEmergency:</span><span class="sxs-lookup"><span data-stu-id="7463b-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="7463b-114">Следующая команда связывает номер с указанной политикой расположения, указав параметр EmergencyNumbers в командлете Set-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="7463b-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="7463b-115">В следующем примере создается номер аварийной ситуации с одной маской набора 112:</span><span class="sxs-lookup"><span data-stu-id="7463b-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="7463b-116">Следующая команда создает аварийный номер с несколькими масками набора:</span><span class="sxs-lookup"><span data-stu-id="7463b-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="7463b-117">В следующем примере добавляется несколько номеров экстренных служб с несколькими масками на циферблате, а затем сопопосается номера экстренных служб с указанной политикой расположения:</span><span class="sxs-lookup"><span data-stu-id="7463b-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="7463b-118">В следующем примере настраивается несколько номеров экстренных служб для поставщиков медицинских услуг, которые используют как 911, так и 450:</span><span class="sxs-lookup"><span data-stu-id="7463b-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="7463b-119">В следующем примере настраивается несколько номеров экстренных служб для города Лондона:</span><span class="sxs-lookup"><span data-stu-id="7463b-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="7463b-120">В следующем примере настраивается несколько экстренных номеров для Индии:</span><span class="sxs-lookup"><span data-stu-id="7463b-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="7463b-121">В следующем примере удаляется существующая запись со строкой Dial 911 и масками Dial 112 и 999:</span><span class="sxs-lookup"><span data-stu-id="7463b-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```