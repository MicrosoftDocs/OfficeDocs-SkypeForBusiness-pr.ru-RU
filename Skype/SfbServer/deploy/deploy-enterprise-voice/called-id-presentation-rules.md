---
title: Создание или изменение правила преобразования для называемое идентификатор представления в Скайп для Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Сводка: Узнайте, как определять правила преобразования с помощью построения правила преобразования в Скайп для Business Server.'
ms.openlocfilehash: 1d1d8fff6c4ab114c2c12d71ec52017d5c491bef
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886263"
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server"></a><span data-ttu-id="5f3d2-103">Создание или изменение правила преобразования для называемое идентификатор представления в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="5f3d2-103">Create or modify a translation rule for called ID presentation in Skype for Business Server</span></span>

<span data-ttu-id="5f3d2-104">**Сводка:** Узнайте, как определять правила преобразования с помощью построения правила преобразования в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server.</span></span>

<span data-ttu-id="5f3d2-105">Чтобы определить правила преобразования, введя набор значений в средстве **построения правила преобразования** и включение Скайп для панели управления Business Server для создания соответствующий шаблон поиска соответствия и правило преобразования, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="5f3d2-106">Кроме того можно регулярное выражение записи вручную, чтобы определить шаблон поиска соответствия и правило преобразования.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="5f3d2-107">Дополнительные сведения см [Создать или изменить перевода правила вручную](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span><span class="sxs-lookup"><span data-stu-id="5f3d2-107">For details, see [Create or Modify a Translation Rule Manually](https://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>

### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="5f3d2-108">Создание правила с помощью средства Build a Translation Rule (Создание правила преобразования)</span><span class="sxs-lookup"><span data-stu-id="5f3d2-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="5f3d2-109">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-109">Open Skype for Business Server Control Panel.</span></span>

2. <span data-ttu-id="5f3d2-110">Чтобы приступить к созданию правила преобразования, следуйте указаниям в [обход настройка магистрали с мультимедиа в Скайп для Business Server](configure-trunk-with-media-bypass.md) через шаг 10 или [Настройка магистрали без такого обхода в Скайп для Business Server](configure-trunk-without-media-bypass.md) по действие 9.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="5f3d2-111">На странице **Создание правила трансляции** или **Изменение правила трансляции** в поле **Имя** введите описательное имя правила преобразования.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="5f3d2-112">(Необязательно) В поле **Описание**введите описание правила преобразования, пример US International long-distance dialing.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="5f3d2-113">В разделе **Построение правила трансляции** введите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="5f3d2-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>

   - <span data-ttu-id="5f3d2-p102">**Начальные цифры**. Укажите первые цифры номеров для поиска соответствия (необязательно). Например, для поиска номеров в формате E.164, которые начинаются с символа +, введите +</span><span class="sxs-lookup"><span data-stu-id="5f3d2-p102">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match. For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>

   - <span data-ttu-id="5f3d2-116">**Продолжительность**: укажите количество цифр в сопоставлении шаблон и выберите шаблон для поиска соответствия, расположенных в этом длина именно то, по крайней мере в этом, или любой длины.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="5f3d2-117">Например, введите 11 и selectAt как минимум в раскрывающемся списке для сопоставления номеров, по крайней мере 11 цифр.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>

   - <span data-ttu-id="5f3d2-118">**Цифры для удаления**: (необязательно) укажите количество начальных цифр для удаления.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="5f3d2-119">Например, введите 1, чтобы убирается + с самого начала номера телефона.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>

   - <span data-ttu-id="5f3d2-p105">**Цифры для добавления**. Укажите цифры, добавляемые в начало преобразуемых номеров (необязательно). Например, если вы хотите, чтобы при применении правила преобразования в начало номеров добавлялись цифры 011, введите значение 011.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-p105">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers. For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>

    <span data-ttu-id="5f3d2-p106">Значения, вводимые в этих полях, отражаются в полях **Шаблон для поиска соответствия** и **Правило трансляции**. Например, если вы ввели значения, показанные в предыдущем примере, в поле **Шаблон для поиска соответствия** будет добавлено следующее регулярное выражение:</span><span class="sxs-lookup"><span data-stu-id="5f3d2-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>

    <span data-ttu-id="5f3d2-124">^\+(\d{9}\d+)$</span><span class="sxs-lookup"><span data-stu-id="5f3d2-124">^\+(\d{9}\d+)$</span></span>

    <span data-ttu-id="5f3d2-p107">Поле **Правило трансляции** задает шаблон для формата преобразованных номеров. Этот шаблон состоит из 2 частей:</span><span class="sxs-lookup"><span data-stu-id="5f3d2-p107">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>

   - <span data-ttu-id="5f3d2-127">Значение (например, $1), которое представляет число цифр в шаблоне соответствия</span><span class="sxs-lookup"><span data-stu-id="5f3d2-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>

   - <span data-ttu-id="5f3d2-128">Значение, добавляемое перед номером, которое вводится в поле **Цифры для добавления** (необязательно)</span><span class="sxs-lookup"><span data-stu-id="5f3d2-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>

    <span data-ttu-id="5f3d2-129">Для значений предыдущего примера в поле Правило трансляции будет отображаться **011$1**.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>

    <span data-ttu-id="5f3d2-130">После применения этого правила преобразования номер +441235551010 будет изменен на 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

6. <span data-ttu-id="5f3d2-131">Чтобы сохранить правило трансляции, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-131">Click **OK** to save the translation rule.</span></span>

7. <span data-ttu-id="5f3d2-132">Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-132">Click **OK** to save the trunk configuration.</span></span>

8. <span data-ttu-id="5f3d2-133">На странице **Конфигурация линии связи** нажмите **Сохранить**, затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="5f3d2-134">Всякий раз при создании или изменении правила преобразования необходимо выполнять команду **Сохранить все**, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="5f3d2-135">Дополнительные сведения см в документации по операциям [Публикация ожидающих изменений конфигурации маршрутизации голосовой связи в Скайп для бизнеса](voice-route-config-changes.md) .</span><span class="sxs-lookup"><span data-stu-id="5f3d2-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="5f3d2-136">Определение правила преобразования вручную</span><span class="sxs-lookup"><span data-stu-id="5f3d2-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="5f3d2-137">Откройте Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="5f3d2-137">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="5f3d2-138">Чтобы приступить к созданию правила преобразования, следуйте указаниям в [обход настройка магистрали с мультимедиа в Скайп для Business Server](configure-trunk-with-media-bypass.md) через шаг 10 или [Настройка магистрали без такого обхода в Скайп для Business Server](configure-trunk-without-media-bypass.md) по действие 9.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server](configure-trunk-without-media-bypass.md) through step 9.</span></span>

3. <span data-ttu-id="5f3d2-139">В поле **Имя** на странице **Создание правила трансляции** или **Изменение правила трансляции** введите имя, описывающее шаблон номера для преобразования.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

4. <span data-ttu-id="5f3d2-140">(Необязательно) В поле **Описание**введите описание этого правила преобразования, например международный звонок из США набора номера.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>

5. <span data-ttu-id="5f3d2-141">Внизу раздела **Построение правила трансляции** нажмите кнопку **Правка**.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

6. <span data-ttu-id="5f3d2-142">В разделе **Ввод регулярных выражений** введите следующие данные.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-142">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="5f3d2-143">В поле **Сопоставить этот шаблон** укажите шаблон, который будет использоваться для сопоставления номеров для преобразования.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>

   - <span data-ttu-id="5f3d2-144">В поле **Правило трансляции** укажите шаблон для формата преобразованных номеров.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>

    <span data-ttu-id="5f3d2-145">Например, если указать ^\+(\d{9}\d+)$ в **соответствие этому шаблону** and011$ 1 в поле **правило преобразования**, правило будет преобразовывать номер + 441235551010 в 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

7. <span data-ttu-id="5f3d2-146">Чтобы сохранить правило трансляции, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-146">Click **OK** to save the translation rule.</span></span>

8. <span data-ttu-id="5f3d2-147">Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-147">Click **OK** to save the trunk configuration.</span></span>

9. <span data-ttu-id="5f3d2-148">На странице **Конфигурация линии связи** нажмите **Сохранить**, затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5f3d2-149">Всякий раз при создании или изменении правила преобразования необходимо выполнять команду **Сохранить все**, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="5f3d2-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="5f3d2-150">Дополнительные сведения см в документации по операциям [Публикация ожидающих изменений конфигурации маршрутизации голосовой связи в Скайп для бизнеса](voice-route-config-changes.md) .</span><span class="sxs-lookup"><span data-stu-id="5f3d2-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

## <a name="see-also"></a><span data-ttu-id="5f3d2-151">См. также</span><span class="sxs-lookup"><span data-stu-id="5f3d2-151">See also</span></span>

[<span data-ttu-id="5f3d2-152">Настройка магистрали без обхода сервера-посредника в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="5f3d2-152">Configure a trunk with media bypass in Skype for Business Server</span></span>](configure-trunk-with-media-bypass.md)

[<span data-ttu-id="5f3d2-153">Настройка магистрали без обхода сервера-посредника в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="5f3d2-153">Configure a trunk without media bypass in Skype for Business Server</span></span>](configure-trunk-without-media-bypass.md)

[<span data-ttu-id="5f3d2-154">Публикация ожидающих изменений конфигурации маршрутизации голосовой связи в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5f3d2-154">Publish pending changes to the voice routing configuration in Skype for Business</span></span>](voice-route-config-changes.md)

[<span data-ttu-id="5f3d2-155">Развертывание сервера-посредника в Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="5f3d2-155">Deploy media bypass in Skype for Business Server</span></span>](deploy-media-bypass.md)

