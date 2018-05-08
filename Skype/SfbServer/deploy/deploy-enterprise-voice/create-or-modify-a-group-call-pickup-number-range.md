---
title: Создание или изменение диапазона номеров для группового ответа на звонки в Skype для бизнеса 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Создание или изменение группы вызова раскладки диапазон номеров в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: e67c8094bf66590d006fbce75f49258bb3f4f2a9
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business-2015"></a><span data-ttu-id="8f25a-103">Создание или изменение диапазона номеров для группового ответа на звонки в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="8f25a-103">Create or modify a Group Call Pickup number range in Skype for Business 2015</span></span>
 
<span data-ttu-id="8f25a-104">Создание или изменение группы вызова раскладки диапазон номеров в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="8f25a-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="8f25a-105">Групповой звонок раскладки основано на приложение парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="8f25a-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="8f25a-106">При развертывании группы вызова раскладки, необходимо настроить таблицы орбиты парковки вызовов с диапазонами телефонных номеров, которые обозначены как номера раскладки групповой звонок.</span><span class="sxs-lookup"><span data-stu-id="8f25a-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="8f25a-107">Эти номера группы — это числа, который пользователи для сбора вызовов, которые мелодий для другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="8f25a-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>
  
<span data-ttu-id="8f25a-108">Как номеров орбит парковки вызовов, вызвать раскладки группы номеров необходимость виртуального расширения, которые не имеют пользователя или назначен телефон.</span><span class="sxs-lookup"><span data-stu-id="8f25a-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="8f25a-109">Каждый пул переднего плана, где развертывание группы вызова раскладки может иметь один или несколько диапазонов номеров раскладки групповой звонок.</span><span class="sxs-lookup"><span data-stu-id="8f25a-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="8f25a-110">Диапазоны номеров группы должно быть глобально уникальным в развертывании и должен быть назначен в качестве типа **GroupPickup** .</span><span class="sxs-lookup"><span data-stu-id="8f25a-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>
  
<span data-ttu-id="8f25a-111">Воспользуйтесь следующей процедурой для создания или изменения диапазона номеров группы ответа на звонки в таблице орбит парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="8f25a-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="8f25a-112">Скайп для консоли Business Server необходимо использовать для создания, изменение, удаление и Просмотр группы вызова раскладки диапазоны номеров в таблице орбит парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="8f25a-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="8f25a-113">Диапазоны номеров группы вызова раскладки, недоступны в Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="8f25a-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span> 
  
<span data-ttu-id="8f25a-114">Диапазоны номеров группы ответа на звонки должны соответствовать следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="8f25a-114">The call pickup group number ranges must comply with the following rules:</span></span>
  
- <span data-ttu-id="8f25a-115">Первый номер диапазона должен быть меньше или равен последнему номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="8f25a-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
- <span data-ttu-id="8f25a-116">Длина начального номера диапазона должна такой же, как и у конечного номера диапазона.</span><span class="sxs-lookup"><span data-stu-id="8f25a-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>
    
- <span data-ttu-id="8f25a-p104">Диапазон номеров должен быть уникальным. Он не может накладываться на любой другой диапазон.</span><span class="sxs-lookup"><span data-stu-id="8f25a-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>
    
- <span data-ttu-id="8f25a-119">Если диапазон номеров начинается с символа \* или #, диапазон должен быть больше 100.</span><span class="sxs-lookup"><span data-stu-id="8f25a-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>
    
- <span data-ttu-id="8f25a-120">Допустимые значения: должны совпадать со строкой регулярного выражения ([\\* | #] ? [1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="8f25a-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="8f25a-121">Это означает, что значение должно быть строк, начиная с любого из символа \* или # или число от 1 до 9 (первого знака не может быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="8f25a-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="8f25a-122">Если первый символ \* или #, символ должно быть число от 1 до 9 (его не может быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="8f25a-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="8f25a-123">Последующие символы могут быть любое число от 0 до 9 до 7 дополнительных символов (например, «#6000», "\*92000" "\*95551212" и «915551212»).</span><span class="sxs-lookup"><span data-stu-id="8f25a-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="8f25a-124">Если первый символ не \* или #, первым символом должно быть числом 1 до 9 (не может быть равно нулю), а затем до восьми знаков, каждый номер 0 – 9 (например, «915551212», «41212», «300»).</span><span class="sxs-lookup"><span data-stu-id="8f25a-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>
    
### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="8f25a-125">Создание или изменение диапазона номеров группы ответа на звонки</span><span class="sxs-lookup"><span data-stu-id="8f25a-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="8f25a-126">Войдите на компьютер, где установлена Скайп для консоли Business Server как член группы RTCUniversalServerAdmins или с необходимые права пользователя как описано в **Делегирование разрешений на установку**.</span><span class="sxs-lookup"><span data-stu-id="8f25a-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="8f25a-127">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="8f25a-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="8f25a-128">**New-CsCallParkOrbit** используется для создания нового диапазона номеров раскладки групповой звонок.</span><span class="sxs-lookup"><span data-stu-id="8f25a-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="8f25a-129">Командлет **Set-CsCallParkOrbit** для изменения существующий диапазон номеров раскладки звонок.</span><span class="sxs-lookup"><span data-stu-id="8f25a-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="8f25a-130">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="8f25a-130">At the command line, run:</span></span>
    
   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="8f25a-131">Например:</span><span class="sxs-lookup"><span data-stu-id="8f25a-131">For example:</span></span>
    
   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="8f25a-132">Следующий пример показывает, как изменить диапазон номеров с орбит парковки вызовов на группы ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="8f25a-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="8f25a-133">Используйте этот командлет для изменения типа, назначенного диапазонам номеров, только в том случае, если вы изначально указали неправильный тип, а данный диапазон номеров группы пока не используется.</span><span class="sxs-lookup"><span data-stu-id="8f25a-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="8f25a-134">Если изменить диапазон номеров с CallPark на GroupPickup или наоборот, когда этот диапазон уже используется, то для этого диапазона номеров будет прекращена работа компонента парковки вызовов или группового ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="8f25a-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="8f25a-135">Например чтобы изменить диапазон номеров из CallPark GroupPick, приложение парковки вызовов больше не можно использовать диапазон орбиты для приостановки звонков.</span><span class="sxs-lookup"><span data-stu-id="8f25a-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8f25a-136">См. также</span><span class="sxs-lookup"><span data-stu-id="8f25a-136">See also</span></span>

#### 

[<span data-ttu-id="8f25a-137">Новый CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="8f25a-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="8f25a-138">SET-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="8f25a-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="8f25a-139">Удаление диапазона орбиты парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="8f25a-139">Delete a Call Park Orbit Range</span></span>](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)

