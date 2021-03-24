---
title: Создание или изменение диапазона орбиты Call Park в Skype для бизнеса
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: Создание или изменение таблицы диапазона орбиты Call Park в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: eab1c3e6e53eaa878546b5fe4a9684147a00c583
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106325"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="1315d-103">Создание или изменение диапазона орбиты Call Park в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1315d-103">Create or modify a Call Park orbit range in Skype for Business</span></span>

<span data-ttu-id="1315d-104">Создание или изменение таблицы диапазона орбиты Call Park в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="1315d-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="1315d-105">Call Park использует орбиты для вызовов парковки.</span><span class="sxs-lookup"><span data-stu-id="1315d-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="1315d-106">Прежде чем пользователи смогут припарковать и получить вызовы, необходимо настроить таблицу орбиты Call Park.</span><span class="sxs-lookup"><span data-stu-id="1315d-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="1315d-107">Необходимо указать диапазоны номеров расширения (орбит), которые организация зарезервировать для вызовов парковки, и определить маршрутику для этих диапазонов, указав, какой пул Call Park обрабатывает каждый диапазон.</span><span class="sxs-lookup"><span data-stu-id="1315d-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="1315d-108">При определении диапазонов орбит требуется обеспечить достаточное число орбит, чтобы ни одна из орбит не использовалась повторно слишком часто, и одновременно не использовать слишком много орбит, чтобы не ограничивать количество добавочных номеров для пользователей и других служб.</span><span class="sxs-lookup"><span data-stu-id="1315d-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="1315d-109">Можно создать несколько диапазонов орбиты Call Park для каждого пула Skype для бизнес-сервера, в котором развернуто приложение Call Park.</span><span class="sxs-lookup"><span data-stu-id="1315d-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="1315d-110">Каждый диапазон орбиты Call Park должен иметь глобально уникальное имя и уникальный набор расширений.</span><span class="sxs-lookup"><span data-stu-id="1315d-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1315d-p102">Обычно диапазон орбит содержит 100 или менее орбит. Каждый из диапазонов может быть значительно больше, максимальные значения составляют не более 10000 орбит на диапазон и менее 50000 орбит на пул. Если диапазон слишком мал, орбиты используются повторно с большей частотой.</span><span class="sxs-lookup"><span data-stu-id="1315d-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>

<span data-ttu-id="1315d-114">Для своих диапазонов орбит используйте блоки виртуальных добавочных номеров (которым не назначен телефон или пользователь).</span><span class="sxs-lookup"><span data-stu-id="1315d-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

> [!NOTE]
> <span data-ttu-id="1315d-115">Назначение номеров прямого внутреннего набора (DID) в качестве номеров орбиты в таблице орбиты Call Park не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1315d-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>

<span data-ttu-id="1315d-116">Используйте одну из следующих процедур для создания или изменения диапазона парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="1315d-116">Use one of the following procedures to create or modify a call park orbit range.</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="1315d-117">Использование панели управления Skype для бизнес-серверов для создания или изменения диапазона номеров для вызовов парковки</span><span class="sxs-lookup"><span data-stu-id="1315d-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="1315d-118">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1315d-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="1315d-119">Дополнительные сведения см. в разделе **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="1315d-119">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="1315d-120">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="1315d-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="1315d-121">В левой панели навигации выберите **Компоненты голосовой связи**, а затем щелкните **Парковка вызовов**.</span><span class="sxs-lookup"><span data-stu-id="1315d-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4. <span data-ttu-id="1315d-122">На странице **Парковка вызовов** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="1315d-122">On the **Call Park** page, do one of the following:</span></span>

   - <span data-ttu-id="1315d-p104">Чтобы создать новый диапазон орбиты, щелкните **Создать**. В поле **Имя** введите имя, определяющее этот диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="1315d-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>

     > [!NOTE]
     > <span data-ttu-id="1315d-125">После фиксации диапазона орбиты в базе данных, это имя невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="1315d-125">After you commit the orbit range to the database, you cannot change this name.</span></span>

   - <span data-ttu-id="1315d-p105">Чтобы изменить существующий диапазон орбиты, введите все части имени диапазона орбиты в поле поиска. В списке результатов орбит щелкните нужную орбиту, щелкните **Изменить**, затем **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="1315d-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5. <span data-ttu-id="1315d-128">В первом поле **Диапазон номеров** введите начальный номер диапазона добавочных номеров для этой орбиты парковки вызовов, а во втором поле **Диапазон номеров** введите конечный номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="1315d-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="1315d-129">Будьте в курсе:</span><span class="sxs-lookup"><span data-stu-id="1315d-129">Be aware:</span></span>

   - <span data-ttu-id="1315d-130">Начальный номер диапазона должен быть меньше или равен конечному номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="1315d-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

   - <span data-ttu-id="1315d-131">Длина значений начального и конечного номеров диапазона должна быть одинаковой.</span><span class="sxs-lookup"><span data-stu-id="1315d-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

   - <span data-ttu-id="1315d-p107">Диапазон орбиты должен быть уникальным и не должен перекрываться ни с одним другим диапазоном.</span><span class="sxs-lookup"><span data-stu-id="1315d-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>

   - <span data-ttu-id="1315d-134">Если диапазон орбиты начинается с символа или #, диапазон должен быть больше \* 100.</span><span class="sxs-lookup"><span data-stu-id="1315d-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>

   - <span data-ttu-id="1315d-135">Допустимые значения: должны соответствовать регулярной строке выражения ([ \\ \*|#]?[ 1-9]\d {0,7} )| ([1-9]\d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="1315d-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="1315d-136">Это означает, что значение должно быть строкой, начинаемой с символа или #, или числом от 1 до 9 (первый символ не \* может быть нулевым).</span><span class="sxs-lookup"><span data-stu-id="1315d-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="1315d-137">Если первый символ или #, следующий символ должен быть \* номером от 1 до 9 (он не может быть нулевым).</span><span class="sxs-lookup"><span data-stu-id="1315d-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="1315d-138">Последующими символами могут быть любые числа от 0 до 9 до семи дополнительных символов (например, "#6000", \* "92000", \* "95551212" и "915551212").</span><span class="sxs-lookup"><span data-stu-id="1315d-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="1315d-139">Если первый символ не является или не является #, первым должен быть номер от 1 до 9 (он не может быть нулем), а затем до восьми символов, каждый из которых имеет значение от 0 до \* 9 (например, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="1315d-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

   - <span data-ttu-id="1315d-p109">В пуле не должно быть более 50 000 орбит. Каждый диапазон орбиты обычно включает не более 100 орбит, но может быть гораздо больше, до 10 000 орбит. Например, вместо указания начального номера "7000000" и конечного номера  "8000000" рекомендуется указывать начальный номер "7000000" и конечный номер "7000100".</span><span class="sxs-lookup"><span data-stu-id="1315d-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

6. <span data-ttu-id="1315d-p110">В поле **Полное доменное имя сервера назначения** выберите полное доменное имя или идентификатор службы приложений, где размещается приложение парковки вызовов. Все вызовы, припаркованные по номерам в диапазоне, заданном начальным и конечным номерами диапазона орбиты, будут маршрутизироваться на этот сервер или в этот пул.</span><span class="sxs-lookup"><span data-stu-id="1315d-p110">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application. All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7. <span data-ttu-id="1315d-145">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="1315d-145">Click **Commit**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="1315d-146">Использование оболочки управления Skype для бизнес-серверов для создания или изменения диапазона номеров для вызовов парковки</span><span class="sxs-lookup"><span data-stu-id="1315d-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="1315d-147">Войдите на компьютер, на котором установлена оболочка управления Skype для бизнес-серверов в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в разрешениях делегирования **установки.**</span><span class="sxs-lookup"><span data-stu-id="1315d-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="1315d-148">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="1315d-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="1315d-149">Используйте командлет **New-CsCallParkOrbit** для создания нового диапазона номеров орбиты.</span><span class="sxs-lookup"><span data-stu-id="1315d-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="1315d-150">Используйте командлет **Set-CsCallParkOrbit** для изменения существующего диапазона номеров орбиты.</span><span class="sxs-lookup"><span data-stu-id="1315d-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>

    <span data-ttu-id="1315d-151">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="1315d-151">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="1315d-152">Пример:</span><span class="sxs-lookup"><span data-stu-id="1315d-152">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="1315d-153">В приведенном ниже примере показано, как изменять номера в существующем диапазоне орбиты.</span><span class="sxs-lookup"><span data-stu-id="1315d-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="1315d-154">См. также</span><span class="sxs-lookup"><span data-stu-id="1315d-154">See also</span></span>

[<span data-ttu-id="1315d-155">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="1315d-155">New-CsCallParkOrbit</span></span>](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="1315d-156">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="1315d-156">Set-CsCallParkOrbit</span></span>](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="1315d-157">Удаление диапазона орбит для парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="1315d-157">Delete a Call Park Orbit Range</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)