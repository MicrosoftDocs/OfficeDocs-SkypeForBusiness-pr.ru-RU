---
title: Создание или изменение правила трансляции для представления кода вызываемого абонента в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
description: 'Сводка: Узнайте, как определять правила преобразования с помощью построения правила преобразования в Скайп для Business Server 2015.'
ms.openlocfilehash: aa433375ad4dfa2dcc0c141d36b6d51ae28647f1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-translation-rule-for-called-id-presentation-in-skype-for-business-server-2015"></a><span data-ttu-id="903ab-103">Создание или изменение правила трансляции для представления кода вызываемого абонента в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="903ab-103">Create or modify a translation rule for called ID presentation in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="903ab-104">**Сводка:** Узнайте, как определять правила преобразования с помощью построения правила преобразования в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="903ab-104">**Summary:** Learn how to define a translation rule by using the Build a Translation Rule tool in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="903ab-105">Чтобы определить правила преобразования, введя набор значений в средстве **построения правила преобразования** и включение Скайп для панели управления Business Server для создания соответствующий шаблон поиска соответствия и правило преобразования, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="903ab-105">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Skype for Business Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="903ab-106">Кроме того можно регулярное выражение записи вручную, чтобы определить шаблон поиска соответствия и правило преобразования.</span><span class="sxs-lookup"><span data-stu-id="903ab-106">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="903ab-107">Дополнительные сведения см [Создать или изменить перевода правила вручную](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span><span class="sxs-lookup"><span data-stu-id="903ab-107">For details, see [Create or Modify a Translation Rule Manually](http://technet.microsoft.com/library/049d1db3-af58-48c5-be89-52e1d068a4bd.aspx).</span></span>
  
### <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="903ab-108">Создание правила с помощью средства Build a Translation Rule (Создание правила преобразования)</span><span class="sxs-lookup"><span data-stu-id="903ab-108">To define a rule by using the Build a Translation Rule tool</span></span>

1. <span data-ttu-id="903ab-109">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="903ab-109">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="903ab-110">Чтобы приступить к созданию правила преобразования, следуйте указаниям в [обход настройка магистрали с мультимедиа в Скайп для Business Server 2015](configure-trunk-with-media-bypass.md) через шаг 10 или [Настройка магистрали без такого обхода в Скайп для Business Server 2015](configure-trunk-without-media-bypass.md) по действие 9.</span><span class="sxs-lookup"><span data-stu-id="903ab-110">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server 2015](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server 2015](configure-trunk-without-media-bypass.md) through step 9.</span></span>
    
3. <span data-ttu-id="903ab-111">На странице **Создание правила трансляции** или **Изменение правила трансляции** в поле **Имя** введите описательное имя правила преобразования.</span><span class="sxs-lookup"><span data-stu-id="903ab-111">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>
    
4. <span data-ttu-id="903ab-112">(Необязательно) В поле **Описание**введите описание правила преобразования, пример US International long-distance dialing.</span><span class="sxs-lookup"><span data-stu-id="903ab-112">(Optional) Under **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>
    
5. <span data-ttu-id="903ab-113">В разделе **Построение правила трансляции** введите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="903ab-113">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
   - <span data-ttu-id="903ab-114">**Начальных цифр**: (необязательно) укажите начальные цифры номерам, которые должны сопоставляться с шаблоном в соответствии с.</span><span class="sxs-lookup"><span data-stu-id="903ab-114">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="903ab-115">Например, введите + в это поле для сопоставления номеров E.164 в формате (которой начинаются с +).</span><span class="sxs-lookup"><span data-stu-id="903ab-115">For example, enter + in this field to match numbers in E.164 format (which begin with +).</span></span>
    
   - <span data-ttu-id="903ab-116">**Продолжительность**: укажите количество цифр в сопоставлении шаблон и выберите шаблон для поиска соответствия, расположенных в этом длина именно то, по крайней мере в этом, или любой длины.</span><span class="sxs-lookup"><span data-stu-id="903ab-116">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length.</span></span> <span data-ttu-id="903ab-117">Например, введите 11 и selectAt как минимум в раскрывающемся списке для сопоставления номеров, по крайней мере 11 цифр.</span><span class="sxs-lookup"><span data-stu-id="903ab-117">For example, enter 11 and selectAt least in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
   - <span data-ttu-id="903ab-118">**Цифры для удаления**: (необязательно) укажите количество начальных цифр для удаления.</span><span class="sxs-lookup"><span data-stu-id="903ab-118">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="903ab-119">Например, введите 1, чтобы убирается + с самого начала номера телефона.</span><span class="sxs-lookup"><span data-stu-id="903ab-119">For example, enter 1 to strip out the+ from the beginning of the number.</span></span>
    
   - <span data-ttu-id="903ab-120">**Цифры для добавления**: (необязательно) укажите количество цифр, которые должны добавляться в начало для преобразованных номеров.</span><span class="sxs-lookup"><span data-stu-id="903ab-120">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers.</span></span> <span data-ttu-id="903ab-121">Например введите 011, если требуется 011 для должны добавляться в начало преобразуемого номера при применении правила.</span><span class="sxs-lookup"><span data-stu-id="903ab-121">For example, enter 011 if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="903ab-p106">Значения, вводимые в этих полях, отражаются в полях **Шаблон для поиска соответствия** и **Правило трансляции**. Например, если вы ввели значения, показанные в предыдущем примере, в поле **Шаблон для поиска соответствия** будет добавлено следующее регулярное выражение:</span><span class="sxs-lookup"><span data-stu-id="903ab-p106">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="903ab-124">^\+(\d{9}\d+)$</span><span class="sxs-lookup"><span data-stu-id="903ab-124">^\+(\d{9}\d+)$</span></span>
    
    <span data-ttu-id="903ab-p107">Поле **Правило трансляции** задает шаблон для формата преобразованных номеров. Этот шаблон состоит из 2 частей:</span><span class="sxs-lookup"><span data-stu-id="903ab-p107">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
   - <span data-ttu-id="903ab-127">Значение (например, $1), которое представляет число цифр в шаблоне соответствия</span><span class="sxs-lookup"><span data-stu-id="903ab-127">A value (for example, $1) that represents the number of digits in the matching pattern</span></span>
    
   - <span data-ttu-id="903ab-128">Значение, добавляемое перед номером, которое вводится в поле **Цифры для добавления** (необязательно)</span><span class="sxs-lookup"><span data-stu-id="903ab-128">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="903ab-129">С помощью описанных выше примере значений 011$ 1 появляется в поле **правило преобразования** .</span><span class="sxs-lookup"><span data-stu-id="903ab-129">Using the preceding example values, 011$1 appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="903ab-130">После применения этого правила преобразования номер +441235551010 будет изменен на 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="903ab-130">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>
    
6. <span data-ttu-id="903ab-131">Чтобы сохранить правило трансляции, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="903ab-131">Click **OK** to save the translation rule.</span></span>
    
7. <span data-ttu-id="903ab-132">Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="903ab-132">Click **OK** to save the trunk configuration.</span></span>
    
8. <span data-ttu-id="903ab-133">На странице **Конфигурация линии связи** нажмите **Сохранить**, затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="903ab-133">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span> 
    
   > [!NOTE]
   > <span data-ttu-id="903ab-134">Всякий раз при создании или изменении правила преобразования необходимо выполнять команду **Сохранить все**, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="903ab-134">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="903ab-135">Дополнительные сведения см в документации по операциям [Публикация ожидающих изменений конфигурации маршрутизации голосовой связи в Скайп для 2015 бизнеса](voice-route-config-changes.md) .</span><span class="sxs-lookup"><span data-stu-id="903ab-135">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
### <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="903ab-136">Определение правила преобразования вручную</span><span class="sxs-lookup"><span data-stu-id="903ab-136">To define a translation rule manually</span></span>

1. <span data-ttu-id="903ab-137">Откройте Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="903ab-137">Open Skype for Business Server Control Panel</span></span>
    
2. <span data-ttu-id="903ab-138">Чтобы приступить к созданию правила преобразования, следуйте указаниям в [обход настройка магистрали с мультимедиа в Скайп для Business Server 2015](configure-trunk-with-media-bypass.md) через шаг 10 или [Настройка магистрали без такого обхода в Скайп для Business Server 2015](configure-trunk-without-media-bypass.md) по действие 9.</span><span class="sxs-lookup"><span data-stu-id="903ab-138">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Skype for Business Server 2015](configure-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Skype for Business Server 2015](configure-trunk-without-media-bypass.md) through step 9.</span></span>
    
3. <span data-ttu-id="903ab-139">В поле **Имя** на странице **Создание правила трансляции** или **Изменение правила трансляции** введите имя, описывающее шаблон номера для преобразования.</span><span class="sxs-lookup"><span data-stu-id="903ab-139">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>
    
4. <span data-ttu-id="903ab-140">(Необязательно) В поле **Описание**введите описание этого правила преобразования, например международный звонок из США набора номера.</span><span class="sxs-lookup"><span data-stu-id="903ab-140">(Optional) In **Description**, type a description of the translation rule, for example US International long-distance dialing.</span></span>
    
5. <span data-ttu-id="903ab-141">Внизу раздела **Построение правила трансляции** нажмите кнопку **Правка**.</span><span class="sxs-lookup"><span data-stu-id="903ab-141">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>
    
6. <span data-ttu-id="903ab-142">В разделе **Ввод регулярных выражений** введите следующие данные.</span><span class="sxs-lookup"><span data-stu-id="903ab-142">Enter the following in **Type a Regular Expression**:</span></span>
    
   - <span data-ttu-id="903ab-143">В поле **Сопоставить этот шаблон** укажите шаблон, который будет использоваться для сопоставления номеров для преобразования.</span><span class="sxs-lookup"><span data-stu-id="903ab-143">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
   - <span data-ttu-id="903ab-144">В поле **Правило трансляции** укажите шаблон для формата преобразованных номеров.</span><span class="sxs-lookup"><span data-stu-id="903ab-144">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="903ab-145">Например, если указать ^\+(\d{9}\d+)$ в **соответствие этому шаблону** and011$ 1 в поле **правило преобразования**, правило будет преобразовывать номер + 441235551010 в 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="903ab-145">For example, if you enter ^\+(\d{9}\d+)$ in **Match this pattern** and011$1 in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>
    
7. <span data-ttu-id="903ab-146">Чтобы сохранить правило трансляции, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="903ab-146">Click **OK** to save the translation rule.</span></span>
    
8. <span data-ttu-id="903ab-147">Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="903ab-147">Click **OK** to save the trunk configuration.</span></span>
    
9. <span data-ttu-id="903ab-148">На странице **Конфигурация линии связи** нажмите **Сохранить**, затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="903ab-148">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="903ab-149">Всякий раз при создании или изменении правила преобразования необходимо выполнять команду **Сохранить все**, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="903ab-149">Whenever you create or modify a translation rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="903ab-150">Дополнительные сведения см в документации по операциям [Публикация ожидающих изменений конфигурации маршрутизации голосовой связи в Скайп для 2015 бизнеса](voice-route-config-changes.md) .</span><span class="sxs-lookup"><span data-stu-id="903ab-150">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="903ab-151">См. также</span><span class="sxs-lookup"><span data-stu-id="903ab-151">See also</span></span>

#### 

[<span data-ttu-id="903ab-152">Настройка магистрали без обхода сервера-посредника в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="903ab-152">Configure a trunk with media bypass in Skype for Business Server 2015</span></span>](configure-trunk-with-media-bypass.md)
  
[<span data-ttu-id="903ab-153">Настройка магистрали без обхода сервера-посредника в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="903ab-153">Configure a trunk without media bypass in Skype for Business Server 2015</span></span>](configure-trunk-without-media-bypass.md)
  
[<span data-ttu-id="903ab-154">Публикация ожидающих изменений конфигурации маршрутизации голосовой связи в Скайп для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="903ab-154">Publish pending changes to the voice routing configuration in Skype for Business 2015</span></span>](voice-route-config-changes.md)
#### 

[<span data-ttu-id="903ab-155">Развертывание сервера-посредника в Скайп for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="903ab-155">Deploy media bypass in Skype for Business Server 2015</span></span>](deploy-media-bypass.md)

