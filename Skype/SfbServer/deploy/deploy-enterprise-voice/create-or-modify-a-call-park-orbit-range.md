---
title: Создание или изменение диапазона орбит для парковки вызовов в Skype для бизнеса 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Создание или изменение таблицы диапазон орбиты парковки вызовов в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 3617fb739d56e395c31359c6cedae74e9fb63756
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business-2015"></a><span data-ttu-id="696d2-103">Создание или изменение диапазона орбит для парковки вызовов в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="696d2-103">Create or modify a Call Park orbit range in Skype for Business 2015</span></span>
 
<span data-ttu-id="696d2-104">Создание или изменение таблицы диапазон орбиты парковки вызовов в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="696d2-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="696d2-105">Парковка вызовов с помощью орбиты парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="696d2-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="696d2-106">Прежде чем пользователи могут приостанавливать и извлечение вызовов, необходимо настроить таблицу орбиты парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="696d2-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="696d2-107">Необходимо указать диапазоны добавочных номеров (орбиты), что ваша организация будет зарезервировать для парковки вызовов и определите маршрут для этих диапазонов путем указания, какой пул парковки вызовов обрабатывает каждого диапазона.</span><span class="sxs-lookup"><span data-stu-id="696d2-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="696d2-108">При определении диапазонов орбит цель — иметь достаточный орбиты, чтобы любой один орбиты не повторно слишком быстро, но не слишком большом числе орбиты ограничить число расширения, доступные для пользователей или других служб.</span><span class="sxs-lookup"><span data-stu-id="696d2-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="696d2-109">Можно создать несколько диапазонов орбит парковки вызовов для каждого Скайп для пула Business Server, где развернуто приложение парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="696d2-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="696d2-110">Каждый диапазон орбиты парковки вызовов должны иметь глобальное уникальное имя и уникальный набор расширений.</span><span class="sxs-lookup"><span data-stu-id="696d2-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="696d2-p102">Обычно диапазон орбит содержит 100 или менее орбит. Каждый из диапазонов может быть значительно больше, максимальные значения составляют не более 10000 орбит на диапазон и менее 50000 орбит на пул. Если диапазон слишком мал, орбиты используются повторно с большей частотой.</span><span class="sxs-lookup"><span data-stu-id="696d2-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span> 
  
<span data-ttu-id="696d2-114">Для своих диапазонов орбит используйте блоки виртуальных добавочных номеров (которым не назначен телефон или пользователь).</span><span class="sxs-lookup"><span data-stu-id="696d2-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="696d2-115">Назначение номеров прямого входного набора (DID) в качестве номеров орбит парковки вызовов в таблице орбит не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="696d2-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span> 
  
<span data-ttu-id="696d2-116">Используйте одну из следующих процедур для создания или изменения диапазона парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="696d2-116">Use one of the following procedures to create or modify a call park orbit range.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="696d2-117">Чтобы использовать Скайп для панели управления Business Server для создания или изменения диапазона номеров для парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="696d2-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="696d2-118">Войдите на компьютер как член группы RTCUniversalServerAdmins или членом роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="696d2-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="696d2-119">Дополнительные сведения см **Делегирование разрешений на установку**.</span><span class="sxs-lookup"><span data-stu-id="696d2-119">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="696d2-120">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="696d2-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="696d2-121">На панели навигации слева щелкните пункт **Функции голосовой связи**, а затем щелкните **Парковка вызовов**.</span><span class="sxs-lookup"><span data-stu-id="696d2-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>
    
4. <span data-ttu-id="696d2-122">На странице **Парковка вызовов** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="696d2-122">On the **Call Park** page, do one of the following:</span></span>
    
  - <span data-ttu-id="696d2-p104">Чтобы создать новый диапазон орбиты, щелкните **Создать**. В поле **Имя** введите имя, определяющее этот диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="696d2-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="696d2-125">После фиксации диапазона орбиты в базе данных, это имя невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="696d2-125">After you commit the orbit range to the database, you cannot change this name.</span></span> 
  
  - <span data-ttu-id="696d2-p105">Чтобы изменить существующий диапазон орбиты, введите все части имени диапазона орбиты в поле поиска. В списке результатов орбит щелкните нужную орбиту, щелкните **Изменить**, затем **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="696d2-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="696d2-128">В первом поле **Диапазон номеров** введите начальный номер диапазона добавочных номеров для этой орбиты парковки вызовов, а во втором поле **Диапазон номеров** введите конечный номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="696d2-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="696d2-129">Необходимо учитывать.</span><span class="sxs-lookup"><span data-stu-id="696d2-129">Be aware:</span></span>
    
   - <span data-ttu-id="696d2-130">Первый номер диапазона должен быть меньше или равен последнему номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="696d2-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="696d2-131">Длина начального номера диапазона должна такой же, как и у конечного номера диапазона.</span><span class="sxs-lookup"><span data-stu-id="696d2-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>
    
   - <span data-ttu-id="696d2-p107">Диапазон орбит должен быть уникальным. Он не может пересекаться с другими диапазонами.</span><span class="sxs-lookup"><span data-stu-id="696d2-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>
    
   - <span data-ttu-id="696d2-134">Если диапазон орбиты начинается с символа \* или #, диапазон должен быть больше 100.</span><span class="sxs-lookup"><span data-stu-id="696d2-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>
    
   - <span data-ttu-id="696d2-135">Допустимые значения: должны совпадать со строкой регулярного выражения ([\\* | #] ?[1-9]\d{0,7}) | ([1-9] \d {0,8}).</span><span class="sxs-lookup"><span data-stu-id="696d2-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="696d2-136">Это означает, что значение должно быть строк, начиная с любого из символа \* или # или число от 1 до 9 (первого знака не может быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="696d2-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="696d2-137">Если первый символ \* или #, символ должно быть число от 1 до 9 (его не может быть равно нулю).</span><span class="sxs-lookup"><span data-stu-id="696d2-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="696d2-138">Последующие символы могут быть любое число от 0 до 9 до 7 дополнительных символов (например, «#6000», "\*92000" "\*95551212" и «915551212»).</span><span class="sxs-lookup"><span data-stu-id="696d2-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="696d2-139">Если первый символ не \* или #, первым символом должно быть числом 1 до 9 (не может быть равно нулю), а затем до восьми знаков, каждый номер 0 – 9 (например, «915551212», «41212», «300»).</span><span class="sxs-lookup"><span data-stu-id="696d2-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>
    
   - <span data-ttu-id="696d2-p109">Всего для пула не должно быть более 50000 орбит. Каждый диапазон орбит обычно охватывает 100 или меньше орбит, но это число может быть намного больше, но не может превышать 10000. Например, вместо указания начального номера "7000000" и конечного номера "8000000" попробуйте задать начальный номер "7000000" и конечный номер "7000100".</span><span class="sxs-lookup"><span data-stu-id="696d2-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>
    
6. <span data-ttu-id="696d2-143">В **поле полное доменное имя конечного сервера**щелкните полное доменное имя (FQDN) или идентификатор службы приложения, на котором размещается приложение парковки вызовов службы.</span><span class="sxs-lookup"><span data-stu-id="696d2-143">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="696d2-144">Все припаркованные звонки на номера в пределах диапазона, заданного начальным и конечным номером в диапазоне орбит, будет направляться на этот сервер или пул.</span><span class="sxs-lookup"><span data-stu-id="696d2-144">All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>
    
7. <span data-ttu-id="696d2-145">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="696d2-145">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="696d2-146">Чтобы использовать Скайп для консоли Business Server для создания или изменения диапазона номеров для парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="696d2-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="696d2-147">Войдите на компьютер, где установлена Скайп для консоли Business Server как член группы RTCUniversalServerAdmins или с необходимые права пользователя как описано в **Делегирование разрешений на установку**.</span><span class="sxs-lookup"><span data-stu-id="696d2-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="696d2-148">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="696d2-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="696d2-149">Чтобы создать новый диапазон номеров орбит используйте **New-CsCallParkOrbit** .</span><span class="sxs-lookup"><span data-stu-id="696d2-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="696d2-150">Командлет **Set-CsCallParkOrbit** для изменения существующий диапазон номеров орбит.</span><span class="sxs-lookup"><span data-stu-id="696d2-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>
    
    <span data-ttu-id="696d2-151">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="696d2-151">At the command line, run:</span></span>
    
   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="696d2-152">Например:</span><span class="sxs-lookup"><span data-stu-id="696d2-152">For example:</span></span>
     
   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="696d2-153">В приведенном ниже примере показано, как изменять номера в существующем диапазоне орбиты.</span><span class="sxs-lookup"><span data-stu-id="696d2-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>
    
   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="696d2-154">См. также</span><span class="sxs-lookup"><span data-stu-id="696d2-154">See also</span></span>

#### 

[<span data-ttu-id="696d2-155">Новый CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="696d2-155">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="696d2-156">SET-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="696d2-156">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="696d2-157">Удаление диапазона орбиты парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="696d2-157">Delete a Call Park Orbit Range</span></span>](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)

