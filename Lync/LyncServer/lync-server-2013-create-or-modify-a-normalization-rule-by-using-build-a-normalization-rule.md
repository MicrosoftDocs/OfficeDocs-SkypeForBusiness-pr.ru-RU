---
title: Создание или изменение правила нормализации с помощью построения правила нормализации
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule by using Build a Normalization Rule
ms:assetid: e8547d7b-f74d-4a73-9a7d-df20d7a87fcd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399036(v=OCS.15)
ms:contentKeyID: 48185889
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 299d4c6d5b8a8cd53cee9fdae0a38769a535b118
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508846"
---
# <a name="create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule-in-lync-server-2013"></a><span data-ttu-id="3a599-102">Создание или изменение правила нормализации с помощью построения правила нормализации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a599-102">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a599-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3a599-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3a599-104">Выполните следующие действия, чтобы создать или изменить правило нормализации в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a599-104">Complete the following steps if you want to create or modify a normalization rule in Lync Server Control Panel.</span></span> <span data-ttu-id="3a599-105">Кроме того, если вы хотите создать или изменить правило нормализации вручную, ознакомьтесь со статьей [Создание или изменение правила нормализации вручную в Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="3a599-105">Alternatively, if you want to create or modify a normalization rule manually, see [Create or modify a normalization rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-build-a-normalization-rule"></a><span data-ttu-id="3a599-106">"Построение правила нормализации"</span><span class="sxs-lookup"><span data-stu-id="3a599-106">To define a rule by using Build a Normalization Rule</span></span>

1.  <span data-ttu-id="3a599-107">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3a599-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3a599-108">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="3a599-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3a599-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3a599-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3a599-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3a599-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3a599-111">Необязательно Выполните действия, описанные в статье [Создание абонентской группы в Lync server 2013](lync-server-2013-create-a-dial-plan.md) до этапа 11 или [Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) с шага 10.</span><span class="sxs-lookup"><span data-stu-id="3a599-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) through step 11 or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md) through step 10.</span></span>

4.  <span data-ttu-id="3a599-112">В разделе **Создание правила нормализации** или **Изменение правила нормализации** в поле **Имя** введите имя, которое описывает шаблон номера для нормализации (например, **5DigitExtension**).</span><span class="sxs-lookup"><span data-stu-id="3a599-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, **5DigitExtension**).</span></span>

5.  <span data-ttu-id="3a599-113">В поле **Описание** введите описание правила нормализации (например, "Преобразует 5-значные добавочные номера") (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="3a599-113">(Optional) In **Description**, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="3a599-114">В разделе **Построение правила нормализации** введите значения в следующих полях.</span><span class="sxs-lookup"><span data-stu-id="3a599-114">In **Build a Normalization Rule**, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="3a599-115">**Начальные цифры**     Необязательно Укажите начальные цифры набранных номеров, которые должны сопоставляться с шаблоном.</span><span class="sxs-lookup"><span data-stu-id="3a599-115">**Starting digits**   (Optional) Specify the leading digits of dialed numbers you want the pattern to match.</span></span> <span data-ttu-id="3a599-116">Например, введите **425** , если вы хотите, чтобы шаблон собирал номера с набором, начинающийся с 425.</span><span class="sxs-lookup"><span data-stu-id="3a599-116">For example, type **425** if you want the pattern to match dialed numbers beginning with 425.</span></span>
    
      - <span data-ttu-id="3a599-117">**Length (длина**     ) Укажите количество цифр в соответствующем шаблоне и укажите, будет ли шаблон соответствовать этой длине точно, совпадать с набираемыми номерами по крайней мере до этой длины или с набираемыми номерами любой длины.</span><span class="sxs-lookup"><span data-stu-id="3a599-117">**Length**   Specify the number of digits in the matching pattern and select whether you want the pattern to match this length exactly, match dialed numbers that are at least this length, or match dialed numbers of any length.</span></span>
    
      - <span data-ttu-id="3a599-118">**Цифры для удаления**     Необязательно Укажите количество начальных цифр, которые необходимо удалить из набора номеров, которые должны соответствовать шаблону.</span><span class="sxs-lookup"><span data-stu-id="3a599-118">**Digits to remove**   (Optional) Specify the number of starting digits to be removed from dialed numbers you want the pattern to match.</span></span>
    
      - <span data-ttu-id="3a599-119">**Цифры для добавления**     Необязательно Укажите цифры, которые будут добавляться к номерам, которые должны сопоставляться с шаблоном.</span><span class="sxs-lookup"><span data-stu-id="3a599-119">**Digits to add**   (Optional) Specify digits to be added to dialed numbers you want the pattern to match.</span></span>
    
    <span data-ttu-id="3a599-p105">Значения, введенные в этих полях, отражаются в **шаблоне для поиска соответствия** и в **правиле преобразования**. Например, если поле **Цифры в начале** оставлено пустым, в поле **Длина** указано **7** и выбрано **Точно**, а в поле **Цифры для удаления** указано **0**, то  в **шаблоне для поиска соответствия** появится следующее итоговое регулярное выражение:</span><span class="sxs-lookup"><span data-stu-id="3a599-p105">The values you enter in these fields are reflected in **Pattern to match** and **Translation rule**. For example, if you leave **Starting digits** empty, type **7** into the **Length** field and select **Exactly**, and specify **0** in **Digits to remove**, the resulting regular expression in the **Pattern to match** is:</span></span>
    
    <span data-ttu-id="3a599-122">**^ ( \\ d {7} ) $**</span><span class="sxs-lookup"><span data-stu-id="3a599-122">**^(\\d{7})$**</span></span>

7.  <span data-ttu-id="3a599-123">В поле **Правило преобразования** укажите шаблон для формата преобразуемых телефонных номеров E.164 следующим образом.</span><span class="sxs-lookup"><span data-stu-id="3a599-123">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers as follows:</span></span>
    
      - <span data-ttu-id="3a599-124">Значение, которое представляет количество цифр, указанных в шаблоне соответствия.</span><span class="sxs-lookup"><span data-stu-id="3a599-124">A value that represents the number of digits specified in the matching pattern.</span></span> <span data-ttu-id="3a599-125">Например, если шаблон соответствует **^ ( \\ d {7} ) $** , **$1** в правиле преобразования представляет номера набора из 7 цифр.</span><span class="sxs-lookup"><span data-stu-id="3a599-125">For example, if the matching pattern is **^(\\d{7})$** then **$1** in the translation rule represents 7-digit dialed numbers.</span></span>
    
      - <span data-ttu-id="3a599-126">Введите значение в поле **Цифры для добавления**, указывающее цифры, которые должны добавляться в начало преобразуемого номера, например, **+1425** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="3a599-126">(Optional) Type a value into the **Digits to add** field to specify digits to be prepended to the translated number (for example, **+1425**).</span></span>
    
    <span data-ttu-id="3a599-127">Например, если **шаблон для сравнения** содержит **^ ( \\ d {7} ) $** как шаблон для набранных номеров, а **правило преобразования** содержит **+ 1425 $1** в качестве шаблона для телефонных номеров E. 164, то правило нормализует 5550100 в + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="3a599-127">For example, if **Pattern to match** contains **^(\\d{7})$** as the pattern for dialed numbers and **Translation rule** contains **+1425$1** as the pattern for E.164 phone numbers, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="3a599-128">Если правило нормализации приводит к телефонному номеру, который является внутренним номером в организации, выберите **Внутренний добавочный номер** (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="3a599-128">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="3a599-p107">Введите номер для проверки правила нормализации и нажмите кнопку **Перейти** (необязательно). Результаты теста появятся под заголовком **Введите номер телефона для проверки**.</span><span class="sxs-lookup"><span data-stu-id="3a599-p107">(Optional) Enter a number to test the normalization rule, and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="3a599-131">Можно сохранить правило нормализации, которое еще не прошло проверку, а затем изменить его настройки.</span><span class="sxs-lookup"><span data-stu-id="3a599-131">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="3a599-132">Дополнительные сведения см <A href="lync-server-2013-test-voice-routing.md">в статье Проверка маршрутизации голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="3a599-132">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="3a599-133">Нажмите кнопку **ОК**, чтобы сохранить правило нормализации.</span><span class="sxs-lookup"><span data-stu-id="3a599-133">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="3a599-134">Нажмите кнопку **ОК**, чтобы сохранить абонентскую группу.</span><span class="sxs-lookup"><span data-stu-id="3a599-134">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="3a599-135">На странице **Абонентская группа**, нажмите кнопку **Зафиксировать**, а затем **Commit all** (Фиксировать все).</span><span class="sxs-lookup"><span data-stu-id="3a599-135">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="3a599-136">Каждый раз при создании или изменении правила нормализации следует запускать команду <STRONG>Сохранить все</STRONG>, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="3a599-136">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="3a599-137">Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="3a599-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3a599-138">См. также</span><span class="sxs-lookup"><span data-stu-id="3a599-138">See Also</span></span>


[<span data-ttu-id="3a599-139">Создание или изменение правила нормализации вручную в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a599-139">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)  
[<span data-ttu-id="3a599-140">Создание абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a599-140">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="3a599-141">Изменение абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a599-141">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="3a599-142">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a599-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="3a599-143">Проверка маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a599-143">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

