---
title: 'Lync Server 2013: создание или изменение диапазона номеров для группового ответа на звонки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d215fe6959b169ec5f092757174d105a75a5402a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="f2872-102">Создание или изменение диапазона номеров для группового ответа на звонки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2872-102">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2872-103">_**Последнее изменение темы:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="f2872-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="f2872-104">Используйте следующую процедуру для создания или изменения диапазона номеров группы ответа на звонки в таблице орбит парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="f2872-104">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f2872-105">Для создания, изменения, удаления и просмотра групп номеров для ответа на звонки в таблице орбит парковки вызовов необходимо использовать командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2872-105">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="f2872-106">Диапазоны номеров для группового ответа на звонки недоступны в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f2872-106">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="f2872-107">Диапазону номеров группы ответа на звонки должен быть назначен тип Грауппиккуп.</span><span class="sxs-lookup"><span data-stu-id="f2872-107">The call pickup group number range must be assigned a type of GroupPickup.</span></span> <span data-ttu-id="f2872-108">Пользователи могут получать групповые звонки только в том случае, если номер группы, которым она назначена, имеет тип Грауппиккуп.</span><span class="sxs-lookup"><span data-stu-id="f2872-108">Users are enabled for Group Call Pickup only if the group number that they are assigned is type GroupPickup.</span></span>



</div>

<span data-ttu-id="f2872-109">Диапазоны номеров группы ответа на звонки должны соответствовать следующим правилам:</span><span class="sxs-lookup"><span data-stu-id="f2872-109">The call pickup group number ranges must comply with the following rules:</span></span>

  - <span data-ttu-id="f2872-110">Начальный номер диапазона должен быть меньше или равен конечному номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="f2872-110">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="f2872-111">Значение начального номера диапазона должно иметь такую же длину, что и конечный номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="f2872-111">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="f2872-p103">Диапазон номеров должен быть уникальным. Он не может накладываться на любой другой диапазон.</span><span class="sxs-lookup"><span data-stu-id="f2872-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="f2872-114">Если диапазон номеров начинается с символа \* или \#, диапазон должен быть больше 100.</span><span class="sxs-lookup"><span data-stu-id="f2872-114">If the number range begins with the character \* or \#, the range must be greater than 100.</span></span>

  - <span data-ttu-id="f2872-115">Допустимые значения: должны быть согласованы со строкой регулярного\[\\\*|\#\]выражения (?\[ 1-9\]\\d{0,7}) | (\[1-9\]\\d{0,8}).</span><span class="sxs-lookup"><span data-stu-id="f2872-115">Valid values: Must match the regular expression string (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}).</span></span> <span data-ttu-id="f2872-116">Это означает, что значение должно быть строкой, начинающейся с \* символа \# или цифры от 1 до 9 (первый символ не может быть нулевым).</span><span class="sxs-lookup"><span data-stu-id="f2872-116">This means the value must be a string beginning with either the character \* or \# or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="f2872-117">Если первый символ является \* или \#, то следующий символ должен быть цифрой от 1 до 9 (он не может быть нулевым).</span><span class="sxs-lookup"><span data-stu-id="f2872-117">If the first character is \* or \#, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="f2872-118">Последующими символами могут быть цифры от 0 до 9 до семи дополнительных символов (например,\#"6000",\*"92000",\*"95551212" и "915551212").</span><span class="sxs-lookup"><span data-stu-id="f2872-118">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "\#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="f2872-119">Если первый символ не \* или \#, то первым символом должен быть цифра от 1 до 9 (он не может быть равен нулю), а должен содержать до восьми символов, каждый из которых имеет цифру от 0 до 9 (например, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="f2872-119">If the first character is not \* or \#, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="f2872-120">Создание или изменение диапазона группы ответа на звонки</span><span class="sxs-lookup"><span data-stu-id="f2872-120">To create or modify a call pickup group range</span></span>

1.  <span data-ttu-id="f2872-121">Выполните вход на компьютер, на котором установлена командная консоль Lync Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разделе [Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f2872-121">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f2872-122">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="f2872-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="f2872-123">Используйте **New – CsCallParkOrbit** для создания нового диапазона номеров группы ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="f2872-123">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="f2872-124">Используйте **Set – CsCallParkOrbit** , чтобы изменить существующий диапазон номеров для ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="f2872-124">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="f2872-125">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f2872-125">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    <span data-ttu-id="f2872-126">Пример:</span><span class="sxs-lookup"><span data-stu-id="f2872-126">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    <span data-ttu-id="f2872-127">В приведенном ниже примере показано, как изменить диапазон номеров с орбит парковки вызовов на группы ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="f2872-127">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f2872-128">Используйте этот командлет для изменения типа, назначенного для диапазонов номеров, только в том случае, если изначально указан неверный тип, а диапазон групп еще не используется.</span><span class="sxs-lookup"><span data-stu-id="f2872-128">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="f2872-129">Если вы изменяете диапазон номеров с CallPark на Грауппиккуп или наоборот, а диапазон номеров уже используется, то для этого диапазона номеров будет прекращена работа приостановки вызовов или групповой отправки звонков.</span><span class="sxs-lookup"><span data-stu-id="f2872-129">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="f2872-130">Например, если изменить диапазон номеров с CallPark на Грауппикк, то приложение парковки вызовов больше не сможет использовать этот диапазон орбит для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="f2872-130">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f2872-131">См. также</span><span class="sxs-lookup"><span data-stu-id="f2872-131">See Also</span></span>


[<span data-ttu-id="f2872-132">Удаление диапазона орбит парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f2872-132">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="f2872-133">New — CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="f2872-133">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="f2872-134">Set — CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="f2872-134">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

