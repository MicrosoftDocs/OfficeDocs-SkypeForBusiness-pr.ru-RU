---
title: Создание или изменение диапазона номеров для группового звонка в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Создание или изменение диапазона номеров для группового звонка в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 546fefd996286678aae77338b4e0867285670a57
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001719"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="e31cb-103">Создание или изменение диапазона номеров для группового звонка в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="e31cb-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="e31cb-104">Создание или изменение диапазона номеров для группового звонка в Skype для бизнеса Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="e31cb-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="e31cb-105">Отправка группового звонка осуществляется на основе заявления на приостановку звонков.</span><span class="sxs-lookup"><span data-stu-id="e31cb-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="e31cb-106">При развертывании группового звонка необходимо настроить таблицу на приостановку соединения с диапазонами номеров телефонов, которые назначены номерам групп для отправки звонков.</span><span class="sxs-lookup"><span data-stu-id="e31cb-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="e31cb-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span><span class="sxs-lookup"><span data-stu-id="e31cb-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="e31cb-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span><span class="sxs-lookup"><span data-stu-id="e31cb-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="e31cb-109">У каждого пула переднего плана, в котором вы развертываете раскладки группового звонка, может быть один или несколько диапазонов номеров групп для раскладки звонков.</span><span class="sxs-lookup"><span data-stu-id="e31cb-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="e31cb-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span><span class="sxs-lookup"><span data-stu-id="e31cb-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="e31cb-111">Воспользуйтесь следующей процедурой для создания или изменения диапазона номеров группы ответа на звонки в таблице орбит парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="e31cb-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="e31cb-112">Для создания, изменения, удаления и просмотра групповых диапазонов для приема звонков в таблице "приостановить Звонок" необходимо использовать консоль управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e31cb-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="e31cb-113">На панели управления "Skype для бизнеса Server" не поддерживаются диапазоны номеров для отправки групповых звонков.</span><span class="sxs-lookup"><span data-stu-id="e31cb-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="e31cb-114">Диапазоны номеров группы ответа на звонки должны соответствовать следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="e31cb-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="e31cb-115">Первый номер диапазона должен быть меньше или равен последнему номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="e31cb-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="e31cb-116">Длина начального номера диапазона должна такой же, как и у конечного номера диапазона.</span><span class="sxs-lookup"><span data-stu-id="e31cb-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="e31cb-p104">Диапазон номеров должен быть уникальным. Он не может накладываться на любой другой диапазон.</span><span class="sxs-lookup"><span data-stu-id="e31cb-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="e31cb-119">Если диапазон номеров начинается с символа \* или #, диапазон должен быть больше 100.</span><span class="sxs-lookup"><span data-stu-id="e31cb-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="e31cb-120">Допустимые значения: должны соответствовать строке регулярного выражения (\\[\* | #]? [ 1-9] \d{0,7}) | ([1-9] \d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="e31cb-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="e31cb-121">Это означает, что значение должно быть строкой, начинающейся с \* символа или # или числа 1 – 9 (первый символ не может равняться нулю).</span><span class="sxs-lookup"><span data-stu-id="e31cb-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="e31cb-122">Если первый символ имеет \* значение или #, следующий символ должен быть числом от 1 до 9 (оно не может равняться нулю).</span><span class="sxs-lookup"><span data-stu-id="e31cb-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="e31cb-123">Последующие символы могут быть числами от 0 до 9 до семи дополнительных символов (например, "#6000", "\*92000", "\*95551212" и "915551212").</span><span class="sxs-lookup"><span data-stu-id="e31cb-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="e31cb-124">Если первый символ не \* является числом, то первый символ должен быть цифрами от 1 до 9 (он не может быть равен нулю), после чего следует использовать до восьми символов, каждый из которых содержит число от 0 до 9 (например, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="e31cb-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="e31cb-125">Создание или изменение диапазона номеров группы ответа на звонки</span><span class="sxs-lookup"><span data-stu-id="e31cb-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="e31cb-126">Войдите в систему на компьютере, на котором установлена консоль управления Skype для бизнеса Server, в качестве участника группы Рткуниверсалсерверадминс или с необходимыми правами пользователя, описанными в разделе **Делегирование разрешений на настройку**.</span><span class="sxs-lookup"><span data-stu-id="e31cb-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="e31cb-127">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="e31cb-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="e31cb-128">Используйте командлет  **New-CsCallParkOrbit** для создания нового диапазона номеров группы ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="e31cb-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="e31cb-129">Используйте командлет **Set-CsCallParkOrbit** для изменения существующего диапазона номеров ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="e31cb-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="e31cb-130">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e31cb-130">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="e31cb-131">Например:</span><span class="sxs-lookup"><span data-stu-id="e31cb-131">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="e31cb-132">Следующий пример показывает, как изменить диапазон номеров с орбит парковки вызовов на группы ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="e31cb-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="e31cb-133">Используйте этот командлет для изменения типа, назначенного диапазонам номеров, только в том случае, если вы изначально указали неправильный тип, а данный диапазон номеров группы пока не используется.</span><span class="sxs-lookup"><span data-stu-id="e31cb-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="e31cb-134">Если изменить диапазон номеров с CallPark на GroupPickup или наоборот, когда этот диапазон уже используется, то для этого диапазона номеров будет прекращена работа компонента парковки вызовов или группового ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="e31cb-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="e31cb-135">Например, если изменить диапазон номеров с Каллпарк на Грауппикк, приложение для парковки звонков больше не сможет использовать этот диапазон орбиты для приостановки звонка.</span><span class="sxs-lookup"><span data-stu-id="e31cb-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="e31cb-136">См. также</span><span class="sxs-lookup"><span data-stu-id="e31cb-136">See also</span></span>

[<span data-ttu-id="e31cb-137">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="e31cb-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="e31cb-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="e31cb-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="e31cb-139">Удаление диапазона орбиты на расстоянии вверх</span><span class="sxs-lookup"><span data-stu-id="e31cb-139">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
