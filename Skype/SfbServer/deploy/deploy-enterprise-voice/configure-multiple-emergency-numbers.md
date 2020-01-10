---
title: Настройка нескольких номеров экстренной помощи в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: В этой статье рассказывается о том, как настроить несколько номеров для экстренного реагирования в Skype для бизнеса Server.
ms.openlocfilehash: a0a16536799024085afcce07d6a2a9a0e4c899e1
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001319"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="304f2-103">Настройка нескольких номеров экстренной помощи в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="304f2-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="304f2-104">В этой статье рассказывается о том, как настроить несколько номеров для экстренного реагирования в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="304f2-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="304f2-105">Skype для бизнеса Server теперь поддерживает несколько номеров экстренного реагирования для клиента.</span><span class="sxs-lookup"><span data-stu-id="304f2-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="304f2-106">Несколько номеров для экстренного реагирования — это новая функция, представленная в накопительном обновлении за июнь 2016.</span><span class="sxs-lookup"><span data-stu-id="304f2-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="304f2-107">Перед настройкой среды для поддержки нескольких номеров для экстренного реагирования прочтите [план для нескольких номеров экстренной помощи в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="304f2-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="304f2-108">Если вы еще не обновили накопительный пакет обновления за ноябрь 2016 ноября, ознакомьтесь с [обновлением для Skype для бизнеса Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="304f2-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="304f2-109">Благодаря накопительному обновлению за ноябрь 2016 ноября количество номеров экстренных случаев поддержки возрастает от 5 до 100.</span><span class="sxs-lookup"><span data-stu-id="304f2-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span> 

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="304f2-110">Настройка нескольких номеров экстренных служб</span><span class="sxs-lookup"><span data-stu-id="304f2-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="304f2-111">Чтобы настроить несколько номеров для экстренного реагирования, используйте командлет New-Ксемерженцинумбер, а затем укажите параметр Емерженцинумберс с помощью командлетов [New-кслокатионполици](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) и [Set-кслокатионполици](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="304f2-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="304f2-112">Полное описание всех параметров политики местоположения (например, использование PSTN и расположение) можно найти в разделе [Set-кслокатионполици](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="304f2-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="304f2-113">Следующая команда создает новый номер экстренной службы со строкой набора 911 с помощью командлета New-CsEmergency:</span><span class="sxs-lookup"><span data-stu-id="304f2-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 
```

<span data-ttu-id="304f2-114">Следующая команда связывает номер с указанной политикой расположения путем задания параметра EmergencyNumbers в командлете Set-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="304f2-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

<span data-ttu-id="304f2-115">В следующем примере создается номер экстренной службы с одной маской номера — 112:</span><span class="sxs-lookup"><span data-stu-id="304f2-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

<span data-ttu-id="304f2-116">Следующая команда создает номер для экстренного реагирования с несколькими масками набора номера:</span><span class="sxs-lookup"><span data-stu-id="304f2-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

<span data-ttu-id="304f2-117">В следующем примере добавляется несколько номеров экстренных служб с несколькими масками номера, а затем эти номера связываются с выбранной политикой расположения:</span><span class="sxs-lookup"><span data-stu-id="304f2-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 
```

<span data-ttu-id="304f2-118">В следующем примере настраивается несколько номеров экстренных служб для поставщиков услуг здравоохранения, которые используют номера 911 и 450: </span><span class="sxs-lookup"><span data-stu-id="304f2-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span> 

```powershell
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="304f2-119">В следующем примере настраивается несколько номеров экстренных служб для Лондона:</span><span class="sxs-lookup"><span data-stu-id="304f2-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="304f2-120">В следующем примере настраивается несколько номеров экстренных служб для Индии:</span><span class="sxs-lookup"><span data-stu-id="304f2-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="304f2-121">В следующем примере выполняется удаление существующей записи со строкой набора 911 и масками номеров 112 и 999:</span><span class="sxs-lookup"><span data-stu-id="304f2-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```


