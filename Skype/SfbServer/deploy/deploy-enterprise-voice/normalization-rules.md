---
title: Создание и изменение правила нормализации в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Сводка: сведения о том, как определять, создавать и изменять правила нормализации в Skype для бизнеса Server.'
ms.openlocfilehash: 4739bdb50e0a76c088cb6129539438c1ac6d795a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34306152"
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business"></a><span data-ttu-id="1e357-103">Создание и изменение правила нормализации в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1e357-103">Create or modify a normalization rule in Skype for Business</span></span>

<span data-ttu-id="1e357-104">**Сводка:** Сведения о том, как определить, создать и изменить правило нормализации в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1e357-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server.</span></span>

<span data-ttu-id="1e357-105">Определение, создание и изменение правил нормализации в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="1e357-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>

### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="1e357-106">Задание правила нормализации с помощью инструмента "Построение правила нормализации"</span><span class="sxs-lookup"><span data-stu-id="1e357-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="1e357-107">Открытие панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1e357-107">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="1e357-108">Необязательно Выполните действия, описанные в статье [Создание или изменение абонентской группы в Skype для бизнеса Server на](dial-plans.md) этапе 11, или [измените абонентскую группу](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) на шаге 10.</span><span class="sxs-lookup"><span data-stu-id="1e357-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md) through step 11 or [Modify a Dial Plan](https://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>

3. <span data-ttu-id="1e357-109">В окне **новое правило нормализации** или **изменить правило нормализации**введите имя, описывающее шаблон номера, который нормализован в **Name** (например, 5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="1e357-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>

4. <span data-ttu-id="1e357-110">В поле **Описание** введите описание правила нормализации (например, "Преобразование пятизначных добавочных номеров") (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="1e357-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="1e357-111">В разделе **Построение правила нормализации** введите значения в следующих полях.</span><span class="sxs-lookup"><span data-stu-id="1e357-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>

   - <span data-ttu-id="1e357-112">**Начальные цифры** Необязательно Укажите начальные цифры набранных номеров, которые должны соответствовать шаблону.</span><span class="sxs-lookup"><span data-stu-id="1e357-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="1e357-113">Например, type425, если вы хотите, чтобы шаблон соответствовал номерам, набираемым начиная с 425.</span><span class="sxs-lookup"><span data-stu-id="1e357-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>

   - <span data-ttu-id="1e357-114">**Length (длина** ) Укажите количество цифр в соответствующем шаблоне и укажите, следует ли точно соответствовать этой длине, совпадать с набранными номерами по крайней мере до этой длины или с одинаковым набором знаков.</span><span class="sxs-lookup"><span data-stu-id="1e357-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>

   - <span data-ttu-id="1e357-115">**Цифры для удаления** Необязательно Укажите количество начальных цифр, которые должны быть удалены из набранных номеров, которые должны соответствовать шаблону.</span><span class="sxs-lookup"><span data-stu-id="1e357-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>

   - <span data-ttu-id="1e357-116">**Цифры для добавления** Необязательно Укажите цифры, которые нужно добавить к номерам, которые должны быть сопоставлены с шаблоном.</span><span class="sxs-lookup"><span data-stu-id="1e357-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>

     <span data-ttu-id="1e357-117">Значения, введенные в этих полях, отражаются в полях **Шаблон для поиска соответствия** и **Правило трансляции**.</span><span class="sxs-lookup"><span data-stu-id="1e357-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="1e357-118">Например, если вы оставите \*\*\*\* пустое значение в поле " **Длина** ", type7, а затем выберете значение " **точное**" и укажите 0 в **числах для удаления**, получившееся регулярное выражение в **шаблоне** :</span><span class="sxs-lookup"><span data-stu-id="1e357-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>

     <span data-ttu-id="1e357-119">^ (\d{7}) $</span><span class="sxs-lookup"><span data-stu-id="1e357-119">^(\d{7})$</span></span>

6. <span data-ttu-id="1e357-120">В поле **Правило трансляции** укажите шаблон для формата преобразованных телефонных номеров E.164 следующим образом.</span><span class="sxs-lookup"><span data-stu-id="1e357-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>

   - <span data-ttu-id="1e357-121">Значение количества цифр, указанных в шаблоне соответствия.</span><span class="sxs-lookup"><span data-stu-id="1e357-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="1e357-122">Например, если шаблон соответствует ^ (\d{7}) $, то $1 в правиле перевода представляет номера из 7 цифр.</span><span class="sxs-lookup"><span data-stu-id="1e357-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>

   - <span data-ttu-id="1e357-123">Необязательно Введите значение в поле **цифры для добавления** , чтобы указать цифры, добавляемые к переведенному номеру (например, + 1425).</span><span class="sxs-lookup"><span data-stu-id="1e357-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>

     <span data-ttu-id="1e357-124">Например, если **в** качестве шаблона для набора номера указан параметр{7}^ (\d) $ и в **правиле перевода** содержится + 1425 $1 в качестве шаблона для номеров телефонов E. 164, правило нормализует 5550100 в + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="1e357-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="1e357-125">Если в результате применения правила нормализации получается внутренний телефонный номер организации, выберите **Внутреннее расширение** (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="1e357-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="1e357-p104">Введите номер для проверки правила нормализации, затем нажмите кнопку **Перейти** (необязательно). Результаты проверки отображаются под полем **Введите номер телефона для проверки**.</span><span class="sxs-lookup"><span data-stu-id="1e357-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1e357-p105">Можно сохранить правило нормализации, которое еще не прошло проверку, и изменить его настройки позднее. См. раздел [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span><span class="sxs-lookup"><span data-stu-id="1e357-p105">You can save a normalization rule that does not yet pass the test and then reconfigure it later. For details, see [Test Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span>

9. <span data-ttu-id="1e357-130">Нажмите кнопку **ОК** для сохранения правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="1e357-130">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="1e357-131">Нажмите кнопку **ОК** для сохранения абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="1e357-131">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="1e357-132">На странице **Абонентская группа** нажмите кнопку **Сохранить**, затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="1e357-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1e357-133">Каждый раз, когда вы создаете или изменяете правило нормализации, необходимо выполнить команду **commit all** , чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1e357-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="1e357-134">Дополнительные сведения можно найти в разделе [Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Skype для бизнеса](voice-route-config-changes.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="1e357-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>

### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="1e357-135">Определение правила нормализации вручную</span><span class="sxs-lookup"><span data-stu-id="1e357-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="1e357-136">Открытие панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="1e357-136">Open Skype for Business Server Control Panel</span></span>

2. <span data-ttu-id="1e357-137">Необязательно Следуйте указаниям, приведенным в статье [Создание или изменение абонентской группы в Skype для бизнеса Server](dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="1e357-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server](dial-plans.md).</span></span>

3. <span data-ttu-id="1e357-138">В окне **новое правило нормализации** или **изменить правило нормализации**введите имя, описывающее шаблон номера, который нормализован в **Name** (например, имя нормализации rule5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="1e357-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>

4. <span data-ttu-id="1e357-139">В поле **Описание** введите описание правила нормализации (например, "Преобразование пятизначных добавочных номеров") (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="1e357-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

5. <span data-ttu-id="1e357-140">В разделе **Построение правила нормализации** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="1e357-140">In **Build a Normalization Rule**, click **Edit**.</span></span>

6. <span data-ttu-id="1e357-141">В разделе **Введите регулярное выражение** введите следующие данные.</span><span class="sxs-lookup"><span data-stu-id="1e357-141">Enter the following in **Type a Regular Expression**:</span></span>

   - <span data-ttu-id="1e357-142">В поле **Сопоставить этот шаблон** укажите шаблон, которому должен соответствовать набираемый телефонный номер.</span><span class="sxs-lookup"><span data-stu-id="1e357-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>

   - <span data-ttu-id="1e357-143">В поле **Правило трансляции** укажите шаблон для формата преобразуемых телефонных номеров E.164.</span><span class="sxs-lookup"><span data-stu-id="1e357-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>

     <span data-ttu-id="1e357-144">Например, если ввести ^ (\d{7}) $ в соответствии с **этим шаблоном** и + 1425 $1 в **правиле перевода**, правило нормализует 5550100 в + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="1e357-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

7. <span data-ttu-id="1e357-145">Если в результате применения правила нормализации получается внутренний телефонный номер организации, выберите **Внутреннее расширение** (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="1e357-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

8. <span data-ttu-id="1e357-p107">Введите номер для проверки правила нормализации, затем нажмите кнопку **Перейти** (необязательно). Результаты проверки отображаются под полем **Введите номер телефона для проверки**.</span><span class="sxs-lookup"><span data-stu-id="1e357-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>

9. <span data-ttu-id="1e357-148">Нажмите кнопку **ОК** для сохранения правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="1e357-148">Click **OK** to save the normalization rule.</span></span>

10. <span data-ttu-id="1e357-149">Нажмите кнопку **ОК** для сохранения абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="1e357-149">Click **OK** to save the dial plan.</span></span>

11. <span data-ttu-id="1e357-150">На странице **Абонентская группа** нажмите кнопку **Сохранить**, затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="1e357-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1e357-151">Каждый раз, когда вы создаете или изменяете правило нормализации, необходимо выполнить команду **commit all** , чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="1e357-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="1e357-152">Дополнительные сведения можно найти в разделе [Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Skype для бизнеса](voice-route-config-changes.md) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="1e357-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business](voice-route-config-changes.md) in the Operations documentation.</span></span>


