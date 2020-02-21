---
title: Создание или изменение правила преобразования с помощью инструмента "Построение правила преобразования"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule by using the Build a Translation Rule tool
ms:assetid: ba112df8-3bb4-48e4-a353-4bf9110ccd71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412909(v=OCS.15)
ms:contentKeyID: 48185224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9641170534c4c4ad1ef4976d018699d01d6069a3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool-in-lync-server-2013"></a><span data-ttu-id="8a244-102">Создание или изменение правила преобразования с помощью средства "Построение правила преобразования" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a244-102">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8a244-103">_**Последнее изменение темы:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="8a244-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="8a244-104">Выполните указанные ниже действия, чтобы определить правило преобразования, введя набор значений в инструменте **Создание правила преобразования** и включите панель управления Lync Server, чтобы создать соответствующий шаблон и правило преобразования.</span><span class="sxs-lookup"><span data-stu-id="8a244-104">Follow these steps if you want to define a translation rule by entering a set of values in the **Build a Translation Rule** tool and enabling Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="8a244-105">В качестве альтернативного варианта можно задать шаблон поиска соответствия и правило преобразования вручную с помощью регулярного выражения.</span><span class="sxs-lookup"><span data-stu-id="8a244-105">Alternatively, you can a write regular expression manually to define the matching pattern and translation rule.</span></span> <span data-ttu-id="8a244-106">Дополнительные сведения см. [в статье Создание или изменение правила трансляции вручную в Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span><span class="sxs-lookup"><span data-stu-id="8a244-106">For details, see [Create or modify a translation rule manually in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-manually.md).</span></span>

<div>

## <a name="to-define-a-rule-by-using-the-build-a-translation-rule-tool"></a><span data-ttu-id="8a244-107">Создание правила с помощью средства Build a Translation Rule (Создание правила преобразования)</span><span class="sxs-lookup"><span data-stu-id="8a244-107">To define a rule by using the Build a Translation Rule tool</span></span>

1.  <span data-ttu-id="8a244-108">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8a244-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8a244-109">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8a244-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8a244-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8a244-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8a244-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8a244-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8a244-112">Чтобы приступить к определению правила преобразования, выполните действия, описанные в статье [Настройка магистрали с обходом сервера, в Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) до этапа 10 или [Настройка магистрали без обхода сервера в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) с шага 9.</span><span class="sxs-lookup"><span data-stu-id="8a244-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="8a244-113">На странице **New Translation Rule** (Создание правила преобразования) или **Edit Translation Rule** (Изменение правила преобразования) в поле **Name** (Имя) введите описательное имя правила преобразования.</span><span class="sxs-lookup"><span data-stu-id="8a244-113">Under **Name** on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="8a244-114">В поле **Description** (Описание) введите описание правила преобразования, например, **US International long-distance dialing** (Международные и междугородние звонки США) (необязательно).</span><span class="sxs-lookup"><span data-stu-id="8a244-114">(Optional) Under **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="8a244-115">В разделе **Build a Translation Rule** (Создание правила преобразования) введите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="8a244-115">In the **Build a Translation Rule** section of the dialog box, enter values in the following fields:</span></span>
    
      - <span data-ttu-id="8a244-116">**Начальные цифры**: (необязательно) укажите начальные цифры чисел, которые должны сопоставляться с шаблоном.</span><span class="sxs-lookup"><span data-stu-id="8a244-116">**Starting digits**: (Optional) Specify the leading digits of numbers you want the pattern to match.</span></span> <span data-ttu-id="8a244-117">Например, введите **+** в это поле значение, чтобы сопоставлять числа в формате E. 164 (начинающиеся с +).</span><span class="sxs-lookup"><span data-stu-id="8a244-117">For example, enter **+** in this field to match numbers in E.164 format (which begin with +).</span></span>
    
      - <span data-ttu-id="8a244-p105">**Length** (Длина). Укажите число цифр шаблона и укажите, должны ли цифры номера соответствовать всему шаблону, минимальному числу цифр шаблона или любому числу цифр шаблона. Например, введите **11** и в раскрывающемся списке выберите **At least** (Минимум) для поиска номеров, состоящих как минимум из 11 цифр.</span><span class="sxs-lookup"><span data-stu-id="8a244-p105">**Length**: Specify the number of digits in the matching pattern and select whether you want the pattern to match numbers that are this length exactly, at least this length, or any length. For example, enter **11** and select **At least** in the drop-down list to match numbers that are at least 11 digits in length.</span></span>
    
      - <span data-ttu-id="8a244-120">**Цифры для удаления**: (необязательно) укажите количество начальных цифр для удаления.</span><span class="sxs-lookup"><span data-stu-id="8a244-120">**Digits to remove**: (Optional) Specify the number of starting digits to be removed.</span></span> <span data-ttu-id="8a244-121">Например, введите **1** , чтобы удалить **+** из начала номера.</span><span class="sxs-lookup"><span data-stu-id="8a244-121">For example, enter **1** to strip out the **+** from the beginning of the number.</span></span>
    
      - <span data-ttu-id="8a244-p107">**Digits to add** (Число добавляемых цифр). Укажите цифры, добавляемые в начало преобразуемых номеров (необязательно). Например, если вы хотите, чтобы при применении правила преобразования в начало номеров добавлялись цифры 011, введите значение **011**.</span><span class="sxs-lookup"><span data-stu-id="8a244-p107">**Digits to add**: (Optional) Specify digits to be prepended to the translated numbers. For example, enter **011** if you want 011 to be prepended to the translated numbers when the rule is applied.</span></span>
    
    <span data-ttu-id="8a244-p108">Значения, вводимые в этих полях, отражаются в полях **Pattern to match** (Шаблон для поиска соответствия) и **Translation rule** (Правило преобразования). Например, если вы ввели значения, показанные в предыдущем примере, в поле **Pattern to match** (Шаблон для поиска соответствия) будет добавлено следующее регулярное выражение:</span><span class="sxs-lookup"><span data-stu-id="8a244-p108">The values you enter in these fields are reflected in the **Pattern to match** and **Translation rule** fields. For example, if you specify the preceding example values, the resulting regular expression in the **Pattern to match** field is:</span></span>
    
    <span data-ttu-id="8a244-126">**^\\+ (\\d{9}\\d) $**</span><span class="sxs-lookup"><span data-stu-id="8a244-126">**^\\+(\\d{9}\\d+)$**</span></span>
    
    <span data-ttu-id="8a244-p109">Поле **Translation rule** (Правило преобразования) задает шаблон для формата преобразованных номеров. Этот шаблон состоит из 2 частей:</span><span class="sxs-lookup"><span data-stu-id="8a244-p109">The **Translation rule** field specifies a pattern for the format of translated numbers. This pattern has two parts:</span></span>
    
      - <span data-ttu-id="8a244-129">Значение (например, **$1**), которое представляет число цифр в шаблоне соответствия</span><span class="sxs-lookup"><span data-stu-id="8a244-129">A value (for example, **$1**) that represents the number of digits in the matching pattern</span></span>
    
      - <span data-ttu-id="8a244-130">Значение, добавляемое перед номером, которое вводится в поле **Digits to add** (Число добавляемых цифр) (необязательно)</span><span class="sxs-lookup"><span data-stu-id="8a244-130">(Optional) A value that you can prepend by entering it in the **Digits to add** field</span></span>
    
    <span data-ttu-id="8a244-131">Для значений предыдущего примера в поле **Translation rule** (Правило преобразования) будет отображаться **011$1**.</span><span class="sxs-lookup"><span data-stu-id="8a244-131">Using the preceding example values, **011$1** appears in the **Translation rule** field.</span></span>
    
    <span data-ttu-id="8a244-132">После применения этого правила преобразования номер +441235551010 будет изменен на 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="8a244-132">When this translation rule is applied, +441235551010 becomes 011441235551010.</span></span>

7.  <span data-ttu-id="8a244-133">Чтобы сохранить правило преобразования, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8a244-133">Click **OK** to save the translation rule.</span></span>

8.  <span data-ttu-id="8a244-134">Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="8a244-134">Click **OK** to save the trunk configuration.</span></span>

9.  <span data-ttu-id="8a244-135">На странице **Trunk Configuration** (Конфигурация магистрали) щелкните **Commit** (Сохранить) и затем щелкните **Commit all** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="8a244-135">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="8a244-136">Всякий раз при создании или изменении правила преобразования необходимо выполнять команду <STRONG>Commit all</STRONG> (Сохранить все), чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8a244-136">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="8a244-137">Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="8a244-137">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8a244-138">См. также</span><span class="sxs-lookup"><span data-stu-id="8a244-138">See Also</span></span>


[<span data-ttu-id="8a244-139">Создание или изменение правила трансляции вручную в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a244-139">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)  
[<span data-ttu-id="8a244-140">Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a244-140">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="8a244-141">Настройка магистрали без обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a244-141">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="8a244-142">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a244-142">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="8a244-143">Глобальные параметры обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8a244-143">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

