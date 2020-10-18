---
title: 'Lync Server 2013: создание или изменение правила трансляции вручную'
description: 'Lync Server 2013: создание или изменение правила трансляции вручную.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a translation rule manually
ms:assetid: 049d1db3-af58-48c5-be89-52e1d068a4bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398099(v=OCS.15)
ms:contentKeyID: 48183276
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f393ca1983e072090cc27d47b142dace8b566c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574505"
---
# <a name="create-or-modify-a-translation-rule-manually-in-lync-server-2013"></a><span data-ttu-id="a464d-103">Создание или изменение правила трансляции вручную в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a464d-103">Create or modify a translation rule manually in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a464d-104">_**Последнее изменение темы:** 2012-08-06_</span><span class="sxs-lookup"><span data-stu-id="a464d-104">_**Topic Last Modified:** 2012-08-06_</span></span>

<span data-ttu-id="a464d-105">Если требуется задать правило преобразования путем создания регулярного выражения для шаблона соответствия и правила преобразования, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="a464d-105">Follow these steps if you want to define a translation rule by writing a regular expression for the matching pattern and translation rule.</span></span> <span data-ttu-id="a464d-106">Кроме того, можно ввести набор значений в инструменте **Создание правила преобразования** и включить панель управления Lync Server для создания соответствующего шаблона и правила преобразования.</span><span class="sxs-lookup"><span data-stu-id="a464d-106">Alternatively, you can enter a set of values in the **Build a Translation Rule** tool and enable Lync Server Control Panel to generate the corresponding matching pattern and translation rule for you.</span></span> <span data-ttu-id="a464d-107">Дополнительные сведения см. в статье [Создание или изменение правила преобразования с помощью средства создания правил преобразования в Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span><span class="sxs-lookup"><span data-stu-id="a464d-107">For details, see [Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md).</span></span>

<div>

## <a name="to-define-a-translation-rule-manually"></a><span data-ttu-id="a464d-108">Определение правила преобразования вручную</span><span class="sxs-lookup"><span data-stu-id="a464d-108">To define a translation rule manually</span></span>

1.  <span data-ttu-id="a464d-109">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="a464d-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="a464d-110">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="a464d-110">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="a464d-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a464d-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a464d-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a464d-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a464d-113">Чтобы приступить к определению правила преобразования, выполните действия, описанные в статье [Настройка магистрали с обходом сервера, в Lync server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) до этапа 10 или [Настройка магистрали без обхода сервера в Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) с шага 9.</span><span class="sxs-lookup"><span data-stu-id="a464d-113">To begin defining a translation rule, follow the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md) through step 10 or [Configure a trunk without media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md) through step 9.</span></span>

4.  <span data-ttu-id="a464d-114">В поле **Имя** на странице **Создание правила преобразования** или  **Изменение правила преобразования** введите имя, описывающее шаблон номера для преобразования.</span><span class="sxs-lookup"><span data-stu-id="a464d-114">In the **Name** field on the **New Translation Rule** or **Edit Translation Rule** page, type a name that describes the number pattern being translated.</span></span>

5.  <span data-ttu-id="a464d-115">В поле **Описание** введите описание этого правила преобразования, например **Международный звонок из США** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="a464d-115">(Optional) In **Description**, type a description of the translation rule, for example **US International long-distance dialing**.</span></span>

6.  <span data-ttu-id="a464d-116">Внизу раздела **Построение правила преобразования** нажмите кнопку **Правка**.</span><span class="sxs-lookup"><span data-stu-id="a464d-116">Click **Edit** at the bottom of the **Build a Translation Rule** section.</span></span>

7.  <span data-ttu-id="a464d-117">В диалоговом окне **Ввод регулярных выражений** введите следующее.</span><span class="sxs-lookup"><span data-stu-id="a464d-117">Enter the following in **Type a Regular Expression**:</span></span>
    
      - <span data-ttu-id="a464d-118">В поле **Сопоставить этот шаблон** укажите шаблон, который будет использоваться для сопоставления номеров для преобразования.</span><span class="sxs-lookup"><span data-stu-id="a464d-118">In **Match this pattern**, specify the pattern that will be used to match the numbers to be translated.</span></span>
    
      - <span data-ttu-id="a464d-119">В поле **Правило преобразования** укажите шаблон для формата преобразованных номеров.</span><span class="sxs-lookup"><span data-stu-id="a464d-119">In **Translation rule**, specify a pattern for the format of translated numbers.</span></span>
    
    <span data-ttu-id="a464d-120">Например, если ввести \*\* ^ \\ + ( \\ d {9} \\ d +) $\*\* в поле **сопоставить этот шаблон** и **011 $1** в **правиле преобразования**, то правило будет переводиться + 441235551010 на 011441235551010.</span><span class="sxs-lookup"><span data-stu-id="a464d-120">For example, if you enter **^\\+(\\d{9}\\d+)$** in **Match this pattern** and **011$1** in **Translation rule**, the rule will translate +441235551010 to 011441235551010.</span></span>

8.  <span data-ttu-id="a464d-121">Чтобы сохранить правило преобразования, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a464d-121">Click **OK** to save the translation rule.</span></span>

9.  <span data-ttu-id="a464d-122">Чтобы сохранить конфигурацию магистрали, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="a464d-122">Click **OK** to save the trunk configuration.</span></span>

10. <span data-ttu-id="a464d-123">На странице **Trunk Configuration** (Конфигурация магистрали) щелкните **Commit** (Сохранить) и затем щелкните **Commit all** (Сохранить все).</span><span class="sxs-lookup"><span data-stu-id="a464d-123">On the **Trunk Configuration** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a464d-124">Всякий раз при создании или изменении правила преобразования необходимо выполнять команду <STRONG>Commit all</STRONG> (Сохранить все), чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a464d-124">Whenever you create or modify a translation rule, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="a464d-125">Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="a464d-125">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a464d-126">См. также</span><span class="sxs-lookup"><span data-stu-id="a464d-126">See Also</span></span>


[<span data-ttu-id="a464d-127">Создание или изменение правила преобразования с помощью средства "Построение правила преобразования" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a464d-127">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)  
[<span data-ttu-id="a464d-128">Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a464d-128">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="a464d-129">Настройка магистрали без обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a464d-129">Configure a trunk without media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-without-media-bypass.md)  
[<span data-ttu-id="a464d-130">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a464d-130">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="a464d-131">Глобальные параметры обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a464d-131">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

