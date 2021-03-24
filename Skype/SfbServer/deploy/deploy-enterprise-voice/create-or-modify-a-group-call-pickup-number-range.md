---
title: Создание или изменение диапазона номеров группового вызова в Skype для бизнеса
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Создание или изменение диапазона номеров группового вызова в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: e71915519014b1fa4cfffa3172327e9949ed73a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100425"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="94ef1-103">Создание или изменение диапазона номеров группового вызова в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="94ef1-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="94ef1-104">Создание или изменение диапазона номеров группового вызова в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="94ef1-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="94ef1-105">Выбор группового вызова основан на приложении Call Park.</span><span class="sxs-lookup"><span data-stu-id="94ef1-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="94ef1-106">При развертывании группового вызова необходимо настроить таблицу орбиты парка вызовов с диапазонами номеров телефонов, назначенных в качестве номеров групп вызова.</span><span class="sxs-lookup"><span data-stu-id="94ef1-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="94ef1-107">Эти групповые номера — это номера, на которые пользователи звонят для вызова другого пользователя.</span><span class="sxs-lookup"><span data-stu-id="94ef1-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="94ef1-108">Как и номера орбиты парка вызовов, номера групп вызова должны быть виртуальными расширениями, которые не имеют пользователя или телефона, назначенного им.</span><span class="sxs-lookup"><span data-stu-id="94ef1-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="94ef1-109">Каждый пул переднего конца, в котором развертывается групповой вызов, может иметь один или несколько диапазонов номеров групп вызова.</span><span class="sxs-lookup"><span data-stu-id="94ef1-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="94ef1-110">Диапазоны номеров групп должны быть глобально уникальными в развертывании и должны быть назначены в качестве типа **GroupPickup.**</span><span class="sxs-lookup"><span data-stu-id="94ef1-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="94ef1-111">Используйте следующую процедуру для создания или изменения диапазона номеров группы вызова в таблице орбиты парка вызовов.</span><span class="sxs-lookup"><span data-stu-id="94ef1-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="94ef1-112">Чтобы создать, изменить, удалить и просмотреть диапазоны номеров группового вызова в таблице орбиты парка вызовов, необходимо использовать Оболочку управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="94ef1-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="94ef1-113">Диапазоны номеров группового вызова недоступны в панели управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="94ef1-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="94ef1-114">Диапазоны номеров групп вызова должны соответствовать следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="94ef1-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="94ef1-115">Начальный номер диапазона должен быть меньше или равен конечному номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="94ef1-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="94ef1-116">Значение начального номера диапазона должно иметь такую же длину, что и конечный номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="94ef1-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="94ef1-p104">Диапазон номеров должен быть уникальным. Он не может накладываться на любой другой диапазон.</span><span class="sxs-lookup"><span data-stu-id="94ef1-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="94ef1-119">Если диапазон номеров начинается с символа или #, диапазон должен быть больше \* 100.</span><span class="sxs-lookup"><span data-stu-id="94ef1-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="94ef1-120">Допустимые значения: должны соответствовать регулярной строке выражения ([ \\ \*|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="94ef1-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="94ef1-121">Это означает, что значение должно быть строкой, начинаемой с символа или #, или числом от 1 до 9 (первый символ не \* может быть нулевым).</span><span class="sxs-lookup"><span data-stu-id="94ef1-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="94ef1-122">Если первый символ или #, следующий символ должен быть \* номером от 1 до 9 (он не может быть нулевым).</span><span class="sxs-lookup"><span data-stu-id="94ef1-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="94ef1-123">Последующими символами могут быть любые числа от 0 до 9 до семи дополнительных символов (например, "#6000", \* "92000", \* "95551212" и "915551212").</span><span class="sxs-lookup"><span data-stu-id="94ef1-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="94ef1-124">Если первый символ не является или не является #, первым должен быть номер от 1 до 9 (он не может быть нулем), а затем до восьми символов, каждый из которых имеет значение от 0 до \* 9 (например, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="94ef1-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="94ef1-125">Создание или изменение диапазона групп вызова.</span><span class="sxs-lookup"><span data-stu-id="94ef1-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="94ef1-126">Войдите на компьютер, на котором установлена оболочка управления Skype для бизнес-серверов в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разрешениях делегирования **установки.**</span><span class="sxs-lookup"><span data-stu-id="94ef1-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="94ef1-127">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="94ef1-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="94ef1-128">Используйте **New-CsCallParkOrbit** для создания нового диапазона номеров групп вызова.</span><span class="sxs-lookup"><span data-stu-id="94ef1-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="94ef1-129">Используйте **Set-CsCallParkOrbit для** изменения существующего диапазона номеров вызова.</span><span class="sxs-lookup"><span data-stu-id="94ef1-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="94ef1-130">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="94ef1-130">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="94ef1-131">Пример:</span><span class="sxs-lookup"><span data-stu-id="94ef1-131">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="94ef1-132">В следующем примере показано, как изменить диапазон номеров с орбит парка вызовов на группы вызова.</span><span class="sxs-lookup"><span data-stu-id="94ef1-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="94ef1-133">Используйте этот комлет, чтобы изменить тип, заданный в диапазоны номеров, только если изначально указан неправильный тип и диапазон групп еще не используется.</span><span class="sxs-lookup"><span data-stu-id="94ef1-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="94ef1-134">Если вы измените диапазон номеров от CallPark до GroupPickup или наоборот, а диапазон номеров уже используется, то для этого диапазона номеров перестанут работать либо call Park, либо Group Call Pickup.</span><span class="sxs-lookup"><span data-stu-id="94ef1-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="94ef1-135">Например, если вы измените диапазон номеров от CallPark до GroupPick, приложение Call Park больше не сможет использовать этот диапазон орбит для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="94ef1-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="94ef1-136">См. также</span><span class="sxs-lookup"><span data-stu-id="94ef1-136">See also</span></span>

[<span data-ttu-id="94ef1-137">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="94ef1-137">New-CsCallParkOrbit</span></span>](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="94ef1-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="94ef1-138">Set-CsCallParkOrbit</span></span>](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="94ef1-139">Удаление диапазона орбит для парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="94ef1-139">Delete a Call Park Orbit Range</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)