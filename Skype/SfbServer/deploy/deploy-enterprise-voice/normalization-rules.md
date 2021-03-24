---
title: Создание или изменение правила нормализации в Skype для бизнеса
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
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: Сводка. Узнайте, как определить, создать и изменить правило нормализации в Skype для бизнеса Server.
ms.openlocfilehash: 3550e27884d125f065c4688fec2ace797f9e8ce2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103395"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="6ed22-103">Создание или изменение правила нормализации в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="6ed22-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="6ed22-104">**Сводка:** Узнайте, как определить, создать и изменить правило нормализации в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6ed22-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="6ed22-105">Определение, создание и изменение правил нормализации в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6ed22-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="6ed22-106">Определение правила нормализации с помощью правила Сборка нормализации</span><span class="sxs-lookup"><span data-stu-id="6ed22-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="6ed22-107">Откройте панель управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="6ed22-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="6ed22-108">(Необязательный) Следуйте шагам в Создании или изменении плана набора телефонов [](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-dial-plan) в [Skype для](dial-plans.md) бизнес-сервера с помощью шага 11 или изменения плана набора через шаг 10.</span><span class="sxs-lookup"><span data-stu-id="6ed22-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](/previous-versions/office/lync-server-2013/lync-server-2013-modify-a-dial-plan) through step 10.</span></span>

3. <span data-ttu-id="6ed22-109">В **новом правиле** нормализации или правиле **изменения** нормализации введите имя, которое описывает норму числа, которая нормализуется в **Name** (например, 5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="6ed22-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="6ed22-110">В поле **Описание** введите описание правила нормализации (например, "Преобразует 5-значные добавочные номера") (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="6ed22-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="6ed22-111">В разделе **Построение правила нормализации** введите значения в следующих полях.</span><span class="sxs-lookup"><span data-stu-id="6ed22-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="6ed22-112">**Начальные цифры** (необязательный) укажите ведущие цифры набраных номеров, которые нужно соответствовать шаблону.</span><span class="sxs-lookup"><span data-stu-id="6ed22-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="6ed22-113">Например, введите 425, если вы хотите, чтобы шаблон совпадал с набраными номерами, начиная с 425.</span><span class="sxs-lookup"><span data-stu-id="6ed22-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="6ed22-114">**Длина** Укажите количество цифр в шаблоне совпадения и выберите, хотите ли вы, чтобы шаблон точно совпадал с этой длиной, совпадали с набраными номерами, которые по крайней мере этой длины, или совпадали с набраными номерами любой длины.</span><span class="sxs-lookup"><span data-stu-id="6ed22-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="6ed22-115">**Цифры для удаления** (необязательный) укажите количество начальных цифр, которые будут удалены из набраных номеров, которые необходимо использовать для совпадения шаблона.</span><span class="sxs-lookup"><span data-stu-id="6ed22-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="6ed22-116">**Цифры для добавления** (необязательных) указать цифры, которые будут добавлены в набраны номера, которые необходимо соответствовать шаблону.</span><span class="sxs-lookup"><span data-stu-id="6ed22-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

     <span data-ttu-id="6ed22-117">Значения, введенные в этих полях, отражаются в **шаблоне для поиска соответствия** и в **правиле преобразования**.</span><span class="sxs-lookup"><span data-stu-id="6ed22-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="6ed22-118">Например, если оставить  начальные цифры пустыми, введите 7 в поле Длина и выберите **Точно**, и укажите 0 в Цифры, чтобы **удалить,** в результате регулярное выражение в **шаблоне,** чтобы соответствовать: </span><span class="sxs-lookup"><span data-stu-id="6ed22-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

     <span data-ttu-id="6ed22-119">^(\d {7} )$</span><span class="sxs-lookup"><span data-stu-id="6ed22-119">^(\d{7})$</span></span>

6. <span data-ttu-id="6ed22-120">В поле **Правило преобразования** укажите шаблон для формата преобразуемых телефонных номеров E.164 следующим образом.</span><span class="sxs-lookup"><span data-stu-id="6ed22-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="6ed22-121">Значение, которое представляет количество цифр, указанных в шаблоне соответствия.</span><span class="sxs-lookup"><span data-stu-id="6ed22-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="6ed22-122">Например, если шаблон совпадения ^(\d )$, то $1 в правиле перевода представляет {7} 7-значные набраные номера.</span><span class="sxs-lookup"><span data-stu-id="6ed22-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="6ed22-123">(Необязательный) Введите значение в **цифры,** чтобы добавить поле, чтобы указать цифры, которые должны быть предварительно заранее переведены (например, +1425).</span><span class="sxs-lookup"><span data-stu-id="6ed22-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

     <span data-ttu-id="6ed22-124">Например, если  шаблон для совпадения содержит ^(\d )$ в качестве шаблона для набора номеров и правила перевода содержит +1425$1 в качестве шаблона для номеров {7} телефонов E.164, правило нормализует 5550100 до +14255550100. </span><span class="sxs-lookup"><span data-stu-id="6ed22-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="6ed22-125">Если правило нормализации приводит к телефонному номеру, который является внутренним номером в организации, выберите **Внутренний добавочный номер** (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="6ed22-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="6ed22-p104">Введите номер для проверки правила нормализации и нажмите кнопку **Перейти** (необязательно). Результаты теста появятся под заголовком **Введите номер телефона для проверки**.</span><span class="sxs-lookup"><span data-stu-id="6ed22-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ed22-128">Можно сохранить правило нормализации, которое еще не прошло проверку, а затем изменить его настройки.</span><span class="sxs-lookup"><span data-stu-id="6ed22-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="6ed22-129">Дополнительные сведения см. в статье [Test Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="6ed22-129">For details, see [Test Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing).</span></span>

9. <span data-ttu-id="6ed22-130">Нажмите кнопку **ОК**, чтобы сохранить правило нормализации.</span><span class="sxs-lookup"><span data-stu-id="6ed22-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="6ed22-131">Нажмите кнопку **ОК**, чтобы сохранить абонентскую группу.</span><span class="sxs-lookup"><span data-stu-id="6ed22-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="6ed22-132">На странице **Абонентская группа**, нажмите кнопку **Зафиксировать**, а затем **Commit all** (Фиксировать все).</span><span class="sxs-lookup"><span data-stu-id="6ed22-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ed22-133">Каждый раз при создании или изменении правила нормализации следует запускать команду **Сохранить все**, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6ed22-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="6ed22-134">Подробные сведения см. в публикации Публикация изменений конфигурации маршрутирования голосовой почты в [Skype для бизнеса](voice-route-config-changes.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="6ed22-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="6ed22-135">Определение правила нормализации вручную</span><span class="sxs-lookup"><span data-stu-id="6ed22-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="6ed22-136">Откройте панель управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="6ed22-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="6ed22-137">(Необязательный) Выполните действия в [Create or modify a dial plan in Skype for Business Server.](dial-plans.md)</span><span class="sxs-lookup"><span data-stu-id="6ed22-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="6ed22-138">В **новом правиле** нормализации или правиле изменения нормализации **введите** имя, которое описывает норму числа, нормируемую в **Name** (например, назовем правило нормализации5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="6ed22-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="6ed22-139">(Дополнительно). В поле **Описание** введите описание правила нормализации (например, "Преобразование расширений из 5 цифр").</span><span class="sxs-lookup"><span data-stu-id="6ed22-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="6ed22-140">В разделе **Build a Normalization Rule** (Создание правила нормализации) нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="6ed22-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="6ed22-141">В разделе **Type a Regular Expression** (Введите регулярное выражение) введите следующие данные.</span><span class="sxs-lookup"><span data-stu-id="6ed22-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="6ed22-142">В поле **Match this pattern** (Соответствие этому шаблону) укажите шаблон, который требуется использовать для сопоставления набираемых номеров.</span><span class="sxs-lookup"><span data-stu-id="6ed22-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="6ed22-143">В поле **Translation rule** (Правило преобразования) укажите шаблон для формата преобразуемых номеров E.164.</span><span class="sxs-lookup"><span data-stu-id="6ed22-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

     <span data-ttu-id="6ed22-144">Например, если вы вводите ^(\d )$ в соответствие этому шаблону и +1425$1 в правиле перевода, правило нормализует {7} 5550100 до +14255550100.  </span><span class="sxs-lookup"><span data-stu-id="6ed22-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="6ed22-145">(Дополнительно). Если в результате применения правила нормализации получается внутренний номер телефона организации, выберите **Internal extension** (Внутренний добавочный номер).</span><span class="sxs-lookup"><span data-stu-id="6ed22-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="6ed22-p107">(Дополнительно). Введите номер для проверки правила нормализации, а затем нажмите кнопку **Перейти**. Результаты проверки отображаются в разделе **Enter a number to test** (Введите номер телефона для проверки).</span><span class="sxs-lookup"><span data-stu-id="6ed22-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="6ed22-148">Нажмите кнопку **ОК**, чтобы сохранить правило нормализации.</span><span class="sxs-lookup"><span data-stu-id="6ed22-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="6ed22-149">Нажмите кнопку **ОК**, чтобы сохранить абонентскую группу.</span><span class="sxs-lookup"><span data-stu-id="6ed22-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="6ed22-150">На странице **Абонентская группа**, нажмите кнопку **Зафиксировать**, а затем **Commit all** (Фиксировать все).</span><span class="sxs-lookup"><span data-stu-id="6ed22-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="6ed22-151">Каждый раз при создании или изменении правила нормализации следует запускать команду **Сохранить все**, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6ed22-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="6ed22-152">Подробные сведения см. в публикации Публикация изменений конфигурации маршрутирования голосовой почты в [Skype для бизнеса](voice-route-config-changes.md) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="6ed22-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>