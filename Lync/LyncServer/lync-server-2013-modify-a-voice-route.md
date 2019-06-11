---
title: 'Lync Server 2013: изменение голосового маршрута'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47a138fd0ffa1556ea4f6f80c53f7357137a7661
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="53a37-102">Изменение маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53a37-102">Modify a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53a37-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="53a37-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="53a37-104">В этой статье объясняется, как изменить голосовой маршрут.</span><span class="sxs-lookup"><span data-stu-id="53a37-104">This topic explains how to edit a voice route.</span></span> <span data-ttu-id="53a37-105">Чтобы создать новый маршрут, ознакомьтесь со сведениями [Создание маршрута голосовой связи в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="53a37-105">To create a new route, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>

<div>

## <a name="to-modify-a-voice-route"></a><span data-ttu-id="53a37-106">Изменение маршрута голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="53a37-106">To modify a voice route</span></span>

1.  <span data-ttu-id="53a37-107">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="53a37-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="53a37-108">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="53a37-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="53a37-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53a37-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="53a37-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="53a37-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="53a37-111">В левой панели навигации щелкните **Маршрутизация голосовой связи**, затем **Маршрут**.</span><span class="sxs-lookup"><span data-stu-id="53a37-111">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>

4.  <span data-ttu-id="53a37-112">На странице **Маршрут** (Маршрут) измените маршрут голосовой связи одним из следующих способов.</span><span class="sxs-lookup"><span data-stu-id="53a37-112">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
      - <span data-ttu-id="53a37-113">Щелкните имя маршрута голосовой связи, затем **Изменить** и **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="53a37-113">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="53a37-p104">Щелкните имя маршрута голосовой связи, затем **Изменить**, **Копировать** и **Вставить** (Вставить). Щелкните только что созданную копию маршрута голосовой связи, затем **Изменить** и **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="53a37-p104">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**. Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="53a37-116">В поле **Имя** на странице **изменения маршрута голосовой связи** введите информативное имя маршрута голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="53a37-116">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>

6.  <span data-ttu-id="53a37-117">В поле **Описание** введите дополнительные сведения о маршруте голосовой связи (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="53a37-117">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>

7.  <span data-ttu-id="53a37-118">Регулярное выражение для задания шаблонов, с которыми требуется согласовать этот маршрут, можно сформировать с помощью инструмента **Построение шаблона для поиска соответствия** или написать вручную.</span><span class="sxs-lookup"><span data-stu-id="53a37-118">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="53a37-p105">Для формирования регулярного выражения с помощью инструмента **Построение шаблона для поиска соответствия** для создания регулярного выражения, введите следующие значения. Можно задать два типа соответствия шаблону.</span><span class="sxs-lookup"><span data-stu-id="53a37-p105">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="53a37-121">**Начальные цифры для чисел, которые вы хотите разрешить:** Введите значения префиксов, которые должен разместить этот маршрут (включая интерлиньяж + при необходимости).</span><span class="sxs-lookup"><span data-stu-id="53a37-121">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="53a37-122">Например, введите **+ 425** и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="53a37-122">For example, type **+425** and then click **Add**.</span></span> <span data-ttu-id="53a37-123">Повторите эти действия для каждого значения префикса, которое вы хотите включить в маршрут.</span><span class="sxs-lookup"><span data-stu-id="53a37-123">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="53a37-124">**Исключения.** Если вы хотите задать одно или несколько исключений для значения prefix, выделите префикс и нажмите кнопку **исключения**.</span><span class="sxs-lookup"><span data-stu-id="53a37-124">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="53a37-125">Введите одно или несколько значений для соответствующих шаблонов, которые *не* должны допускает этот маршрут.</span><span class="sxs-lookup"><span data-stu-id="53a37-125">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="53a37-126">Например, чтобы исключить из маршрута номера, начинающиеся с + 425237, введите в поле **исключения** значение **+ 425237** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="53a37-126">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="53a37-127">Для задания шаблона соответствия вручную нажмите кнопку **Изменить** в инструменте **Построение шаблона для поиска соответствия**, затем введите регулярное выражение .NET Framework, определяющее шаблон соответствия для телефонных номеров адресатов, к которым применяется маршрут.</span><span class="sxs-lookup"><span data-stu-id="53a37-127">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="53a37-128">Сведения о том, как создавать регулярные выражения, приведены в [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)разделе "регулярные выражения .NET Framework".</span><span class="sxs-lookup"><span data-stu-id="53a37-128">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

8.  <span data-ttu-id="53a37-p109">Если требуется, чтобы идентификатор телефона, с которого выполняется посылка вызова, не отображался на устройстве вызываемого абонента, выберите **Скрыть идентификатор звонящего**. При выборе этого этого режима необходимо задать параметр **Дополнительный идентификатор звонящего** для отображения на дисплее вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="53a37-p109">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

9.  <span data-ttu-id="53a37-131">Для связывания одной или нескольких линий связи ТСОП с маршрутом голосовой связи нажмите кнопку **Добавить**, затем выберите в списке линию связи.</span><span class="sxs-lookup"><span data-stu-id="53a37-131">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53a37-132">Если в развертывании есть серверы исправлений Microsoft Office Communications Server 2007 R2, они также будут доступны в списке.</span><span class="sxs-lookup"><span data-stu-id="53a37-132">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

10. <span data-ttu-id="53a37-133">Чтобы сопоставить один или несколько использованных PSTN с голосовым маршрутом, щелкните **выбрать** и выберите запись из списка записей PSTN-связи, которые были определены для вашего корпоративного речевого развертывания.</span><span class="sxs-lookup"><span data-stu-id="53a37-133">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53a37-134">Чтобы просмотреть свойства каждой из доступных записей об использовании PSTN, ознакомьтесь со сведениями <A href="lync-server-2013-view-pstn-usage-records.md">Просмотр записей об использовании PSTN в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="53a37-134">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="53a37-135">Чтобы создать или изменить записи использования PSTN, ознакомьтесь <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">со сведениями создание политики голосовой связи и настройка записей использования PSTN в Lync server 2013</A> или <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">изменение политики голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="53a37-135">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="53a37-p110">Упорядочите записи использования ТСОП для достижений оптимальной производительности. Чтобы изменить положение записи в списке, выделите ее имя и щелкните стрелку вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="53a37-p110">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53a37-138">В отличие от политики голосовой связи, в которой указаны важные записи использования PSTN, порядок записи использования PSTN в маршруте голосовой связи неважен.</span><span class="sxs-lookup"><span data-stu-id="53a37-138">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="53a37-139">Тем не менее, мы рекомендуем упорядочить список по частоте использования, например: Редмондлокал, Редмондлонгдист, Редмондинтернатионал, Редмондбаккуп.</span><span class="sxs-lookup"><span data-stu-id="53a37-139">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="53a37-140">(Lync Server обходит список сверху вниз.)</span><span class="sxs-lookup"><span data-stu-id="53a37-140">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

12. <span data-ttu-id="53a37-p112">Введите значение в поле **Преобразованный номер для проверки** и нажмите кнопку **Перейти** (Не обязательно). Результаты проверки отображаются под полем.</span><span class="sxs-lookup"><span data-stu-id="53a37-p112">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53a37-143">Вы можете сохранить маршрут голосовой связи, который еще не пройдет проверку, а затем настроить его позже.</span><span class="sxs-lookup"><span data-stu-id="53a37-143">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="53a37-144">Подробные сведения можно найти <A href="lync-server-2013-test-voice-routing.md">в разделе Проверка маршрутизации голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="53a37-144">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="53a37-145">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="53a37-145">Click **OK**.</span></span>

14. <span data-ttu-id="53a37-146">На странице **Маршрут** (Маршрут) щелкните **Сохранить**, затем **Сохранить все**.</span><span class="sxs-lookup"><span data-stu-id="53a37-146">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53a37-147">Каждый раз, когда вы создаете или изменяете голосовой маршрут, необходимо выполнить команду <STRONG>commit all</STRONG> , чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="53a37-147">Whenever you create or modify a voice route, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="53a37-148">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</A> в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="53a37-148">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="53a37-149">См. также</span><span class="sxs-lookup"><span data-stu-id="53a37-149">See Also</span></span>


[<span data-ttu-id="53a37-150">Создание голосового маршрута в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53a37-150">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="53a37-151">Просмотр записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53a37-151">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="53a37-152">Создание политики голосовой связи и настройка записей об использовании PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53a37-152">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="53a37-153">Изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53a37-153">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="53a37-154">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53a37-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="53a37-155">Тестирование голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53a37-155">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

