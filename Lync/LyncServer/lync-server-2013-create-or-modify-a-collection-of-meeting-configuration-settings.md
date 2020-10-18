---
title: Создание или изменение коллекции параметров конфигурации собраний
description: Создание или изменение коллекции параметров конфигурации собраний.
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
ms.openlocfilehash: 51dd68b3d149e5a96628fc3343d0d7eb3ae8020d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578245"
---
# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="71878-103">Создание или изменение коллекции параметров конфигурации собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71878-103">Create or modify a collection of meeting configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71878-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="71878-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="71878-105">Вы можете использовать параметры на странице Конфигурация собрания, чтобы определить различные характеристики интерфейса присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="71878-105">You can use the settings on the Meeting Configuration page to define various characteristics of the meeting join experience.</span></span> <span data-ttu-id="71878-106">По умолчанию этот порядок определяют глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="71878-106">By default, the global settings define the join experience.</span></span> <span data-ttu-id="71878-107">Однако можно создать параметры уровня сайта и пула.</span><span class="sxs-lookup"><span data-stu-id="71878-107">You can also create site-level and pool-level meeting join settings.</span></span> <span data-ttu-id="71878-108">При создании параметров уровня пула эти параметры применяются ко всем собраниям, размещенным в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="71878-108">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="71878-109">В отсутствие параметров уровня пула применяются параметры уровня сайта (при наличии).</span><span class="sxs-lookup"><span data-stu-id="71878-109">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="71878-110">Если параметры уровня сайта также не заданы, ко всем собраниям применяются глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="71878-110">If you do not define site-level settings, the global settings apply to all meetings.</span></span>

<div>

## <a name="to-create-new-meeting-join-settings"></a><span data-ttu-id="71878-111">Создание параметров присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="71878-111">To create new meeting join settings</span></span>

1.  <span data-ttu-id="71878-112">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="71878-112">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="71878-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="71878-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="71878-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="71878-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="71878-115">В левой панели навигации последовательно нажмите пункты **Conferencing (Конференц-связь)** и **Meeting Configuration (Конфигурация собрания)**.</span><span class="sxs-lookup"><span data-stu-id="71878-115">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="71878-116">На странице **конфигурации собрания** нажмите **New (Создать)**, а затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="71878-116">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="71878-p103">Чтобы создать политику на уровне узла, выберите пункт **Site configuration (Конфигурация узла)**. В поле поиска **Select a Site (Выбор узла)** введите имя (или часть имени) узла, для которого требуется определить параметры присоединения к собранию. В появившемся списке узлов выберите нужный и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="71878-p103">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="71878-p104">Чтобы создать политику уровня пула, выберите вариант **Pool configuration** (Настройка пула). В поле поиска **Выберите службу** введите часть или полное имя службы пула, для которой требуется определить параметры присоединения к собранию. В полученном списке служб выберите нужную службу и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="71878-p104">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="71878-p105">Чтобы направлять участников, которые присоединяются к собранию через ТСОП, в "зал ожидания", снимите флажок **PSTN callers bypass lobby** (Обход "зала ожидания" для абонентов ТСОП). По умолчанию участники, подключающиеся из ТСОП, могут сразу присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="71878-p105">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>

6.  <span data-ttu-id="71878-125">Чтобы настроить пользователей, которые могут быть выступающими, в разделе **Designate as presenter** (Назначить выступающим) выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="71878-125">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
      - <span data-ttu-id="71878-126">Чтобы запретить назначение выступающими любых пользователей кроме организатора, выберите вариант **Нет**.</span><span class="sxs-lookup"><span data-stu-id="71878-126">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
      - <span data-ttu-id="71878-p106">Чтобы разрешить быть выступающими только сотрудникам организации, выберите вариант **Компания**. Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="71878-p106">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
      - <span data-ttu-id="71878-129">Чтобы разрешить всем участникам быть выступающими, выберите вариант **Все**.</span><span class="sxs-lookup"><span data-stu-id="71878-129">To allow any participants to be a presenter, click **Everyone**.</span></span>

7.  <span data-ttu-id="71878-p107">Чтобы настроить для организатора возможность выбора типа конференции при планировании собрания, снимите флажок **Assigned conference type by default** (Назначение типа конференции по умолчанию). По умолчанию тип конференции назначается автоматически.</span><span class="sxs-lookup"><span data-stu-id="71878-p107">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>

8.  <span data-ttu-id="71878-p108">Чтобы запретить автоматическое предоставление доступа анонимным (не прошедшим проверку подлинности) пользователям, снимите флажок **Admit anonymous users by default** (Допускать анонимных пользователей по умолчанию). По умолчанию анонимные пользователи автоматически допускаются к собраниям.</span><span class="sxs-lookup"><span data-stu-id="71878-p108">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>

9.  <span data-ttu-id="71878-134">Чтобы настроить приглашение на собрание, отправленное участникам, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="71878-134">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="71878-135">Обратите внимание, что максимальная длина для URL-адресов и настраиваемого текста нижнего колонтитула — 1 КБ.</span><span class="sxs-lookup"><span data-stu-id="71878-135">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="71878-136">Если не указать значение для настроек, кроме **URL-адреса справки**, они не будут включены в собрание.</span><span class="sxs-lookup"><span data-stu-id="71878-136">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="71878-137">Если вы не включили URL-адрес настраиваемой справки, в приглашении будет отображаться URL-адрес справки по умолчанию для Lync.</span><span class="sxs-lookup"><span data-stu-id="71878-137">If you do not include a custom help URL, the default help URL for Lync will be displayed in the invite.</span></span>
    
      - <span data-ttu-id="71878-138">Чтобы настроить эмблему, которая отображается в приглашении на собрание, введите расположение логотипа в поле **URL-адрес логотипа**.</span><span class="sxs-lookup"><span data-stu-id="71878-138">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span>
        
        <div>
        

        > [!NOTE]
        > <span data-ttu-id="71878-139">Логотип должен представлять собой изображение в формате GIF или JPG с размером 188 на 30 пикселей.</span><span class="sxs-lookup"><span data-stu-id="71878-139">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span>

        
        </div>
    
      - <span data-ttu-id="71878-140">Чтобы настроить текст справки, который отображается в приглашении на собрание, введите расположение текста справки в поле **URL-адрес**справки.</span><span class="sxs-lookup"><span data-stu-id="71878-140">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
      - <span data-ttu-id="71878-141">Чтобы настроить юридический текст, отображаемый в приглашении на собрание, введите в поле **URL-адрес юридического**текста место для юридического текста.</span><span class="sxs-lookup"><span data-stu-id="71878-141">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
      - <span data-ttu-id="71878-142">Чтобы настроить текст нижнего колонтитула, который отображается в приглашении на собрание, введите текст в поле **текст нижнего колонтитула**.</span><span class="sxs-lookup"><span data-stu-id="71878-142">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>

10. <span data-ttu-id="71878-143">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="71878-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a><span data-ttu-id="71878-144">Изменение существующей коллекции конфигураций собраний</span><span class="sxs-lookup"><span data-stu-id="71878-144">To modify an existing collection of meeting configurations</span></span>

1.  <span data-ttu-id="71878-145">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="71878-145">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="71878-146">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="71878-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="71878-147">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="71878-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="71878-148">На левой панели навигации щелкните **Conferencing** (Конференц-связь), а затем **Meeting Configuration** (Конфигурация собрания).</span><span class="sxs-lookup"><span data-stu-id="71878-148">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="71878-149">В списке конфигураций собрания выберите конфигурацию, которую требуется изменить, нажмите кнопку **изменить**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="71878-149">In the list of meeting configurations, click the configuration that you want to change, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="71878-150">В разделе **изменение конфигурации собрания**измените любые параметры конфигурации, за исключением имени конфигурации, которое не может быть изменено.</span><span class="sxs-lookup"><span data-stu-id="71878-150">In **Edit Meeting Configuration**, modify any of the configuration settings, except for the configuration name, which cannot be modified.</span></span>

6.  <span data-ttu-id="71878-151">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="71878-151">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="71878-152">Создание новых параметров конфигурации собраний с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="71878-152">Creating New Meeting Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="71878-153">Параметры конфигурации собраний можно создать (только на уровне сайта) с помощью Windows PowerShell и командлета New-CsMeetingConfiguration.</span><span class="sxs-lookup"><span data-stu-id="71878-153">Meeting configuration settings can be created (at the site scope only) by using Windows PowerShell and the New-CsMeetingConfiguration cmdlet.</span></span> <span data-ttu-id="71878-154">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71878-154">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="71878-155">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="71878-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a><span data-ttu-id="71878-156">Создание параметров конфигурации собраний, в которых используются значения по умолчанию</span><span class="sxs-lookup"><span data-stu-id="71878-156">To create meeting configuration settings that use the default values</span></span>

  - <span data-ttu-id="71878-157">Эта команда создает новый набор параметров конфигурации собрания для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="71878-157">This command creates a new set of meeting configuration settings for the Redmond site:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    <span data-ttu-id="71878-158">Так как в предыдущей команде не были указаны никакие параметры (кроме обязательного параметра Identity), новые параметры конфигурации собрания будут использовать значения по умолчанию для всех свойств.</span><span class="sxs-lookup"><span data-stu-id="71878-158">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a><span data-ttu-id="71878-159">Изменение значения свойства при создании параметров конфигурации собраний</span><span class="sxs-lookup"><span data-stu-id="71878-159">To change a property value when creating meeting configuration settings</span></span>

  - <span data-ttu-id="71878-160">Чтобы создать параметры, использующие другие значения свойств, просто включите соответствующий параметр и его значение.</span><span class="sxs-lookup"><span data-stu-id="71878-160">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="71878-161">Например, чтобы создать коллекцию параметров конфигурации собраний, которые по умолчанию допускают всех участников собрания в качестве докладчика, выполните команду следующим образом:</span><span class="sxs-lookup"><span data-stu-id="71878-161">For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a><span data-ttu-id="71878-162">Изменение значений нескольких свойств при создании параметров конфигурации собраний</span><span class="sxs-lookup"><span data-stu-id="71878-162">To change multiple property values when creating meeting configuration settings</span></span>

  - <span data-ttu-id="71878-163">Чтобы изменить несколько значений свойств, можно включить несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="71878-163">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="71878-164">Например, эта команда раздает всем участникам собрания как докладчика, а также предписывает пользователям PSTN ждать в зале ожидания, пока они формально не подаются на собрание:</span><span class="sxs-lookup"><span data-stu-id="71878-164">For example, this command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

<span data-ttu-id="71878-165">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [New – CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) .</span><span class="sxs-lookup"><span data-stu-id="71878-165">For more information, see the help topic for the [New-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

