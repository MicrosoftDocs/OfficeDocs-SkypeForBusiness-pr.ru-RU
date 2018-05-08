---
title: Создание или изменение правила нормализации в Skype для бизнеса 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
description: 'Сводка: Узнайте, как определить, создание и изменение правила нормализации в Скайп для Business Server 2015.'
ms.openlocfilehash: 5ee0b138d118d0c437255cb3e90321019119aedf
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="create-or-modify-a-normalization-rule-in-skype-for-business-2015"></a><span data-ttu-id="9019f-103">Создание или изменение правила нормализации в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="9019f-103">Create or modify a normalization rule in Skype for Business 2015</span></span>
 
<span data-ttu-id="9019f-104">**Сводка:** Узнайте, как определить, создание и изменение правила нормализации в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="9019f-104">**Summary:** Learn how to define, create, and modify a normalization rule in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="9019f-105">Определите, создание и изменение правил нормализации в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="9019f-105">Define, create, and modify normalization rules in Skype for Business Server.</span></span>
  
### <a name="to-define-a-normalization-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="9019f-106">Задание правила нормализации с помощью инструмента "Построение правила нормализации"</span><span class="sxs-lookup"><span data-stu-id="9019f-106">To define a normalization rule by using Build a Normalization Rule</span></span>

1. <span data-ttu-id="9019f-107">Откройте Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="9019f-107">Open Skype for Business Server Control Panel</span></span>
    
2. <span data-ttu-id="9019f-108">(Необязательно) Выполните действия, описанные в [Создание и изменение абонентской группы в Скайп для Business Server 2015](dial-plans.md) через шаг 11 или [Изменить телефонной](http://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) по действие 10.</span><span class="sxs-lookup"><span data-stu-id="9019f-108">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server 2015](dial-plans.md) through step 11 or [Modify a Dial Plan](http://technet.microsoft.com/library/a91f02df-cf60-40cf-82fe-e0342c118b91.aspx) through step 10.</span></span>
    
3. <span data-ttu-id="9019f-109">**Создание правила нормализации** или **Изменение правила нормализации**введите имя, описывающее шаблон номера для нормализации в поле **имя** (например, 5DigitExtension).</span><span class="sxs-lookup"><span data-stu-id="9019f-109">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example,5DigitExtension).</span></span>
    
4. <span data-ttu-id="9019f-110">В поле **Описание** введите описание правила нормализации (например, "Преобразование пятизначных добавочных номеров") (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="9019f-110">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>
    
5. <span data-ttu-id="9019f-111">В разделе **Построение правила нормализации** введите значения в следующих полях.</span><span class="sxs-lookup"><span data-stu-id="9019f-111">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
   - <span data-ttu-id="9019f-112">**Начальных цифр** (Необязательно) Укажите начальные цифры должны сопоставляться с шаблоном для сопоставления набираемых номеров.</span><span class="sxs-lookup"><span data-stu-id="9019f-112">**Starting digits** (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="9019f-113">Например type425 Если вы хотите, чтобы шаблон для поиска соответствия набора номера, начинающиеся с 425.</span><span class="sxs-lookup"><span data-stu-id="9019f-113">For example, type425 if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
   - <span data-ttu-id="9019f-114">**Длина** Укажите количество цифр в шаблоне соответствия и выберите должны сопоставляться с шаблоном на точное соответствие длину, совпадение набираемым номерам, которые по крайней мере длину или совпадение набираемым номерам, любой длины.</span><span class="sxs-lookup"><span data-stu-id="9019f-114">**Length** Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
   - <span data-ttu-id="9019f-115">**Цифры для удаления** (Необязательно) Укажите количество начальных цифр для удаления из набираемых номеров, которые должны сопоставляться с шаблоном в соответствии с.</span><span class="sxs-lookup"><span data-stu-id="9019f-115">**Digits to remove** (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
   - <span data-ttu-id="9019f-116">**Цифры для добавления** (Необязательно) Укажите количество цифр для добавления к набираемых номеров, требуется шаблон для поиска соответствия.</span><span class="sxs-lookup"><span data-stu-id="9019f-116">**Digits to add** (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="9019f-117">Значения, введенные в этих полях, отражаются в полях **Шаблон для поиска соответствия** и **Правило трансляции**.</span><span class="sxs-lookup"><span data-stu-id="9019f-117">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**.</span></span> <span data-ttu-id="9019f-118">Например если оставить пустым, type7 **начала цифр** в поле **Длина** и выберите **точно**и укажите 0 в **цифры для удаления**результате регулярное выражение в **шаблон для поиска соответствия** — это:</span><span class="sxs-lookup"><span data-stu-id="9019f-118">For example, if you leave **Starting digits** empty, type7 into the **Length** field and select **Exactly**, and specify 0 in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="9019f-119">^(\d{7})$</span><span class="sxs-lookup"><span data-stu-id="9019f-119">^(\d{7})$</span></span>
    
6. <span data-ttu-id="9019f-120">В поле **Правило трансляции** укажите шаблон для формата преобразованных телефонных номеров E.164 следующим образом.</span><span class="sxs-lookup"><span data-stu-id="9019f-120">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
   - <span data-ttu-id="9019f-121">Значение количества цифр, указанных в шаблоне соответствия.</span><span class="sxs-lookup"><span data-stu-id="9019f-121">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="9019f-122">Например, если шаблон поиска соответствия ^(\d{7})$, а затем $1 в перевода правила представляет 7-значных набираемых номеров.</span><span class="sxs-lookup"><span data-stu-id="9019f-122">For example, if the matching pattern is ^(\d{7})$ then$1 in the translation rule represents 7-digit dialed numbers.</span></span>
    
   - <span data-ttu-id="9019f-123">(Необязательно) Введите значение в поле **цифры для добавления** , указывающее цифры, которые должны добавляться в начало преобразуемого номер (например, + 1425).</span><span class="sxs-lookup"><span data-stu-id="9019f-123">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example,+1425).</span></span>
    
    <span data-ttu-id="9019f-124">Например, если **шаблон для поиска соответствия** содержит ^(\d{7})$ как шаблон для набора номера и содержит **правила преобразования** + 1425$ 1 как шаблон для формата E.164 номера телефонов, правило будет выполнять нормализацию номера 5550100 до + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="9019f-124">For example, if **Pattern to match** contains^(\d{7})$ as the pattern for dialed numbers and **Translation rule** contains+1425$1 as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>
    
7. <span data-ttu-id="9019f-125">Если в результате применения правила нормализации получается внутренний телефонный номер организации, выберите **Внутреннее расширение** (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="9019f-125">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>
    
8. <span data-ttu-id="9019f-p104">Введите номер для проверки правила нормализации, затем нажмите кнопку **Перейти** (необязательно). Результаты проверки отображаются под полем **Введите номер телефона для проверки**.</span><span class="sxs-lookup"><span data-stu-id="9019f-p104">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9019f-128">Можно сохранить правило нормализации, который еще не прошел проверку и настроить его более поздняя версия.</span><span class="sxs-lookup"><span data-stu-id="9019f-128">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="9019f-129">Дополнительные сведения см [Тестирование маршрутизации голосовой связи](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span><span class="sxs-lookup"><span data-stu-id="9019f-129">For details, see [Test Voice Routing](http://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).</span></span> 
  
9. <span data-ttu-id="9019f-130">Нажмите кнопку **ОК** для сохранения правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="9019f-130">Click **OK** to save the normalization rule.</span></span>
    
10. <span data-ttu-id="9019f-131">Нажмите кнопку **ОК** для сохранения абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="9019f-131">Click **OK** to save the dial plan.</span></span>
    
11. <span data-ttu-id="9019f-132">На странице **Абонентская группа** нажмите кнопку **Сохранить**, затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="9019f-132">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="9019f-133">При создании или изменение правила нормализации, необходимо выполнить команду **Сохранить все** публикация изменений конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9019f-133">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="9019f-134">Дополнительные сведения см в документации по операциям [Публикация ожидающих изменений конфигурации маршрутизации голосовой связи в Скайп для 2015 бизнеса](voice-route-config-changes.md) .</span><span class="sxs-lookup"><span data-stu-id="9019f-134">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  
### <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="9019f-135">Определение правила нормализации вручную</span><span class="sxs-lookup"><span data-stu-id="9019f-135">To define a normalization rule manually</span></span>

1. <span data-ttu-id="9019f-136">Откройте Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="9019f-136">Open Skype for Business Server Control Panel</span></span>
    
2. <span data-ttu-id="9019f-137">(Необязательно) Выполните действия, описанные в [Создание и изменение абонентской группы в Скайп для Business Server 2015](dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="9019f-137">(Optional) Follow the steps in [Create or modify a dial plan in Skype for Business Server 2015](dial-plans.md).</span></span> 
    
3. <span data-ttu-id="9019f-138">**Создание правила нормализации** или **Изменение правила нормализации**введите имя, описывающее шаблон номера для нормализации (например, имя rule5DigitExtension нормализации) в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="9019f-138">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule5DigitExtension).</span></span>
    
4. <span data-ttu-id="9019f-139">В поле **Описание** введите описание правила нормализации (например, "Преобразование пятизначных добавочных номеров") (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="9019f-139">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>
    
5. <span data-ttu-id="9019f-140">В разделе **Построение правила нормализации** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="9019f-140">In **Build a Normalization Rule**, click **Edit**.</span></span>
    
6. <span data-ttu-id="9019f-141">В разделе **Введите регулярное выражение** введите следующие данные.</span><span class="sxs-lookup"><span data-stu-id="9019f-141">Enter the following in **Type a Regular Expression**:</span></span>
    
   - <span data-ttu-id="9019f-142">В поле **Сопоставить этот шаблон** укажите шаблон, которому должен соответствовать набираемый телефонный номер.</span><span class="sxs-lookup"><span data-stu-id="9019f-142">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>
    
   - <span data-ttu-id="9019f-143">В поле **Правило трансляции** укажите шаблон для формата преобразуемых телефонных номеров E.164.</span><span class="sxs-lookup"><span data-stu-id="9019f-143">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>
    
    <span data-ttu-id="9019f-144">Например, если вводится ^(\d{7})$ в **соответствие этому шаблону** и + 1425$ 1 в поле **правило преобразования**, правило будет выполнять нормализацию номера 5550100 до + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="9019f-144">For example, if you enter ^(\d{7})$ in **Match this pattern** and+1425$1 in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>
    
7. <span data-ttu-id="9019f-145">Если в результате применения правила нормализации получается внутренний телефонный номер организации, выберите **Внутреннее расширение** (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="9019f-145">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>
    
8. <span data-ttu-id="9019f-p107">Введите номер для проверки правила нормализации, затем нажмите кнопку **Перейти** (необязательно). Результаты проверки отображаются под полем **Введите номер телефона для проверки**.</span><span class="sxs-lookup"><span data-stu-id="9019f-p107">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
9. <span data-ttu-id="9019f-148">Нажмите кнопку **ОК** для сохранения правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="9019f-148">Click **OK** to save the normalization rule.</span></span>
    
10. <span data-ttu-id="9019f-149">Нажмите кнопку **ОК** для сохранения абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="9019f-149">Click **OK** to save the dial plan.</span></span>
    
11. <span data-ttu-id="9019f-150">На странице **Абонентская группа** нажмите кнопку **Сохранить**, затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="9019f-150">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="9019f-151">При создании или изменение правила нормализации, необходимо выполнить команду **Сохранить все** публикация изменений конфигурации.</span><span class="sxs-lookup"><span data-stu-id="9019f-151">Whenever you create or change a normalization rule, you must run the **Commit all** command to publish the configuration change.</span></span> <span data-ttu-id="9019f-152">Дополнительные сведения см в документации по операциям [Публикация ожидающих изменений конфигурации маршрутизации голосовой связи в Скайп для 2015 бизнеса](voice-route-config-changes.md) .</span><span class="sxs-lookup"><span data-stu-id="9019f-152">For details, see [Publish pending changes to the voice routing configuration in Skype for Business 2015](voice-route-config-changes.md) in the Operations documentation.</span></span>
  

