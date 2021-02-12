---
title: Create or modify a translation rule for called ID presentation in Skype for Business Server
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
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: Сводка. Узнайте, как определить правило трансляции с помощью средства создания правила трансляции в Skype для бизнеса Server.
ms.openlocfilehash: b93d271abd0ade1b178e859f2a0599464a6759e5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804199"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="1049a-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1049a-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="1049a-104">**Сводка:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1049a-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="1049a-105">Выполните следующие действия, чтобы определить правило трансляции, введите  набор значений в средстве создания правила трансляции и включив панель управления Skype для бизнеса Server для создания соответствующего шаблона и правила трансляции.</span><span class="sxs-lookup"><span data-stu-id="1049a-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="1049a-106">В качестве альтернативного варианта можно задать шаблон поиска соответствия и правило преобразования вручную с помощью регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="1049a-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="1049a-107">Дополнительные сведения см. в разделе [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span><span class="sxs-lookup"><span data-stu-id="1049a-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="1049a-108">Создание правила с помощью средства Build a Translation Rule (Создание правила преобразования)</span><span class="sxs-lookup"><span data-stu-id="1049a-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="1049a-109">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1049a-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="1049a-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span><span class="sxs-lookup"><span data-stu-id="1049a-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="1049a-111">На странице **New Translation Rule** (Создание правила преобразования) или **Edit Translation Rule** (Изменение правила преобразования) в поле **Name** (Имя) введите описательное имя правила преобразования.</span><span class="sxs-lookup"><span data-stu-id="1049a-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="1049a-112">(Необязательно) В **описании** введите описание правила трансляции, например международного телефонного набора (US International).</span><span class="sxs-lookup"><span data-stu-id="1049a-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="1049a-113">В разделе **Build a Translation Rule** (Создание правила преобразования) введите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="1049a-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="1049a-114">**Начальные цифры:**(Необязательно) Укажите начальные цифры чисел, которые должны соответствовать шаблону.</span><span class="sxs-lookup"><span data-stu-id="1049a-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="1049a-115">Например, введите +в это поле для совпадения чисел в формате E.164 (которые начинаются с +).</span><span class="sxs-lookup"><span data-stu-id="1049a-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="1049a-116">**Длина:** укажите количество цифр в шаблоне совпадения и укажите, должен ли шаблон точно соответствовать номерам этой длины, по крайней мере этой длины или любой длины.</span><span class="sxs-lookup"><span data-stu-id="1049a-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="1049a-117">Например, введите 11 и selectAt least в выпадаемом списке для совпадения номеров длиной не менее 11 цифр.</span><span class="sxs-lookup"><span data-stu-id="1049a-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="1049a-118">**Цифры, которые необходимо** удалить: (необязательно) Укажите количество начальных цифр, которые необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="1049a-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="1049a-119">Например, введите 1, чтобы вывести +из начала номера.</span><span class="sxs-lookup"><span data-stu-id="1049a-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="1049a-120">**Цифры для добавления:**(Необязательно) Укажите цифры, которые необходимо добавить в преобразуемую цифру.</span><span class="sxs-lookup"><span data-stu-id="1049a-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="1049a-121">Например, введите 011, если вы хотите, чтобы при применении правила к переведенным номерам был приложен номер 011.</span><span class="sxs-lookup"><span data-stu-id="1049a-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="1049a-p106">Значения, вводимые в этих полях, отражаются в полях **Pattern to match** (Шаблон для поиска соответствия) и **Translation rule** (Правило преобразования). Например, если вы ввели значения, показанные в предыдущем примере, в поле **Pattern to match** (Шаблон для поиска соответствия) будет добавлено следующее регулярное выражение:</span><span class="sxs-lookup"><span data-stu-id="1049a-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="1049a-124">^\+(\d {9} \d+)$</span><span class="sxs-lookup"><span data-stu-id="1049a-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="1049a-125">Поле **Translation rule** (Правило преобразования) задает шаблон для формата преобразованных номеров.</span><span class="sxs-lookup"><span data-stu-id="1049a-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="1049a-126">Этот шаблон состоит из 2 частей:</span><span class="sxs-lookup"><span data-stu-id="1049a-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="1049a-127">Значение (например, $1), которое представляет число цифр в шаблоне соответствия</span><span class="sxs-lookup"><span data-stu-id="1049a-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="1049a-128">Значение, добавляемое перед номером, которое вводится в поле **Digits to add** (Число добавляемых цифр) (необязательно)</span><span class="sxs-lookup"><span data-stu-id="1049a-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="1049a-129">Для значений предыдущего примера в поле Translation rule (Правило преобразования) будет отображаться **011$1**.</span><span class="sxs-lookup"><span data-stu-id="1049a-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="1049a-130">После применения этого правила преобразования номер +441235551010 будет изменен на 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="1049a-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="1049a-131">Чтобы сохранить правило преобразования, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1049a-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="1049a-132">Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1049a-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="1049a-133">На странице **Trunk Configuration** (Конфигурация магистрали) щелкните **Commit** (Сохранить) и затем щелкните **Commit all** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="1049a-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1049a-134">Всякий раз при создании или изменении правила преобразования необходимо выполнять команду **Commit all** (Сохранить все), чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1049a-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="1049a-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="1049a-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="1049a-136">Определение правила преобразования вручную</span><span class="sxs-lookup"><span data-stu-id="1049a-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="1049a-137">Открытие панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1049a-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="1049a-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span><span class="sxs-lookup"><span data-stu-id="1049a-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="1049a-139">В поле **Имя** на странице **Создание правила преобразования** или  **Изменение правила преобразования** введите имя, описывающее шаблон номера для преобразования.</span><span class="sxs-lookup"><span data-stu-id="1049a-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="1049a-140">(Необязательно) В **описании** введите описание правила трансляции, например для международного телефонного набора (US International).</span><span class="sxs-lookup"><span data-stu-id="1049a-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="1049a-141">Внизу раздела **Построение правила преобразования** нажмите кнопку **Правка**.</span><span class="sxs-lookup"><span data-stu-id="1049a-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="1049a-142">В диалоговом окне **Ввод регулярных выражений** введите следующее.</span><span class="sxs-lookup"><span data-stu-id="1049a-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="1049a-143">В поле **Сопоставить этот шаблон** укажите шаблон, который будет использоваться для сопоставления номеров для преобразования.</span><span class="sxs-lookup"><span data-stu-id="1049a-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="1049a-144">В поле **Правило преобразования** укажите шаблон для формата преобразованных номеров.</span><span class="sxs-lookup"><span data-stu-id="1049a-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="1049a-145">Например, если ввести ^ (\d \d+)$ в соответствие этому шаблону и 011$1 в правиле трансляции, правило переведет \+ {9} +441235551010 в 011441235551010.  </span><span class="sxs-lookup"><span data-stu-id="1049a-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="1049a-146">Чтобы сохранить правило преобразования, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1049a-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="1049a-147">Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1049a-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="1049a-148">На странице **Trunk Configuration** (Конфигурация магистрали) щелкните **Commit** (Сохранить) и затем щелкните **Commit all** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="1049a-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1049a-149">Всякий раз при создании или изменении правила преобразования необходимо выполнять команду **Commit all** (Сохранить все), чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1049a-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="1049a-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span><span class="sxs-lookup"><span data-stu-id="1049a-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="1049a-151">См. также</span><span class="sxs-lookup"><span data-stu-id="1049a-151">See also</span></span>

[<span data-ttu-id="1049a-152">Настройка магистрали с обходом сервера-посредника в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1049a-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="1049a-153">Настройка магистрали без обхода сервера-посредника в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1049a-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="1049a-154">Публикация ожидающих изменений в конфигурации маршрутации голосовой почты в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1049a-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="1049a-155">Развертывание обхода сервера-посредника в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1049a-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

