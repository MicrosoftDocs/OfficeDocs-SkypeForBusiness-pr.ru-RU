---
title: 'Lync Server 2013: изменение маршрута голосовых вызовов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice route
ms:assetid: afc562cc-8807-489b-8850-dbbe1c1ab9f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412838(v=OCS.15)
ms:contentKeyID: 48185143
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6e2a3f255a77d7773d24d654c5c207b59b887bc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515346"
---
# <a name="modify-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="91c36-102">Изменение маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91c36-102">Modify a voice route in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91c36-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="91c36-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="91c36-104">В этом разделе даны инструкции по изменению маршрута голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="91c36-104">This topic explains how to edit a voice route.</span></span> <span data-ttu-id="91c36-105">Чтобы создать новый маршрут, ознакомьтесь со статьей [Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span><span class="sxs-lookup"><span data-stu-id="91c36-105">To create a new route, see [Create a voice route in Lync Server 2013](lync-server-2013-create-a-voice-route.md).</span></span>

<div>

## <a name="to-modify-a-voice-route"></a><span data-ttu-id="91c36-106">Изменение маршрута голосовых вызовов</span><span class="sxs-lookup"><span data-stu-id="91c36-106">To modify a voice route</span></span>

1.  <span data-ttu-id="91c36-107">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="91c36-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="91c36-108">Дополнительные сведения см [в разделе Делегирование разрешений на установку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="91c36-108">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="91c36-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91c36-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="91c36-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="91c36-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="91c36-111">В левой панели навигации выберите пункт **Маршрутизация голосовой связи**, а затем — **Route**.</span><span class="sxs-lookup"><span data-stu-id="91c36-111">In the left navigation bar, click **Voice Routing**, and then click **Route**.</span></span>

4.  <span data-ttu-id="91c36-112">На странице **Route** (Маршрут) измените маршрут голосовых вызовов с помощью одного из следующих методов:</span><span class="sxs-lookup"><span data-stu-id="91c36-112">On the **Route** page, use either of the following methods to modify a voice route:</span></span>
    
      - <span data-ttu-id="91c36-113">Последовательно щелкните имя маршрута голосовых вызовов, **Edit** (Изменить) и **Show details** (Подробности).</span><span class="sxs-lookup"><span data-stu-id="91c36-113">Click a voice route name, click **Edit**, and then click **Show details**.</span></span>
    
      - <span data-ttu-id="91c36-p104">Последовательно щелкните имя маршрута голосовых вызовов, **Edit** (Изменить), **Copy** (Копировать) и **Paste** (Вставить). Последовательно щелкните созданную копию маршрута голосовых вызовов, **Edit** (Изменить) и **Show details** (Подробности).</span><span class="sxs-lookup"><span data-stu-id="91c36-p104">Click a voice route name, click **Edit**, click **Copy**, and then click **Paste**. Click the new copy of the voice route that you just created, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="91c36-116">На странице **Edit Voice Route** (Изменение маршрута голосовых вызовов) введите описательное имя маршрута голосовых вызовов в поле **Name** (Имя).</span><span class="sxs-lookup"><span data-stu-id="91c36-116">In the **Name** field on the **Edit Voice Route** page, type a descriptive name for the voice route.</span></span>

6.  <span data-ttu-id="91c36-117">В поле **Description** (Описание) введите дополнительные сведения о маршруте голосовых вызовов (необязательно).</span><span class="sxs-lookup"><span data-stu-id="91c36-117">(Optional) In the **Description** field, type in additional descriptive information for the voice route.</span></span>

7.  <span data-ttu-id="91c36-118">Чтобы указать шаблоны для маршрута, создайте регулярное выражение с помощью средства **Build a pattern to match** (Создание шаблона для поиска соответствия) или вручную.</span><span class="sxs-lookup"><span data-stu-id="91c36-118">To specify the patterns you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="91c36-p105">Для создания регулярного выражения с помощью средства **Build a pattern to match** (Создание шаблона для поиска соответствия) введите значения, показанные ниже. Вы можете указать два типа поиска соответствия по шаблону:</span><span class="sxs-lookup"><span data-stu-id="91c36-p105">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="91c36-121">**Начальные цифры для чисел, которые вы хотите разрешить:** Введите значения префиксов, которые должны поддерживаться этим маршрутом (в том числе ведущие + при необходимости).</span><span class="sxs-lookup"><span data-stu-id="91c36-121">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="91c36-122">Например, введите **+425** и затем щелкните **Add** (Добавить).</span><span class="sxs-lookup"><span data-stu-id="91c36-122">For example, type **+425** and then click **Add**.</span></span> <span data-ttu-id="91c36-123">Повторите этот шаг для каждого значения префикса, которое необходимо включить в маршрут.</span><span class="sxs-lookup"><span data-stu-id="91c36-123">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="91c36-124">**Исключения.** Если вы хотите указать одно или несколько исключений для значения префикса, выделите префикс и нажмите кнопку **исключения**.</span><span class="sxs-lookup"><span data-stu-id="91c36-124">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="91c36-125">Введите одно или несколько значений для поиска соответствия по шаблону, которые *не* требуется включать в маршрут.</span><span class="sxs-lookup"><span data-stu-id="91c36-125">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="91c36-126">Например, чтобы исключить из маршрута номера, начинающиеся с +425237, введите значение **+425237** в поле **Исключения** и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="91c36-126">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="91c36-127">Чтобы вручную определить соответствующие шаблоны, в средстве **создания шаблонов для сопоставления** нажмите кнопку **Edit** (Изменить), а затем введите регулярное выражение .NET Framework, чтобы указать соответствующий шаблон для целевых телефонных номеров, к которым применяется маршрут.</span><span class="sxs-lookup"><span data-stu-id="91c36-127">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="91c36-128">Сведения о том, как писать регулярные выражения, можно найти в разделе "регулярные выражения .NET Framework" [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="91c36-128">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

8.  <span data-ttu-id="91c36-p109">Если вы не хотите, чтобы получатель звонка видел идентификатор телефона, используемого для исходящего вызова, выберите параметр **Скрыть идентификатор звонящего**. При выборе этого параметра вам также потребуется задать параметр **Дополнительный идентификатор звонящего**, который будет отображаться на экране получателя звонка.</span><span class="sxs-lookup"><span data-stu-id="91c36-p109">Select **Suppress caller ID** if you do not want the ID of the phone that is making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

9.  <span data-ttu-id="91c36-131">Чтобы связать один или несколько магистральных каналов ТСОП с маршрутом голосовых вызовов, нажмите кнопку **Добавить** и затем выберите магистральный канал в списке.</span><span class="sxs-lookup"><span data-stu-id="91c36-131">To associate one or more public switched telephone network (PSTN) trunks with the voice route, click **Add**, and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="91c36-132">Если в развертывание включены какие-либо серверы-посредники Microsoft Office Communications Server 2007 R2, они также будут доступны в списке.</span><span class="sxs-lookup"><span data-stu-id="91c36-132">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

10. <span data-ttu-id="91c36-133">Чтобы связать одну или несколько использований PSTN с маршрутом голосовых вызовов, нажмите кнопку **выбрать** и выберите запись из списка записей использования PSTN, определенных для развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="91c36-133">To associate one or more PSTN usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="91c36-134">Чтобы просмотреть свойства каждой из доступных записей об использовании PSTN, ознакомьтесь со статьей <A href="lync-server-2013-view-pstn-usage-records.md">Просмотр записей использования PSTN в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="91c36-134">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="91c36-135">Чтобы создать или изменить записи использования PSTN, ознакомьтесь <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">со статьей Создание политики голосовой связи и настройка записей использования PSTN в Lync server 2013</A> или <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">изменение политики голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="91c36-135">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

11. <span data-ttu-id="91c36-p110">Чтобы оптимизировать производительность, рекомендуется упорядочить записи использования ТСОП. Чтобы изменить положение записи в списке, выделите имя записи и нажмите кнопку со стрелкой "вверх" или "вниз".</span><span class="sxs-lookup"><span data-stu-id="91c36-p110">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="91c36-138">Для политики голосовой связи важен порядок, в котором перечислены режимы работы с ТСОП, а для маршрута голосовых вызовов — нет.</span><span class="sxs-lookup"><span data-stu-id="91c36-138">In contrast to a voice policy where the order in which PSTN usage records are listed is important, the order of PSTN usage records in a voice route is insignificant.</span></span> <span data-ttu-id="91c36-139">Однако мы рекомендуем упорядочить список по частоте использования, например: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span><span class="sxs-lookup"><span data-stu-id="91c36-139">However, we recommend that you organize the list by frequency of use, for example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="91c36-140">(Lync Server обходит список сверху вниз.)</span><span class="sxs-lookup"><span data-stu-id="91c36-140">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

12. <span data-ttu-id="91c36-p112">(Дополнительно). Введите значение в поле **Введите преобразованное число для проверки** и нажмите кнопку **Перейти**. Результаты проверки отобразятся в области под полем.</span><span class="sxs-lookup"><span data-stu-id="91c36-p112">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="91c36-143">Можно сохранить маршрут голосовых вызовов, который еще не прошел проверку, чтобы изменить его конфигурацию позднее.</span><span class="sxs-lookup"><span data-stu-id="91c36-143">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="91c36-144">Дополнительные сведения см <A href="lync-server-2013-test-voice-routing.md">в статье Проверка маршрутизации голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="91c36-144">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

13. <span data-ttu-id="91c36-145">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="91c36-145">Click **OK**.</span></span>

14. <span data-ttu-id="91c36-146">На странице **Route** (Маршрут) щелкните **Commit** (Фиксировать) и затем щелкните **Commit all** (Фиксировать все).</span><span class="sxs-lookup"><span data-stu-id="91c36-146">On the **Route** page, click **Commit**, and then click **Commit all**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="91c36-147">Для публикации изменений конфигурации необходимо использовать команду <STRONG>Сохранить все</STRONG> при каждом изменении или создании маршрута голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="91c36-147">Whenever you create or modify a voice route, you must run the <STRONG>Commit all</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="91c36-148">Дополнительные сведения см в статье <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A> в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="91c36-148">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A> in the Operations documentation.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="91c36-149">См. также</span><span class="sxs-lookup"><span data-stu-id="91c36-149">See Also</span></span>


[<span data-ttu-id="91c36-150">Создание маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91c36-150">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)  
[<span data-ttu-id="91c36-151">Просмотр записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91c36-151">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="91c36-152">Создание политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91c36-152">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="91c36-153">Изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91c36-153">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="91c36-154">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91c36-154">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="91c36-155">Проверка маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91c36-155">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

