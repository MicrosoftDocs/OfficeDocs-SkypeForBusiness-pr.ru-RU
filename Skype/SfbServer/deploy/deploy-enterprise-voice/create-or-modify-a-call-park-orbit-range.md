---
title: Создание или изменение диапазона орбит парковки вызовов в Skype для бизнеса
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
description: Создание или изменение таблицы диапазона орбит парковки вызовов в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 6a17b4faaad026376bccad060cb421a5e2cfa1df
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805479"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="96c6e-103">Создание или изменение диапазона орбит парковки вызовов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="96c6e-103">Create or modify a Call Park orbit range in Skype for Business</span></span>

<span data-ttu-id="96c6e-104">Создание или изменение таблицы диапазона орбит парковки вызовов в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="96c6e-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="96c6e-105">Парковка вызовов использует орбиты для парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="96c6e-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="96c6e-106">Прежде чем пользователи смогут парковать и извлекать вызовы, необходимо настроить таблицу орбит парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="96c6e-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="96c6e-107">Необходимо указать диапазоны номеров (орбит), которые организация будет резервировать для парковки вызовов, и определить маршрутизации для этих диапазонов, указав, какой пул парковки вызовов обрабатывает каждый диапазон.</span><span class="sxs-lookup"><span data-stu-id="96c6e-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="96c6e-108">При определении диапазонов орбит требуется обеспечить достаточное число орбит, чтобы ни одна из орбит не использовалась повторно слишком часто, и одновременно не использовать слишком много орбит, чтобы не ограничивать количество добавочных номеров для пользователей и других служб.</span><span class="sxs-lookup"><span data-stu-id="96c6e-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="96c6e-109">Можно создать несколько диапазонов орбит парковки вызовов для каждого пула Skype для бизнеса Server, в котором развернуто приложение парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="96c6e-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="96c6e-110">Каждый диапазон орбит парковки вызовов должен иметь глобально уникальное имя и уникальный набор расширений.</span><span class="sxs-lookup"><span data-stu-id="96c6e-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96c6e-p102">Обычно диапазон орбит содержит 100 или менее орбит. Каждый из диапазонов может быть значительно больше, максимальные значения составляют не более 10000 орбит на диапазон и менее 50000 орбит на пул. Если диапазон слишком мал, орбиты используются повторно с большей частотой.</span><span class="sxs-lookup"><span data-stu-id="96c6e-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>

<span data-ttu-id="96c6e-114">Для своих диапазонов орбит используйте блоки виртуальных добавочных номеров (которым не назначен телефон или пользователь).</span><span class="sxs-lookup"><span data-stu-id="96c6e-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

> [!NOTE]
> <span data-ttu-id="96c6e-115">Назначение номеров DID в качестве номеров орбиты в таблице орбит парковки вызовов не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="96c6e-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>

<span data-ttu-id="96c6e-116">Используйте одну из следующих процедур для создания или изменения диапазона парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="96c6e-116">Use one of the following procedures to create or modify a call park orbit range.</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="96c6e-117">Использование панели управления Skype для бизнеса Server для создания или изменения диапазона номеров для парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="96c6e-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="96c6e-118">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="96c6e-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="96c6e-119">Дополнительные сведения см. в разделе **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="96c6e-119">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="96c6e-120">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="96c6e-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="96c6e-121">В левой панели навигации выберите **Компоненты голосовой связи**, а затем щелкните **Парковка вызовов**.</span><span class="sxs-lookup"><span data-stu-id="96c6e-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4. <span data-ttu-id="96c6e-122">На странице **Парковка вызовов** выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="96c6e-122">On the **Call Park** page, do one of the following:</span></span>

   - <span data-ttu-id="96c6e-p104">Чтобы создать новый диапазон орбиты, щелкните **Создать**. В поле **Имя** введите имя, определяющее этот диапазон номеров.</span><span class="sxs-lookup"><span data-stu-id="96c6e-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>

     > [!NOTE]
     > <span data-ttu-id="96c6e-125">После фиксации диапазона орбиты в базе данных, это имя невозможно изменить.</span><span class="sxs-lookup"><span data-stu-id="96c6e-125">After you commit the orbit range to the database, you cannot change this name.</span></span>

   - <span data-ttu-id="96c6e-p105">Чтобы изменить существующий диапазон орбиты, введите все части имени диапазона орбиты в поле поиска. В списке результатов орбит щелкните нужную орбиту, щелкните **Изменить**, затем **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="96c6e-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5. <span data-ttu-id="96c6e-128">В первом поле **Диапазон номеров** введите начальный номер диапазона добавочных номеров для этой орбиты парковки вызовов, а во втором поле **Диапазон номеров** введите конечный номер диапазона.</span><span class="sxs-lookup"><span data-stu-id="96c6e-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="96c6e-129">Следует помнить:</span><span class="sxs-lookup"><span data-stu-id="96c6e-129">Be aware:</span></span>

   - <span data-ttu-id="96c6e-130">Начальный номер диапазона должен быть меньше или равен конечному номеру диапазона.</span><span class="sxs-lookup"><span data-stu-id="96c6e-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

   - <span data-ttu-id="96c6e-131">Длина значений начального и конечного номеров диапазона должна быть одинаковой.</span><span class="sxs-lookup"><span data-stu-id="96c6e-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

   - <span data-ttu-id="96c6e-p107">Диапазон орбиты должен быть уникальным и не должен перекрываться ни с одним другим диапазоном.</span><span class="sxs-lookup"><span data-stu-id="96c6e-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>

   - <span data-ttu-id="96c6e-134">Если диапазон орбит начинается с символа #, диапазон должен быть \* больше 100.</span><span class="sxs-lookup"><span data-stu-id="96c6e-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>

   - <span data-ttu-id="96c6e-135">Допустимые значения: должны соответствовать строке регулярного выражения ([ \\ \*|#]?[ 1–9]\d {0,7} )| ([1–9]\d {0,8} ).</span><span class="sxs-lookup"><span data-stu-id="96c6e-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="96c6e-136">Это означает, что значение должно быть строкой, начинаемой с символа или #, или числом от 1 до 9 (первый символ не может \* быть нулем).</span><span class="sxs-lookup"><span data-stu-id="96c6e-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="96c6e-137">Если первый символ является или #, следующий символ должен быть \* числом от 1 до 9 (не может быть нулем).</span><span class="sxs-lookup"><span data-stu-id="96c6e-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="96c6e-138">Последующие символы могут быть любым числом от 0 до 9 до семи дополнительных символов (например, "#6000", \* "92000", \* "95551212" и "915551212").</span><span class="sxs-lookup"><span data-stu-id="96c6e-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="96c6e-139">Если первый символ не является или #, первый символ должен быть числом от 1 до 9 (не может быть нулем), за которым следует до восьми символов, каждый из которых имеет значение от 0 до \* 9 (например, "915551212", "41212", "300").</span><span class="sxs-lookup"><span data-stu-id="96c6e-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

   - <span data-ttu-id="96c6e-p109">В пуле не должно быть более 50 000 орбит. Каждый диапазон орбиты обычно включает не более 100 орбит, но может быть гораздо больше, до 10 000 орбит. Например, вместо указания начального номера "7000000" и конечного номера  "8000000" рекомендуется указывать начальный номер "7000000" и конечный номер "7000100".</span><span class="sxs-lookup"><span data-stu-id="96c6e-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

6. <span data-ttu-id="96c6e-p110">В поле **Полное доменное имя сервера назначения** выберите полное доменное имя или идентификатор службы приложений, где размещается приложение парковки вызовов. Все вызовы, припаркованные по номерам в диапазоне, заданном начальным и конечным номерами диапазона орбиты, будут маршрутизироваться на этот сервер или в этот пул.</span><span class="sxs-lookup"><span data-stu-id="96c6e-p110">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application. All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7. <span data-ttu-id="96c6e-145">Нажмите кнопку **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="96c6e-145">Click **Commit**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="96c6e-146">Создание или изменение диапазона номеров для парковки вызовов с помощью skype для бизнеса Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="96c6e-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="96c6e-147">Войдите на компьютер, на котором установлена оболочка управления Skype для бизнеса Server, в качестве члена группы RTCUniversalServerAdmins или с необходимыми правами пользователя, как описано в делегирования разрешений на **установку.**</span><span class="sxs-lookup"><span data-stu-id="96c6e-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="96c6e-148">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="96c6e-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="96c6e-149">Используйте командлет **New-CsCallParkOrbit** для создания нового диапазона номеров орбиты.</span><span class="sxs-lookup"><span data-stu-id="96c6e-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="96c6e-150">Используйте командлет **Set-CsCallParkOrbit** для изменения существующего диапазона номеров орбиты.</span><span class="sxs-lookup"><span data-stu-id="96c6e-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>

    <span data-ttu-id="96c6e-151">В командной строке выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="96c6e-151">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="96c6e-152">Пример:</span><span class="sxs-lookup"><span data-stu-id="96c6e-152">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="96c6e-153">В приведенном ниже примере показано, как изменять номера в существующем диапазоне орбиты.</span><span class="sxs-lookup"><span data-stu-id="96c6e-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="96c6e-154">См. также</span><span class="sxs-lookup"><span data-stu-id="96c6e-154">See also</span></span>

[<span data-ttu-id="96c6e-155">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="96c6e-155">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="96c6e-156">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="96c6e-156">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="96c6e-157">Удаление диапазона орбит для парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="96c6e-157">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
