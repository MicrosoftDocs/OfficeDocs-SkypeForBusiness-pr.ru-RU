---
title: 'Lync Server 2013: Создание голосового маршрута'
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
ms.openlocfilehash: 30a25f9d070c81d45ffc966be49560dc67c292c4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-route-in-lync-server-2013"></a><span data-ttu-id="21051-102">Создание голосового маршрута в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21051-102">Create a voice route in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21051-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="21051-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="21051-104">Ниже описана процедура создания нового голосового маршрута с помощью панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="21051-104">The following procedure explains how to create a new voice route by using the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="21051-105">Чтобы изменить существующий маршрут, ознакомьтесь со сведениями [в разделе изменение маршрута голосовой связи в Lync Server 2013](lync-server-2013-modify-a-voice-route.md) для этой процедуры.</span><span class="sxs-lookup"><span data-stu-id="21051-105">To edit an existing route, see [Modify a voice route in Lync Server 2013](lync-server-2013-modify-a-voice-route.md) for the procedure.</span></span>

<div>

## <a name="to-create-a-voice-route-by-using-the-lync-server-control-panel"></a><span data-ttu-id="21051-106">Создание голосового маршрута с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="21051-106">To create a voice route by using the Lync Server Control Panel</span></span>

1.  <span data-ttu-id="21051-107">Войдите на компьютер в качестве члена группы RTCUniversalServerAdmins или роли администратора **CsVoiceAdministrator**, **CsServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="21051-107">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>

2.  <span data-ttu-id="21051-108">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="21051-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="21051-109">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="21051-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="21051-110">В левой области навигации щелкните **Маршрутизация голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="21051-110">In the left navigation bar, click **Voice Routing**.</span></span>

4.  <span data-ttu-id="21051-111">Щелкните **Маршрут**.</span><span class="sxs-lookup"><span data-stu-id="21051-111">Click **Route**.</span></span>

5.  <span data-ttu-id="21051-112">Нажмите кнопку **Создать** для отображения диалогового окна **создания маршрута голосовой связи**.</span><span class="sxs-lookup"><span data-stu-id="21051-112">Click **New** to display the **New Voice Route** dialog box.</span></span>

6.  <span data-ttu-id="21051-113">В поле **Имя** введите информативное имя маршрута голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="21051-113">In **Name**, type a descriptive name for the voice route.</span></span>

7.  <span data-ttu-id="21051-114">В поле **Описание** введите дополнительные сведения, характеризующие маршрут голосовой связи (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="21051-114">(Optional) In **Description**, type additional descriptive information for the voice route.</span></span>

8.  <span data-ttu-id="21051-115">Регулярное выражение для задания шаблонов, с которыми требуется согласовать этот маршрут, можно сформировать с помощью инструмента **Построение шаблона для поиска соответствия** или написать вручную.</span><span class="sxs-lookup"><span data-stu-id="21051-115">To specify the patterns that you want this route to accommodate, you can either use the **Build a pattern to match** tool to generate a regular expression, or write the regular expression manually.</span></span>
    
      - <span data-ttu-id="21051-p103">Для формирования регулярного выражения с помощью инструмента **Построение шаблона для поиска соответствия** для создания регулярного выражения, введите следующие значения. Можно задать два типа соответствия шаблону.</span><span class="sxs-lookup"><span data-stu-id="21051-p103">To use the **Build a pattern to match** tool to generate a regular expression, enter values as follows. You can specify two types of pattern matching:</span></span>
        
          - <span data-ttu-id="21051-118">**Начальные цифры для чисел, которые вы хотите разрешить:** Введите значения префиксов, которые должен разместить этот маршрут (включая интерлиньяж + при необходимости).</span><span class="sxs-lookup"><span data-stu-id="21051-118">**Starting digits for numbers that you want to allow:** Enter prefix values that this route must accommodate (including the leading + if needed).</span></span> <span data-ttu-id="21051-119">Например, введите **+ 425**и нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="21051-119">For example, type **+425**, and then click **Add**.</span></span> <span data-ttu-id="21051-120">Повторите эти действия для каждого значения префикса, которое вы хотите включить в маршрут.</span><span class="sxs-lookup"><span data-stu-id="21051-120">Repeat this for each prefix value that you want to include in the route.</span></span>
        
          - <span data-ttu-id="21051-121">**Исключения.** Если вы хотите задать одно или несколько исключений для значения prefix, выделите префикс и нажмите кнопку **исключения**.</span><span class="sxs-lookup"><span data-stu-id="21051-121">**Exceptions:** If you want to specify one or more exceptions for a prefix value, highlight the prefix and click **Exceptions**.</span></span> <span data-ttu-id="21051-122">Введите одно или несколько значений для соответствующих шаблонов, которые *не* должны допускает этот маршрут.</span><span class="sxs-lookup"><span data-stu-id="21051-122">Type in one or more values for the matching patterns that you do *not* want this route to accommodate.</span></span> <span data-ttu-id="21051-123">Например, чтобы исключить из маршрута номера, начинающиеся с + 425237, введите в поле **исключения** значение **+ 425237** , а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="21051-123">For example, to exclude numbers starting with +425237 from the route, enter a value of **+425237** in the **Exceptions** field, and then click **OK**.</span></span>
    
      - <span data-ttu-id="21051-124">Для задания шаблона соответствия вручную нажмите кнопку **Изменить** в инструменте **Построение шаблона для поиска соответствия**, затем введите регулярное выражение .NET Framework, определяющее шаблон соответствия для телефонных номеров адресатов, к которым применяется маршрут.</span><span class="sxs-lookup"><span data-stu-id="21051-124">To define the matching pattern manually, click **Edit** in the **Build a pattern to match** tool and then type in a .NET Framework regular expression to specify the matching pattern for destination phone numbers to which the route is applied.</span></span> <span data-ttu-id="21051-125">Сведения о том, как создавать регулярные выражения, приведены в [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)разделе "регулярные выражения .NET Framework".</span><span class="sxs-lookup"><span data-stu-id="21051-125">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

9.  <span data-ttu-id="21051-p107">Если требуется, чтобы идентификатор телефона, с которого выполняется посылка вызова, не отображался на устройстве вызываемого абонента, выберите **Скрыть идентификатор звонящего**. При выборе этого этого режима необходимо задать параметр **Дополнительный идентификатор звонящего** для отображения на дисплее вызываемого абонента.</span><span class="sxs-lookup"><span data-stu-id="21051-p107">Select **Suppress caller ID** if you do not want the ID of the phone making the outbound call to appear to the call recipient. If you select this option, you must specify an **Alternate caller ID** that will appear on the recipient’s caller ID display.</span></span>

10. <span data-ttu-id="21051-128">Для связывания одной или нескольких линий связи с маршрутом голосовой связи нажмите кнопку **Добавить**, затем выберите в списке линию связи.</span><span class="sxs-lookup"><span data-stu-id="21051-128">To associate one or more trunks with the voice route, click **Add** and then select a trunk from the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21051-129">Если в развертывании есть серверы исправлений Microsoft Office Communications Server 2007 R2, они также будут доступны в списке.</span><span class="sxs-lookup"><span data-stu-id="21051-129">If your deployment includes any Microsoft Office Communications Server 2007 R2 Mediation Servers, they will also be available in the list.</span></span>

    
    </div>

11. <span data-ttu-id="21051-130">Чтобы сопоставить один или несколько использованных коммутируемых телефонных сетей (PSTN) с голосовым маршрутом, щелкните **выбрать** и выберите запись из списка записей PSTN-связи, которые были определены для вашего корпоративного речевого развертывания.</span><span class="sxs-lookup"><span data-stu-id="21051-130">To associate one or more public switched telephone network (PSTN) usages with the voice route, click **Select** and choose a record from the list of PSTN usage records that have been defined for your Enterprise Voice deployment.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21051-131">Чтобы просмотреть свойства каждой из доступных записей об использовании PSTN, ознакомьтесь со сведениями <A href="lync-server-2013-view-pstn-usage-records.md">Просмотр записей об использовании PSTN в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="21051-131">To view the properties of each of the available PSTN usage records, see <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN usage records in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="21051-132">Чтобы создать или изменить записи использования PSTN, ознакомьтесь <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">со сведениями создание политики голосовой связи и настройка записей использования PSTN в Lync server 2013</A> или <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">изменение политики голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="21051-132">To create or edit PSTN usage records, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A>.</span></span>

    
    </div>

12. <span data-ttu-id="21051-p108">Упорядочите записи использования ТСОП для достижений оптимальной производительности. Чтобы изменить положение записи в списке, выделите ее имя и щелкните стрелку вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="21051-p108">Arrange the PSTN usage records for optimum performance. To change a record’s position in the list, highlight the record name and click the up or down arrow.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21051-135">В отличие от политики голосовой связи, в которой указаны важные записи использования PSTN, порядок, в котором записи использования PSTN указаны в маршруте голосовой связи, не важен.</span><span class="sxs-lookup"><span data-stu-id="21051-135">In contrast to a voice policy, where the order in which PSTN usage records are listed is important, the order in which PSTN usage records are listed in the voice route is insignificant.</span></span> <span data-ttu-id="21051-136">Тем не менее, мы рекомендуем упорядочить список по частоте использования.</span><span class="sxs-lookup"><span data-stu-id="21051-136">However, we recommend that you organize the list by frequency of use.</span></span> <span data-ttu-id="21051-137">Например: Редмондлокал, Редмондлонгдист, Редмондинтернатионал, Редмондбаккуп.</span><span class="sxs-lookup"><span data-stu-id="21051-137">For example: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.</span></span> <span data-ttu-id="21051-138">(Lync Server обходит список сверху вниз.)</span><span class="sxs-lookup"><span data-stu-id="21051-138">(Lync Server traverses the list from the top down.)</span></span>

    
    </div>

13. <span data-ttu-id="21051-p110">Введите значение в поле **Преобразованный номер для проверки** и нажмите кнопку **Перейти** (Не обязательно). Результаты проверки отображаются под полем.</span><span class="sxs-lookup"><span data-stu-id="21051-p110">(Optional) Type a value into the **Enter a translated number to test** field and click **Go**. The test results are displayed under the field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="21051-141">Вы можете сохранить маршрут голосовой связи, который еще не пройдет проверку, а затем настроить его позже.</span><span class="sxs-lookup"><span data-stu-id="21051-141">You can save a voice route that does not yet pass the test and then reconfigure it later.</span></span> <span data-ttu-id="21051-142">Подробные сведения можно найти <A href="lync-server-2013-test-voice-routing.md">в разделе Проверка маршрутизации голосовой связи в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="21051-142">For details, see <A href="lync-server-2013-test-voice-routing.md">Test voice routing in Lync Server 2013</A>.</span></span>

    
    </div>

14. <span data-ttu-id="21051-143">Нажмите кнопку **ОК** для сохранения маршрута голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="21051-143">Click **OK** to save the voice route.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="21051-144">Каждый раз, когда вы создаете голосовой маршрут, необходимо выполнить команду <STRONG>commit all</STRONG> , чтобы опубликовать изменение конфигурации.</span><span class="sxs-lookup"><span data-stu-id="21051-144">Whenever you create a voice route, you must run the <STRONG>Commit All</STRONG> command to publish the configuration change.</span></span> <span data-ttu-id="21051-145">Дополнительные сведения можно найти в разделе <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="21051-145">For details, see <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish pending changes to the voice routing configuration in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="21051-146">См. также</span><span class="sxs-lookup"><span data-stu-id="21051-146">See Also</span></span>


[<span data-ttu-id="21051-147">Изменение маршрута голосовой связи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21051-147">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)  
[<span data-ttu-id="21051-148">Просмотр записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21051-148">View PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-view-pstn-usage-records.md)  
[<span data-ttu-id="21051-149">Создание политики голосовой связи и настройка записей об использовании PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21051-149">Create a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="21051-150">Изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21051-150">Modify a voice policy and configure PSTN usage records in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[<span data-ttu-id="21051-151">Публикация ожидающих изменений в конфигурации голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21051-151">Publish pending changes to the voice routing configuration in Lync Server 2013</span></span>](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  


[<span data-ttu-id="21051-152">Тестирование голосовой маршрутизации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21051-152">Test voice routing in Lync Server 2013</span></span>](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

