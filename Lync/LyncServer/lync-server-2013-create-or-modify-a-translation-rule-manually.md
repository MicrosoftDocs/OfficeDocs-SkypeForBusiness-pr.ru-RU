---
title: 'Lync Server 2013: создание или изменение правила трансляции вручную'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 445b17b5a878e066ed0a77c725ae035101d57469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834781"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a><span data-ttu-id="f0ac7-102">Создание и изменение правила трансляции вручную в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0ac7-102">Create or modify a translation rule manually in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0ac7-103">_**Тема последнего изменения:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="f0ac7-103">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="f0ac7-104">Если вы хотите определить правило перевода с помощью регулярного выражения для соответствующего шаблона и правила трансляции, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-104">Follow these steps if you want to define a translation rule by writing a regular expression for the matching pattern and translation rule.</span></span> <span data-ttu-id="f0ac7-105">Кроме того, вы можете ввести набор значений в инструменте **создать правило перевода** и включить для вас соответствующий шаблон и правило перевода с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-105">Alternatively, you can enter a set of values in the **Build a Translation Rule** tool and enable Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="f0ac7-106">Дополнительные сведения можно найти в разделе [Создание или изменение правила трансляции с помощью средства создания правил перевода в Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span><span class="sxs-lookup"><span data-stu-id="f0ac7-106">For details, see [Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span></span>

<div>

## <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="f0ac7-107">Определение правила преобразования вручную</span><span class="sxs-lookup"><span data-stu-id="f0ac7-107">To define a translation rule manually</span></span>

1.  <span data-ttu-id="f0ac7-108">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="f0ac7-109">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f0ac7-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="f0ac7-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f0ac7-111">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f0ac7-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f0ac7-112">Чтобы приступить к определению правила трансляции, выполните действия, описанные в разделе [Настройка канала передачи мультимедиа в Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) с помощью шага 10 или [Настройте магистраль без обхода мультимедиа в Lync Server 2013 на](lync-server-2013-configure-a-trunk-without-media-bypass.md) этапе 9.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-112">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="f0ac7-113">В поле **Имя** на странице **Создание правила трансляции** или **Изменение правила трансляции** введите имя, описывающее шаблон номера для преобразования.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-113">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="f0ac7-114">В поле **Описание** введите описание этого правила преобразования, например **US International long-distance dialing** (Международный звонок из США) (необязательно).</span><span class="sxs-lookup"><span data-stu-id="f0ac7-114">(Optional) In **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="f0ac7-115">Внизу раздела **Построение правила трансляции** нажмите кнопку **Правка**.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-115">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

7.  <span data-ttu-id="f0ac7-116">В разделе **Ввод регулярных выражений** введите следующие данные.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-116">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="f0ac7-117">В поле **Сопоставить этот шаблон** укажите шаблон, который будет использоваться для сопоставления номеров для преобразования.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-117">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
      - <span data-ttu-id="f0ac7-118">В поле **Правило трансляции** укажите шаблон для формата преобразованных номеров.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-118">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="f0ac7-119">Например, если ввести \*\* ^ \\+ (\\d{9}\\d +) $\*\* в соответствии с **этим шаблоном** и **011 $1** в **правиле перевода**, правило будет переведено + 441235551010 в 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-119">For example, if you enter **^\\+(\\d{9}\\d+)$** in **Match this pattern** and **011$1** in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

8.  <span data-ttu-id="f0ac7-120">Чтобы сохранить правило трансляции, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-120">Click **OK** to save the translation rule.</span></span>

9.  <span data-ttu-id="f0ac7-121">Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-121">Click **OK** to save the trunk configuration.</span></span>

10. <span data-ttu-id="f0ac7-122">На странице **Конфигурация линии связи** нажмите **Сохранить**, затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-122">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f0ac7-123">Всякий раз при создании или изменении правила преобразования необходимо выполнять команду <STRONG>Сохранить все</STRONG>, чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-123">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="f0ac7-124">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</A> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="f0ac7-124">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f0ac7-125">См. также</span><span class="sxs-lookup"><span data-stu-id="f0ac7-125">See Also</span></span>


[<span data-ttu-id="f0ac7-126">Создание или изменение правила трансляции с помощью инструмента "Создание правил перевода" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0ac7-126">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[<span data-ttu-id="f0ac7-127">Configure a trunk with media bypass in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0ac7-127">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="f0ac7-128">Настройка магистрали без обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0ac7-128">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="f0ac7-129">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0ac7-129">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="f0ac7-130">Глобальные параметры обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0ac7-130">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

