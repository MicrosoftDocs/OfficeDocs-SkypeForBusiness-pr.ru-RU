---
title: Создание или изменение правила трансляции для вызываемого удостоверения презентация в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Сводка: сведения о том, как определить правило перевода с помощью инструмента "Создание правил перевода" в Skype для бизнеса Server.'
ms.openlocfilehash: 1a1f363ad157775395f77ef3e3c2915e9226bfd5
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768202"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="d4fab-103">Создание или изменение правила трансляции для вызываемого удостоверения презентация в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d4fab-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="d4fab-104">**Сводка:** Сведения о том, как определить правило перевода с помощью средства "Создание правил перевода" в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d4fab-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="d4fab-105">Выполните указанные ниже действия, чтобы определить правило перевода, введя набор значений в инструменте **Создание правил перевода** и включив на панели управления Skype для бизнеса Server для создания соответствующего шаблона сопоставления и правила трансляции.</span><span class="sxs-lookup"><span data-stu-id="d4fab-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="d4fab-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span><span class="sxs-lookup"><span data-stu-id="d4fab-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="d4fab-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span><span class="sxs-lookup"><span data-stu-id="d4fab-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="d4fab-108">Создание правила с помощью средства Build a Translation Rule (Создание правила преобразования)</span><span class="sxs-lookup"><span data-stu-id="d4fab-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="d4fab-109">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="d4fab-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="d4fab-110">Чтобы приступить к определению правила трансляции, выполните действия, описанные в статье [Настройка канала с помощью мультимедиа в Skype для бизнеса Server с](configure-trunk-with-media-bypass.md) помощью шага 10, или [Настройте магистраль без пропуска мультимедиа в Skype для бизнеса Server на](configure-trunk-without-media-bypass.md) этапе 9.</span><span class="sxs-lookup"><span data-stu-id="d4fab-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="d4fab-111">На странице **Создание правила трансляции** или **Изменение правила трансляции** в поле **Имя** введите описательное имя правила преобразования.</span><span class="sxs-lookup"><span data-stu-id="d4fab-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="d4fab-112">Необязательно В поле **Описание**введите описание правила трансляции (например, Международный набор для междугородних звонков в США).</span><span class="sxs-lookup"><span data-stu-id="d4fab-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="d4fab-113">В разделе **Построение правила трансляции** введите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="d4fab-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="d4fab-114">**Начальные цифры**: (необязательно) укажите начальные цифры чисел, которые должны соответствовать шаблону.</span><span class="sxs-lookup"><span data-stu-id="d4fab-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="d4fab-115">Например, введите в этом поле знак "+", чтобы сопоставить числа в формате E. 164 (начиная с +).</span><span class="sxs-lookup"><span data-stu-id="d4fab-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="d4fab-116">**Length (длина**): укажите количество цифр в совпадающем шаблоне и укажите, следует ли использовать шаблон для сопоставления чисел, которые имеют такую длину, хотя бы этой длины или любой длины.</span><span class="sxs-lookup"><span data-stu-id="d4fab-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="d4fab-117">Например, введите 11 и Селектат по крайней мере в раскрывающемся списке, чтобы сопоставить числа длиной не менее 11 цифр.</span><span class="sxs-lookup"><span data-stu-id="d4fab-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="d4fab-118">**Цифры для удаления**: (необязательно) укажите, сколько цифр начинается для удаления.</span><span class="sxs-lookup"><span data-stu-id="d4fab-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="d4fab-119">Например, чтобы удалить знак + с начала номера, введите 1.</span><span class="sxs-lookup"><span data-stu-id="d4fab-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="d4fab-120">**Цифры для добавления**: (необязательно) укажите цифры, которые должны начинаться с переведенных номеров.</span><span class="sxs-lookup"><span data-stu-id="d4fab-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="d4fab-121">Например, если вы хотите, чтобы при применении правила значение 011 было присутствовать в начале преобразованных номеров, введите 011.</span><span class="sxs-lookup"><span data-stu-id="d4fab-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

     <span data-ttu-id="d4fab-p106">Значения, вводимые в этих полях, отражаются в полях **Шаблон для поиска соответствия** и **Правило трансляции**. Например, если вы ввели значения, показанные в предыдущем примере, в поле **Шаблон для поиска соответствия** будет добавлено следующее регулярное выражение:</span><span class="sxs-lookup"><span data-stu-id="d4fab-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

     <span data-ttu-id="d4fab-124">^\+(\d{9}\d +) $</span><span class="sxs-lookup"><span data-stu-id="d4fab-124">^\+(\d{9}\d+)$</span></span>

     <span data-ttu-id="d4fab-125">Поле **Правило трансляции** задает шаблон для формата преобразованных номеров.</span><span class="sxs-lookup"><span data-stu-id="d4fab-125">The **Translation rule** field specifies a pattern for the format of translated numbers.</span></span> <span data-ttu-id="d4fab-126">Этот шаблон состоит из 2 частей:</span><span class="sxs-lookup"><span data-stu-id="d4fab-126">This pattern has two parts:</span></span>

   - <span data-ttu-id="d4fab-127">Значение (например, $1), которое представляет число цифр в шаблоне соответствия</span><span class="sxs-lookup"><span data-stu-id="d4fab-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="d4fab-128">Значение, добавляемое перед номером, которое вводится в поле **Цифры для добавления** (необязательно)</span><span class="sxs-lookup"><span data-stu-id="d4fab-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

     <span data-ttu-id="d4fab-129">Для значений предыдущего примера в поле Правило трансляции будет отображаться **011$1**.</span><span class="sxs-lookup"><span data-stu-id="d4fab-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

     <span data-ttu-id="d4fab-130">После применения этого правила преобразования номер +441235551010 будет изменен на 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="d4fab-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="d4fab-131">Чтобы сохранить правило трансляции, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d4fab-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="d4fab-132">Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d4fab-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="d4fab-133">На странице **Конфигурация линии связи** нажмите **Сохранить**, затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="d4fab-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d4fab-134">Всякий раз при создании или изменении правила преобразования необходимо выполнять команду **Сохранить все**, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d4fab-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="d4fab-135">Дополнительные сведения можно найти в разделе [Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Skype для бизнеса](voice-route-config-changes.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="d4fab-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="d4fab-136">Определение правила преобразования вручную</span><span class="sxs-lookup"><span data-stu-id="d4fab-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="d4fab-137">Открытие панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d4fab-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="d4fab-138">Чтобы приступить к определению правила трансляции, выполните действия, описанные в статье [Настройка канала с помощью мультимедиа в Skype для бизнеса Server с](configure-trunk-with-media-bypass.md) помощью шага 10, или [Настройте магистраль без пропуска мультимедиа в Skype для бизнеса Server на](configure-trunk-without-media-bypass.md) этапе 9.</span><span class="sxs-lookup"><span data-stu-id="d4fab-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="d4fab-139">В поле **Имя** на странице **Создание правила трансляции** или **Изменение правила трансляции** введите имя, описывающее шаблон номера для преобразования.</span><span class="sxs-lookup"><span data-stu-id="d4fab-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="d4fab-140">Необязательно В поле **Описание**введите описание правила трансляции (например, Международный набор для междугородних звонков в США).</span><span class="sxs-lookup"><span data-stu-id="d4fab-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="d4fab-141">Внизу раздела **Построение правила трансляции** нажмите кнопку **Правка**.</span><span class="sxs-lookup"><span data-stu-id="d4fab-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="d4fab-142">В разделе **Ввод регулярных выражений** введите следующие данные.</span><span class="sxs-lookup"><span data-stu-id="d4fab-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="d4fab-143">В поле **Сопоставить этот шаблон** укажите шаблон, который будет использоваться для сопоставления номеров для преобразования.</span><span class="sxs-lookup"><span data-stu-id="d4fab-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="d4fab-144">В поле **Правило трансляции** укажите шаблон для формата преобразованных номеров.</span><span class="sxs-lookup"><span data-stu-id="d4fab-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

     <span data-ttu-id="d4fab-145">Например\+, если ввести ^ (\d{9}\d +) $ в соответствии с **этим шаблоном** And011 $1 в **правиле перевода**, правило будет переведено + 441235551010 в 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="d4fab-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="d4fab-146">Чтобы сохранить правило трансляции, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d4fab-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="d4fab-147">Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d4fab-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="d4fab-148">На странице **Конфигурация линии связи** нажмите **Сохранить**, затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="d4fab-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d4fab-149">Всякий раз при создании или изменении правила преобразования необходимо выполнять команду **Сохранить все**, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="d4fab-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="d4fab-150">Дополнительные сведения можно найти в разделе [Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Skype для бизнеса](voice-route-config-changes.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="d4fab-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4fab-151">См. также</span><span class="sxs-lookup"><span data-stu-id="d4fab-151">See also</span></span>

[<span data-ttu-id="d4fab-152">Настройка канала связи с помощью мультимедиа в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d4fab-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="d4fab-153">Настройка магистрали без пропуска мультимедиа в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d4fab-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="d4fab-154">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="d4fab-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="d4fab-155">Обходной пропускной рекламы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="d4fab-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

