---
title: Создание или изменение правила перевода для так называемой презентации ID в Skype для бизнеса Server
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
description: Сводка. Узнайте, как определить правило перевода с помощью средства Build a Translation Rule в Skype для бизнеса Server.
ms.openlocfilehash: 3f4754184e69e7b574709d0272afc9989553cfe5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103645"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="c16f1-103">Создание или изменение правила перевода для так называемой презентации ID в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c16f1-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="c16f1-104">**Сводка:** Узнайте, как определить правило перевода с помощью средства Build a Translation Rule в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="c16f1-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="c16f1-105">Следуйте этим шагам, если вы хотите определить правило перевода, введите набор значений в инструменте Build **a Translation Rule** и разрешив панели управления Skype для бизнес-серверов создать соответствующий шаблон и правило перевода для вас.</span><span class="sxs-lookup"><span data-stu-id="c16f1-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="c16f1-106">В качестве альтернативного варианта можно задать шаблон поиска соответствия и правило преобразования вручную с помощью регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="c16f1-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="c16f1-107">Дополнительные сведения см. в разделе [Create or Modify a Translation Rule Manually](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually).</span><span class="sxs-lookup"><span data-stu-id="c16f1-107">For details, see [Create or Modify a Translation Rule Manually](/previous-versions/office/lync-server-2013/lync-server-2013-create-or-modify-a-translation-rule-manually).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="c16f1-108">Создание правила с помощью средства Build a Translation Rule (Создание правила преобразования)</span><span class="sxs-lookup"><span data-stu-id="c16f1-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="c16f1-109">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="c16f1-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="c16f1-110">Чтобы приступить к определению правила перевода, выполните действия в Настройка магистрали с обходом мультимедиа в [Skype для](configure-trunk-with-media-bypass.md) бизнеса Server с помощью шага 10 или настройка магистрали без обхода мультимедиа в Skype для бизнеса [Server](configure-trunk-without-media-bypass.md) на этапе 9.</span><span class="sxs-lookup"><span data-stu-id="c16f1-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="c16f1-111">На странице **New Translation Rule** (Создание правила преобразования) или **Edit Translation Rule** (Изменение правила преобразования) в поле **Name** (Имя) введите описательное имя правила преобразования.</span><span class="sxs-lookup"><span data-stu-id="c16f1-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="c16f1-112">(Необязательный) В **описании** введите описание правила перевода, например междугородние номера US International.</span><span class="sxs-lookup"><span data-stu-id="c16f1-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="c16f1-113">В разделе **Build a Translation Rule** (Создание правила преобразования) введите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="c16f1-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="c16f1-114">**Начальные цифры.**(Необязательно) Укажите ведущие цифры чисел, которые должны соответствовать шаблону.</span><span class="sxs-lookup"><span data-stu-id="c16f1-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="c16f1-115">Например, введите + в этом поле, чтобы соответствовать номерам в формате E.164 (которые начинаются с +).</span><span class="sxs-lookup"><span data-stu-id="c16f1-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="c16f1-116">**Длина**. Укажите количество цифр в шаблоне совпадения и выберите, хотите ли вы, чтобы шаблон совпадал с числами этой длины точно, по крайней мере этой длины или любой длины.</span><span class="sxs-lookup"><span data-stu-id="c16f1-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="c16f1-117">Например, введите 11 и выберитеAt как минимум в выпадаемом списке, чтобы соответствовать номерам длиной не менее 11 цифр.</span><span class="sxs-lookup"><span data-stu-id="c16f1-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="c16f1-118">**Цифры для удаления:**(Необязательный) Укажите количество начальных цифр, которые необходимо удалить.</span><span class="sxs-lookup"><span data-stu-id="c16f1-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="c16f1-119">Например, введите 1, чтобы отострить +с начала номера.</span><span class="sxs-lookup"><span data-stu-id="c16f1-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="c16f1-120">**Цифры для добавления**: (Необязательный) Укажите цифры, которые должны быть предварительно добавлены к переведенным номерам.</span><span class="sxs-lookup"><span data-stu-id="c16f1-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="c16f1-121">Например, введите 011, если требуется, чтобы при применении правила 011 был предварительно переведен на переведенные номера.</span><span class="sxs-lookup"><span data-stu-id="c16f1-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="c16f1-p106">Значения, вводимые в этих полях, отражаются в полях **Pattern to match** (Шаблон для поиска соответствия) и **Translation rule** (Правило преобразования). Например, если вы ввели значения, показанные в предыдущем примере, в поле **Pattern to match** (Шаблон для поиска соответствия) будет добавлено следующее регулярное выражение:</span><span class="sxs-lookup"><span data-stu-id="c16f1-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="c16f1-124">^\+(\d {9} \d+)$</span><span class="sxs-lookup"><span data-stu-id="c16f1-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="c16f1-125">Поле **Translation rule** (Правило преобразования) задает шаблон для формата преобразованных номеров.</span><span class="sxs-lookup"><span data-stu-id="c16f1-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="c16f1-126">Этот шаблон состоит из 2 частей:</span><span class="sxs-lookup"><span data-stu-id="c16f1-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="c16f1-127">Значение (например, $1), которое представляет число цифр в шаблоне соответствия</span><span class="sxs-lookup"><span data-stu-id="c16f1-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="c16f1-128">Значение, добавляемое перед номером, которое вводится в поле **Digits to add** (Число добавляемых цифр) (необязательно)</span><span class="sxs-lookup"><span data-stu-id="c16f1-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="c16f1-129">Для значений предыдущего примера в поле Translation rule (Правило преобразования) будет отображаться **011$1**.</span><span class="sxs-lookup"><span data-stu-id="c16f1-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="c16f1-130">После применения этого правила преобразования номер +441235551010 будет изменен на 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="c16f1-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="c16f1-131">Чтобы сохранить правило преобразования, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c16f1-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="c16f1-132">Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c16f1-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="c16f1-133">На странице **Trunk Configuration** (Конфигурация магистрали) щелкните **Commit** (Сохранить) и затем щелкните **Commit all** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="c16f1-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="c16f1-134">Всякий раз при создании или изменении правила преобразования необходимо выполнять команду **Commit all** (Сохранить все), чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c16f1-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="c16f1-135">Подробные сведения см. в публикации Публикация изменений конфигурации маршрутирования голосовой почты в [Skype для бизнеса](voice-route-config-changes.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="c16f1-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="c16f1-136">Определение правила преобразования вручную</span><span class="sxs-lookup"><span data-stu-id="c16f1-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="c16f1-137">Откройте панель управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="c16f1-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="c16f1-138">Чтобы приступить к определению правила перевода, выполните действия в Настройка магистрали с обходом мультимедиа в [Skype для](configure-trunk-with-media-bypass.md) бизнеса Server с помощью шага 10 или настройка магистрали без обхода мультимедиа в Skype для бизнеса [Server](configure-trunk-without-media-bypass.md) на этапе 9.</span><span class="sxs-lookup"><span data-stu-id="c16f1-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="c16f1-139">В поле **Имя** на странице **Создание правила преобразования** или  **Изменение правила преобразования** введите имя, описывающее шаблон номера для преобразования.</span><span class="sxs-lookup"><span data-stu-id="c16f1-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="c16f1-140">(Необязательный) В **описании** введите описание правила перевода, например междугородний диалог us International.</span><span class="sxs-lookup"><span data-stu-id="c16f1-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="c16f1-141">Внизу раздела **Построение правила преобразования** нажмите кнопку **Правка**.</span><span class="sxs-lookup"><span data-stu-id="c16f1-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="c16f1-142">В диалоговом окне **Ввод регулярных выражений** введите следующее.</span><span class="sxs-lookup"><span data-stu-id="c16f1-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="c16f1-143">В поле **Сопоставить этот шаблон** укажите шаблон, который будет использоваться для сопоставления номеров для преобразования.</span><span class="sxs-lookup"><span data-stu-id="c16f1-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="c16f1-144">В поле **Правило преобразования** укажите шаблон для формата преобразованных номеров.</span><span class="sxs-lookup"><span data-stu-id="c16f1-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="c16f1-145">Например, если вы вводите ^ (\d\d+)$ в Соответствие этому шаблону и 011$1 в правиле перевода, правило будет переводить \+ {9} +441235551010 до 011441235551010.  </span><span class="sxs-lookup"><span data-stu-id="c16f1-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="c16f1-146">Чтобы сохранить правило преобразования, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c16f1-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="c16f1-147">Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c16f1-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="c16f1-148">На странице **Trunk Configuration** (Конфигурация магистрали) щелкните **Commit** (Сохранить) и затем щелкните **Commit all** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="c16f1-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c16f1-149">Всякий раз при создании или изменении правила преобразования необходимо выполнять команду **Commit all** (Сохранить все), чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c16f1-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="c16f1-150">Подробные сведения см. в публикации Публикация изменений конфигурации маршрутирования голосовой почты в [Skype для бизнеса](voice-route-config-changes.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="c16f1-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="c16f1-151">См. также</span><span class="sxs-lookup"><span data-stu-id="c16f1-151">See also</span></span>

[<span data-ttu-id="c16f1-152">Настройка магистрали с обходом мультимедиа в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c16f1-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="c16f1-153">Настройка магистрали без обхода мультимедиа в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c16f1-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="c16f1-154">Публикация ожидающих изменений конфигурации маршрутивки голосовой почты в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="c16f1-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="c16f1-155">Развертывание обхода мультимедиа в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c16f1-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)