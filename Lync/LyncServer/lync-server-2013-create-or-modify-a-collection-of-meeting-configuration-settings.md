---
title: Создание и изменение коллекции параметров конфигурации собраний
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a5f80066a68b45e062a351478bea93a5c2e8fd0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="f6fb9-102">Создание и изменение коллекции параметров конфигурации собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6fb9-102">Create or modify a collection of meeting configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6fb9-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="f6fb9-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="f6fb9-104">С помощью параметров на странице Настройка собрания можно определять различные характеристики присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-104">You can use the settings on the Meeting Configuration page to define various characteristics of the meeting join experience.</span></span> <span data-ttu-id="f6fb9-105">По умолчанию глобальные параметры определяют взаимодействие с соединением.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-105">By default, the global settings define the join experience.</span></span> <span data-ttu-id="f6fb9-106">Вы также можете создать параметры присоединения к собранию на уровне сайта и пула.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-106">You can also create site-level and pool-level meeting join settings.</span></span> <span data-ttu-id="f6fb9-107">Параметры, заданные на уровне пула, применяются ко всем собраниям, размещенным в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-107">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="f6fb9-108">При отсутствии параметров уровня пула применяются параметры уровня сайта, если они заданы.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-108">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="f6fb9-109">Если на уровне сайта параметры также не заданы, ко всем собраниям применяются глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-109">If you do not define site-level settings, the global settings apply to all meetings.</span></span>

<div>

## <a name="to-create-new-meeting-join-settings"></a><span data-ttu-id="f6fb9-110">Создание новых параметров присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="f6fb9-110">To create new meeting join settings</span></span>

1.  <span data-ttu-id="f6fb9-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f6fb9-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f6fb9-113">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f6fb9-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f6fb9-114">На панели навигации слева выберите **Конференц** -связь, а затем — **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-114">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="f6fb9-115">На странице **Конфигурация собрания** нажмите кнопку **Создать**, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-115">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="f6fb9-p103">Чтобы создать политику уровня сайта, выберите вариант **Настройка сайта**. В поле поиска **Выбор сайта** частично или полностью введите имя сайта, для которого требуется определить параметры присоединения к собранию. В полученном списке сайтов выберите нужный сайт и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-p103">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="f6fb9-p104">Чтобы создать политику уровня пула, выберите вариант **Конфигурация пула**. В поле поиска **Выбор службы** частично или полностью введите имя службы пула, для которой требуется определить параметры присоединения к собранию. В полученном списке служб выберите нужную службу и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-p104">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="f6fb9-p105">Чтобы направлять участников, которые присоединяются к собранию через ТСОП, в "зал ожидания", снимите флажок **Абоненты ТСОП минуют зал ожидания**. По умолчанию участники, подключающиеся из ТСОП, могут сразу присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-p105">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>

6.  <span data-ttu-id="f6fb9-124">Чтобы настроить пользователей, которые могут быть выступающими, в разделе **Назначить в качестве выступающего** выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-124">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
      - <span data-ttu-id="f6fb9-125">Чтобы запретить назначение выступающими любых пользователей кроме организатора, выберите вариант **Нет**.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-125">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
      - <span data-ttu-id="f6fb9-p106">Чтобы разрешить быть выступающими только сотрудникам организации, выберите вариант **Компания**. Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-p106">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
      - <span data-ttu-id="f6fb9-128">Чтобы разрешить всем участникам быть выступающими, выберите вариант **Все**.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-128">To allow any participants to be a presenter, click **Everyone**.</span></span>

7.  <span data-ttu-id="f6fb9-p107">Чтобы оставить организатору возможность выбора типа конференции при планировании собрания, снимите флажок **Назначаемый тип конференции по умолчанию**. По умолчанию тип конференции назначается автоматически.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-p107">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>

8.  <span data-ttu-id="f6fb9-p108">Чтобы запретить автоматическое предоставление доступа анонимным (не прошедшим проверку подлинности) пользователям, снимите флажок **Допуск анонимных пользователей по умолчанию**. По умолчанию анонимные пользователи автоматически допускаются к собраниям.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-p108">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>

9.  <span data-ttu-id="f6fb9-133">Чтобы настроить отправку участникам приглашения на собрание, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-133">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="f6fb9-134">Обратите внимание, что максимальная длина URL-адресов и настраиваемых колонтитулов — 1 КБ.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-134">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="f6fb9-135">Если не указать значение для настроек, они не будут включены в собрание (кроме **URL-адреса справки**).</span><span class="sxs-lookup"><span data-stu-id="f6fb9-135">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="f6fb9-136">Если вы не включаете URL-адрес настраиваемой справки, в приглашении появится URL-адрес по умолчанию для Lync.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-136">If you do not include a custom help URL, the default help URL for Lync will be displayed in the invite.</span></span>
    
      - <span data-ttu-id="f6fb9-137">Чтобы настроить логотип, который отображается в приглашении на собрание, укажите местоположение логотипа в поле **URL-адрес логотипа**.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-137">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="f6fb9-138">В качестве логотипа необходимо использовать изображение формата GIF или JPG, имеющее размер 188 на 30 пикселей.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-138">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span>

        
        </div>
    
      - <span data-ttu-id="f6fb9-139">Чтобы настроить текст справки, который отображается в приглашении на собрание, введите расположение текста справки в поле **URL-адрес справки**.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-139">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
      - <span data-ttu-id="f6fb9-140">Чтобы настроить юридическую информацию, которая отображается в приглашении на собрание, укажите местоположение в поле **URL-адрес юридических сведений**.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-140">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
      - <span data-ttu-id="f6fb9-141">Чтобы настроить текст колонтитулов, которые отображаются в приглашении на собрание, введите текст в поле **Текст нижнего колонтитула**.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-141">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>

10. <span data-ttu-id="f6fb9-142">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-142">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a><span data-ttu-id="f6fb9-143">Изменение существующей коллекции конфигураций собраний</span><span class="sxs-lookup"><span data-stu-id="f6fb9-143">To modify an existing collection of meeting configurations</span></span>

1.  <span data-ttu-id="f6fb9-144">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-144">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f6fb9-145">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-145">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f6fb9-146">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f6fb9-146">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f6fb9-147">На панели навигации слева выберите **Конференц** -связь, а затем — **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-147">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="f6fb9-148">В списке конфигураций собрания выберите конфигурацию, которую необходимо изменить, щелкните **Изменить**, а затем выберите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-148">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="f6fb9-149">В области **Изменение конфигурации собрания** можно изменить любые параметры конфигурации, за исключением имени конфигурации, которое не подлежит изменению.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-149">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>

6.  <span data-ttu-id="f6fb9-150">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-150">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="f6fb9-151">Создание новых параметров конфигурации собрания с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f6fb9-151">Creating New Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="f6fb9-152">Можно создавать параметры конфигурации собраний (только в области сайта) с помощью Windows PowerShell и командлета New-Ксмитингконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-152">Meeting configuration settings can be created (at the site scope only) by using Windows PowerShell and the New-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="f6fb9-153">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-153">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="f6fb9-154">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-154">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="f6fb9-155">Создание параметров конфигурации собрания, использующих значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="f6fb9-155">To create meeting configuration settings that use the default values</span></span>

  - <span data-ttu-id="f6fb9-156">Эта команда создает новый набор параметров конфигурации собраний для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-156">This command creates a new set of meeting configuration settings for the Redmond site:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="f6fb9-157">Так как при выполнении предыдущей команды не были указаны никакие параметры (кроме обязательного параметра Identity), для всех свойств новых параметров конфигурации собраний будут использоваться значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-157">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a><span data-ttu-id="f6fb9-158">Изменение значения свойства при создании параметров конфигурации собрания</span><span class="sxs-lookup"><span data-stu-id="f6fb9-158">To change a property value when creating meeting configuration settings</span></span>

  - <span data-ttu-id="f6fb9-p112">Для создания настроек, использующих разные значения свойств, просто добавьте соответствующий параметр и значение параметра. Например, чтобы создать коллекцию параметров конфигурации собраний, которые по умолчанию допускают выступление всех участников на собрании, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="f6fb9-p112">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a><span data-ttu-id="f6fb9-161">Изменение нескольких значений свойства при создании параметров конфигурации собрания</span><span class="sxs-lookup"><span data-stu-id="f6fb9-161">To change multiple property values when creating meeting configuration settings</span></span>

  - <span data-ttu-id="f6fb9-162">Чтобы изменить несколько значений свойств, можно включить несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-162">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="f6fb9-163">Например, с помощью этой команды все участники собрания выдаются в качестве выступающего, и пользователи PSTN должны ждать в зале ожидания, пока они не будут формально собраны.</span><span class="sxs-lookup"><span data-stu-id="f6fb9-163">For example, this command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

<span data-ttu-id="f6fb9-164">Дополнительные сведения можно найти в разделе справки по командлету [New-ксмитингконфигуратион](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="f6fb9-164">For more information, see the help topic for the [New-CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

