---
title: Настройка нескольких номеров экстренных служб в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: В этом разделе рассказывается, как настроить несколько номеров экстренных служб в Skype для бизнеса Server.
ms.openlocfilehash: 81d3dbed919c936eb8a656d123f5c44e445044d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027800"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="1dd83-103">Настройка нескольких номеров экстренных служб в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1dd83-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="1dd83-104">В этом разделе рассказывается, как настроить несколько номеров экстренных служб в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1dd83-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="1dd83-105">Skype для бизнеса Server теперь поддерживает несколько номеров экстренных служб для клиента.</span><span class="sxs-lookup"><span data-stu-id="1dd83-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="1dd83-106">Несколько номеров для экстренных служб — это новая функция, появившаяся в накопительном пакете обновления за июнь 2016 года.</span><span class="sxs-lookup"><span data-stu-id="1dd83-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="1dd83-107">Прежде чем настраивать среду для поддержки нескольких номеров экстренных служб, ознакомьтесь со сведениями [о планировании нескольких номеров экстренных служб в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="1dd83-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1dd83-108">Если вы еще не обновили накопительный пакет обновления 2016 для системы, ознакомьтесь со статьей [Updates to Skype для бизнеса Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="1dd83-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="1dd83-109">С накопительным пакетом обновления за ноябрь 2016 ноября количество номеров экстренных служб поддержки возрастает от 5 до 100.</span><span class="sxs-lookup"><span data-stu-id="1dd83-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="1dd83-110">Настройка нескольких номеров экстренных служб</span><span class="sxs-lookup"><span data-stu-id="1dd83-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="1dd83-111">Чтобы настроить несколько номеров экстренных служб, используйте командлет New – Ксемерженцинумбер, а затем укажите параметр EmergencyNumbers с помощью командлетов [New — CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) и [Set + CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="1dd83-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="1dd83-112">Полное описание всех параметров политики расположения, таких как использование PSTN и требуемое расположение, приведено в разделе [Set – CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1dd83-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="1dd83-113">Следующая команда создает новый номер для экстренного реагирования с набором строк 911 с помощью командлета New – Ксемерженци:</span><span class="sxs-lookup"><span data-stu-id="1dd83-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="1dd83-114">Следующая команда связывает номер с указанной политикой расположения, указывая параметр EmergencyNumbers в командлете Set – CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="1dd83-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="1dd83-115">В следующем примере создается номер для экстренного реагирования с одной маской набора номера 112:</span><span class="sxs-lookup"><span data-stu-id="1dd83-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="1dd83-116">Следующая команда создает номер для экстренного реагирования с несколькими масками набора номера:</span><span class="sxs-lookup"><span data-stu-id="1dd83-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="1dd83-117">В следующем примере показано, как добавить несколько номеров экстренных служб с несколькими масками набора номера, а затем связать номера экстренных служб с указанной политикой расположения:</span><span class="sxs-lookup"><span data-stu-id="1dd83-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="1dd83-118">В следующем примере настраивается несколько номеров экстренных служб для поставщиков услуг здравоохранения, использующих как 911, так и 450:</span><span class="sxs-lookup"><span data-stu-id="1dd83-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="1dd83-119">В следующем примере настраивается несколько номеров экстренных служб для города Лондона:</span><span class="sxs-lookup"><span data-stu-id="1dd83-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="1dd83-120">В следующем примере настраивается несколько номеров экстренных служб для Индии:</span><span class="sxs-lookup"><span data-stu-id="1dd83-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="1dd83-121">В следующем примере удаляется существующая запись с набором номера 911 и масками набора 112 и 999:</span><span class="sxs-lookup"><span data-stu-id="1dd83-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
