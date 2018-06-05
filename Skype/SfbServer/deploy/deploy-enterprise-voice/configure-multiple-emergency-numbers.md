---
title: Настройка нескольких номеров экстренных служб в Skype для бизнеса 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 4/21/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: В этой статье описываются способы настройки нескольких номеров экстренных служб в Skype для бизнеса Server 2015.
ms.openlocfilehash: 176233639a6ca935165e4640471377cc012db103
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568237"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business-2015"></a><span data-ttu-id="da144-103">Настройка нескольких номеров экстренных служб в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="da144-103">Configure multiple emergency numbers in Skype for Business 2015</span></span>
 
<span data-ttu-id="da144-104">В этой статье описываются способы настройки нескольких номеров экстренных служб в Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="da144-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="da144-105">Скайп для Business Server теперь поддерживает несколько аварийного номера для клиента.</span><span class="sxs-lookup"><span data-stu-id="da144-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="da144-106">Несколько аварийного номера — это новая возможность, введенные в 2016 июня накопительного обновления.</span><span class="sxs-lookup"><span data-stu-id="da144-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="da144-107">Прежде чем настраивать среду для поддержки нескольких аварийного номера, обязательно прочитайте [Планирование нескольких аварийного номера в Скайп для Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="da144-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="da144-108">Если вы еще не был обновлен для 2016 ноября накопительные пакеты обновления, посетите страницу [обновления для Скайп для Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="da144-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="da144-109">С помощью 2016 ноября накопительные пакеты обновления, количество номеров экстренные службы поддержки увеличивается от 5 до 100.</span><span class="sxs-lookup"><span data-stu-id="da144-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span> 
  
## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="da144-110">Настройка нескольких номеров экстренных служб</span><span class="sxs-lookup"><span data-stu-id="da144-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="da144-111">Чтобы настроить несколько аварийного номера, используйте командлет New-CsEmergencyNumber и укажите параметр EmergencyNumbers с помощью командлетов [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) и [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="da144-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="da144-112">Полное описание всех расположение параметры политики, такие как режим работы с ТСОП и необходимости расположение в разделе [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="da144-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>
  
<span data-ttu-id="da144-113">Следующая команда создает новый номер экстренной службы со строкой набора 911 с помощью командлета New-CsEmergency:</span><span class="sxs-lookup"><span data-stu-id="da144-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 
```

<span data-ttu-id="da144-114">Следующая команда связывает номер с указанной политикой расположения путем задания параметра EmergencyNumbers в командлете Set-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="da144-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>
  
```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 

```

<span data-ttu-id="da144-115">В следующем примере создается номер экстренной службы с одной маской номера — 112:</span><span class="sxs-lookup"><span data-stu-id="da144-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 

```

<span data-ttu-id="da144-116">Далее команда создает аварийного номера с несколько масок телефонных:</span><span class="sxs-lookup"><span data-stu-id="da144-116">The next command creates an emergency number with multiple dial masks:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 

```

<span data-ttu-id="da144-117">В следующем примере добавляется несколько номеров экстренных служб с несколькими масками номера, а затем эти номера связываются с выбранной политикой расположения:</span><span class="sxs-lookup"><span data-stu-id="da144-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 

```

<span data-ttu-id="da144-118">В следующем примере настраивается несколько номеров экстренных служб для поставщиков услуг здравоохранения, которые используют номера 911 и 450: </span><span class="sxs-lookup"><span data-stu-id="da144-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span> 
  
```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="da144-119">В следующем примере настраивается несколько номеров экстренных служб для Лондона:</span><span class="sxs-lookup"><span data-stu-id="da144-119">The next example configures multiple emergency numbers for the city of London:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}

```

<span data-ttu-id="da144-120">В следующем примере настраивается несколько номеров экстренных служб для Индии:</span><span class="sxs-lookup"><span data-stu-id="da144-120">The next example configures multiple emergency numbers for India:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}

```

<span data-ttu-id="da144-121">В следующем примере выполняется удаление существующей записи со строкой набора 911 и масками номеров 112 и 999:</span><span class="sxs-lookup"><span data-stu-id="da144-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 

```


