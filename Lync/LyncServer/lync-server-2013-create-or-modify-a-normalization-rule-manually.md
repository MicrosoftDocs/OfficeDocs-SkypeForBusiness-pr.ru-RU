---
title: 'Lync Server 2013: создание или изменение правила нормализации вручную'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a normalization rule manually
ms:assetid: fc0335e6-8830-4cfb-8c64-6aeb98c0a992
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413074(v=OCS.15)
ms:contentKeyID: 48185943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cf7693eb4a8bac814c81ef69b9f158edb3684f3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722420"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-normalization-rule-manually-in-lync-server-2013"></a><span data-ttu-id="8e293-102">Создание или изменение правила нормализации вручную в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e293-102">Create or modify a normalization rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8e293-103">_**Тема последнего изменения:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="8e293-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="8e293-104">Если вы хотите создать или изменить правило нормализации вручную, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="8e293-104">Complete the following steps if you want to create or modify a normalization rule manually.</span></span> <span data-ttu-id="8e293-105">Если вы хотите создать или изменить правило нормализации с помощью построения правила нормализации на панели управления Lync Server, ознакомьтесь со сведениями [Создание и изменение правила нормализации в Lync server 2013 с помощью сборки](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="8e293-105">If you want to create or modify a normalization rule by using Build a Normalization Rule in Lync Server Control Panel, see [Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md).</span></span>

<div>

## <a name="to-define-a-normalization-rule-manually"></a><span data-ttu-id="8e293-106">Определение правила нормализации вручную</span><span class="sxs-lookup"><span data-stu-id="8e293-106">To define a normalization rule manually</span></span>

1.  <span data-ttu-id="8e293-107">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8e293-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="8e293-108">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="8e293-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="8e293-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8e293-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8e293-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8e293-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="8e293-111">Необязательно Выполните действия, описанные в статье [Создание абонентской группы в Lync server 2013](lync-server-2013-create-a-dial-plan.md) или [Изменение абонентской группы в Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="8e293-111">(Optional) Follow the steps in [Create a dial plan in Lync Server 2013](lync-server-2013-create-a-dial-plan.md) or [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

4.  <span data-ttu-id="8e293-112">В разделе **создания** или **редактирования правила нормализации** в поле **Имя** введите имя, описывающее нормализуемый числовой шаблон (например, **5DigitExtension**).</span><span class="sxs-lookup"><span data-stu-id="8e293-112">In **New Normalization Rule** or **Edit Normalization Rule**, type a name that describes the number pattern being normalized in **Name** (for example, name the normalization rule **5DigitExtension**).</span></span>

5.  <span data-ttu-id="8e293-113">В поле **Описание** введите описание правила нормализации (например, "Преобразование пятизначных добавочных номеров") (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="8e293-113">(Optional) In **Description** field, type a description of the normalization rule (for example, "Translates 5-digit extensions").</span></span>

6.  <span data-ttu-id="8e293-114">В разделе **Построение правила нормализации** нажмите кнопку **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="8e293-114">In **Build a Normalization Rule**, click **Edit**.</span></span>

7.  <span data-ttu-id="8e293-115">В разделе **Введите регулярное выражение** введите следующие данные.</span><span class="sxs-lookup"><span data-stu-id="8e293-115">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="8e293-116">В поле **Сопоставить этот шаблон** укажите шаблон, которому должен соответствовать набираемый телефонный номер.</span><span class="sxs-lookup"><span data-stu-id="8e293-116">In **Match this pattern**, specify the pattern that you want to use to match the dialed phone number.</span></span>
    
      - <span data-ttu-id="8e293-117">В поле **Правило трансляции** укажите шаблон для формата преобразуемых телефонных номеров E.164.</span><span class="sxs-lookup"><span data-stu-id="8e293-117">In **Translation rule**, specify a pattern for the format of translated E.164 phone numbers.</span></span>
    
    <span data-ttu-id="8e293-118">Например, при вводе **\\^ (d{7}) $** в соответствии с **этим шаблоном** и **+ 1425 $1** в **правиле перевода**, правило нормализует 5550100 в + 14255550100.</span><span class="sxs-lookup"><span data-stu-id="8e293-118">For example, if you enter **^(\\d{7})$** in **Match this pattern** and **+1425$1** in **Translation rule**, the rule normalizes 5550100 to +14255550100.</span></span>

8.  <span data-ttu-id="8e293-119">Если в результате применения правила нормализации получается внутренний телефонный номер организации, выберите **Внутреннее расширение** (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="8e293-119">(Optional) If the normalization rule results in a phone number that is internal to your organization, select **Internal extension**.</span></span>

9.  <span data-ttu-id="8e293-p104">Введите номер для проверки правила нормализации, затем нажмите кнопку **Перейти** (необязательно). Результаты проверки отображаются под полем **Введите номер телефона для проверки**.</span><span class="sxs-lookup"><span data-stu-id="8e293-p104">(Optional) Enter a number to test the normalization rule and then click **Go**. The test results are displayed under **Enter a number to test**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8e293-122">Вы можете сохранить правило нормализации, которое еще не прошло тест, а затем настроить его позже.</span><span class="sxs-lookup"><span data-stu-id="8e293-122">You can save a normalization rule that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="8e293-123">Подробные сведения можно найти <A href="lync-server-2013-test-voice-routing.md">в разделе Проверка маршрутизации голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8e293-123">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

10. <span data-ttu-id="8e293-124">Нажмите кнопку **ОК** для сохранения правила нормализации.</span><span class="sxs-lookup"><span data-stu-id="8e293-124">Click **OK** to save the normalization rule.</span></span>

11. <span data-ttu-id="8e293-125">Нажмите кнопку **ОК** для сохранения абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="8e293-125">Click **OK** to save the dial plan.</span></span>

12. <span data-ttu-id="8e293-126">На странице **Абонентская группа** нажмите кнопку **Сохранить**, затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="8e293-126">On the **Dial Plan** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8e293-127">Каждый раз, когда вы создаете или изменяете правило нормализации, необходимо выполнить команду <STRONG>commit all</STRONG> , чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="8e293-127">Whenever you create or change a normalization rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="8e293-128">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</A> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="8e293-128">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8e293-129">См. также</span><span class="sxs-lookup"><span data-stu-id="8e293-129">See Also</span></span>


[<span data-ttu-id="8e293-130">Создание и изменение правила нормализации с помощью сборки правила нормализации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e293-130">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)  
[<span data-ttu-id="8e293-131">Создание абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e293-131">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="8e293-132">Изменение абонентской группы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e293-132">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
[<span data-ttu-id="8e293-133">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e293-133">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="8e293-134">Тестирование голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8e293-134">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

