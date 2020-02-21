---
title: 'Lync Server 2013: создание маршрута голосовой связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice route
ms:assetid: d189057d-cc9d-4622-9d10-f5385d703faf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398898(v=OCS.15)
ms:contentKeyID: 48185438
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37f62b6ba64456b8e892c94117750bf1bc209bc0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191752"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="2c94a-102">Создание маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c94a-102">Create a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c94a-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2c94a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2c94a-104">В следующей процедуре объясняется, как создать новый маршрут голосовой связи с помощью панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2c94a-104">The following procedure explains how to create a new voice route by using the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="2c94a-105">Чтобы изменить существующий маршрут, ознакомьтесь со статьей [изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md) для процедуры.</span><span class="sxs-lookup"><span data-stu-id="2c94a-105">To edit an existing route, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) for the procedure.</span></span>

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a><span data-ttu-id="2c94a-106">Создание маршрута голосовой связи с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="2c94a-106">To create a voice route by using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="2c94a-107">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="2c94a-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="2c94a-108">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2c94a-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2c94a-109">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2c94a-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2c94a-110">В левой области навигации щелкните элемент **Маршрутизация голосовых вызовов**.</span><span class="sxs-lookup"><span data-stu-id="2c94a-110">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="2c94a-111">Перейдите на вкладку **Route** (Маршрут).</span><span class="sxs-lookup"><span data-stu-id="2c94a-111">Click **Route**.</span></span>

5.  <span data-ttu-id="2c94a-112">Нажмите кнопку **Создать**, чтобы вывести на экран диалоговое окно **Создание маршрута голосовых вызовов**.</span><span class="sxs-lookup"><span data-stu-id="2c94a-112">Click **New** to display the **New Voice Route** dialog box.</span></span>

6.  <span data-ttu-id="2c94a-113">В поле **Name** (Имя) введите описательное имя маршрута голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="2c94a-113">In **Name**, type a descriptive name for the voice route.</span></span>

7.  <span data-ttu-id="2c94a-114">(Дополнительно). В поле **Description** (Описание) введите дополнительные сведения, описывающие маршрут голосовых вызовов.</span><span class="sxs-lookup"><span data-stu-id="2c94a-114">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>

8.  <span data-ttu-id="2c94a-115">Чтобы указать шаблоны, которые будет включать этот маршрут, можно использовать средство **создания шаблона для сопоставления**, чтобы создать регулярное выражение или записать это выражение вручную.</span><span class="sxs-lookup"><span data-stu-id="2c94a-115">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="2c94a-p103">Чтобы использовать средство **создания шаблона для сопоставления** для создания регулярного выражения, введите следующие значения. Можно указать два типа сопоставления шаблонов.</span><span class="sxs-lookup"><span data-stu-id="2c94a-p103">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="2c94a-118">**Начальные цифры для чисел, которые вы хотите разрешить:** Введите значения префиксов, которые должны поддерживаться этим маршрутом (в том числе ведущие + при необходимости).</span><span class="sxs-lookup"><span data-stu-id="2c94a-118">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="2c94a-119">Например, введите **+ 425**, а затем нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="2c94a-119">For example, type **+425**, and then click **Add**.</span></span> <span data-ttu-id="2c94a-120">Повторите этот шаг для каждого значения префикса, которое необходимо включить в маршрут.</span><span class="sxs-lookup"><span data-stu-id="2c94a-120">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="2c94a-121">**Исключения.** Если вы хотите указать одно или несколько исключений для значения префикса, выделите префикс и нажмите кнопку **исключения**.</span><span class="sxs-lookup"><span data-stu-id="2c94a-121">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="2c94a-122">Введите одно или несколько значений для поиска соответствия по шаблону, которые *не* требуется включать в маршрут.</span><span class="sxs-lookup"><span data-stu-id="2c94a-122">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="2c94a-123">Например, чтобы исключить из маршрута номера, начинающиеся с +425237, введите значение **+425237** в поле **Исключения** и затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c94a-123">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="2c94a-124">Чтобы вручную определить соответствующие шаблоны, в средстве **создания шаблонов для сопоставления** нажмите кнопку **Edit** (Изменить), а затем введите регулярное выражение .NET Framework, чтобы указать соответствующий шаблон для целевых телефонных номеров, к которым применяется маршрут.</span><span class="sxs-lookup"><span data-stu-id="2c94a-124">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="2c94a-125">Сведения о том, как писать регулярные выражения, можно найти в [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927)разделе "регулярные выражения .NET Framework".</span><span class="sxs-lookup"><span data-stu-id="2c94a-125">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

9.  <span data-ttu-id="2c94a-p107">Выберите **Блокировать АнтиАОН**, если требуется запретить отображение ИД телефона, с которого поступает исходящий вызов, для получателя звонка. Если выбрать этот вариант, необходимо указать **Альтернативный АнтиАОН**, который будет отображаться на экране телефона получателя.</span><span class="sxs-lookup"><span data-stu-id="2c94a-p107">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

10. <span data-ttu-id="2c94a-128">Чтобы связать одну или несколько магистралей с маршрутом голосовых вызовов, нажмите кнопку **Добавить**, а затем выберите магистраль из списка.</span><span class="sxs-lookup"><span data-stu-id="2c94a-128">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2c94a-129">Если в развертывание включены какие-либо серверы-посредники Microsoft Office Communications Server 2007 R2, они также будут доступны в списке.</span><span class="sxs-lookup"><span data-stu-id="2c94a-129">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

11. <span data-ttu-id="2c94a-130">Чтобы связать одно или несколько использований PSTN с маршрутом голосовых звонков, нажмите кнопку **Select** (Выбрать) и выберите запись из списка записей использования PSTN, определенных для развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="2c94a-130">To associate one or more public switched telephone network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2c94a-131">Чтобы просмотреть свойства каждой из доступных записей об использовании PSTN, ознакомьтесь со статьей <A href="lync-server-2013-view-pstn-usage-records.md">Просмотр записей использования PSTN в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2c94a-131">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="2c94a-132">Чтобы создать или изменить записи использования PSTN, ознакомьтесь <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">со статьей Создание политики голосовой связи и настройка записей использования PSTN в Lync server 2013</A> или <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">изменение политики голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2c94a-132">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="2c94a-p108">Чтобы оптимизировать производительность, рекомендуется упорядочить записи использования ТСОП. Чтобы изменить положение записи в списке, выделите имя записи и нажмите кнопку со стрелкой "вверх" или "вниз".</span><span class="sxs-lookup"><span data-stu-id="2c94a-p108">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2c94a-135">В отличие от политики голосовой связи, в порядке, в котором перечислены записи использования PSTN, важен порядок, в котором записи использования PSTN указаны в маршруте голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="2c94a-135">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="2c94a-136">Тем не менее, рекомендуется упорядочить список по частоте использования.</span><span class="sxs-lookup"><span data-stu-id="2c94a-136">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="2c94a-137">Например: Редмондлокал, Редмондлонгдист, Редмондинтернатионал, Редмондбаккуп.</span><span class="sxs-lookup"><span data-stu-id="2c94a-137">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="2c94a-138">(Lync Server обходит список сверху вниз.)</span><span class="sxs-lookup"><span data-stu-id="2c94a-138">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

13. <span data-ttu-id="2c94a-p110">(Дополнительно). Введите значение в поле **Введите преобразованное число для проверки** и нажмите кнопку **Перейти**. Результаты проверки отобразятся в области под полем.</span><span class="sxs-lookup"><span data-stu-id="2c94a-p110">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2c94a-141">Можно сохранить маршрут голосовых вызовов, который еще не прошел проверку, чтобы изменить его конфигурацию позднее.</span><span class="sxs-lookup"><span data-stu-id="2c94a-141">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="2c94a-142">Дополнительные сведения см <A href="lync-server-2013-test-voice-routing.md">в статье Проверка маршрутизации голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2c94a-142">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

14. <span data-ttu-id="2c94a-143">Чтобы сохранить маршрут голосовых вызовов, нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="2c94a-143">Click **OK** to save the voice route.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2c94a-144">Каждый раз при создании маршрута голосовых вызовов необходимо запускать команду <STRONG>Commit All</STRONG> (Фиксировать все), чтобы опубликовать изменение в конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2c94a-144">Whenever you create a voice route, you must run the <STRONG>Commit All</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="2c94a-145">Дополнительные сведения см <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">в статье публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2c94a-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2c94a-146">См. также</span><span class="sxs-lookup"><span data-stu-id="2c94a-146">See Also</span></span>


[<span data-ttu-id="2c94a-147">Изменение маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c94a-147">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="2c94a-148">Просмотр записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c94a-148">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="2c94a-149">Создание политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c94a-149">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="2c94a-150">Изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c94a-150">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="2c94a-151">Публикация ожидающих изменений в конфигурации маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c94a-151">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="2c94a-152">Проверка маршрутизации голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2c94a-152">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

