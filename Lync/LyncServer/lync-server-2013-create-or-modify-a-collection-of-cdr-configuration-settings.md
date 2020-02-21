---
title: 'Lync Server 2013: создание или изменение коллекции параметров конфигурации CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 828c02e11d9e5adfe7028dd8d224c10df14c2247
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190472"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="fef49-102">Создание или изменение коллекции параметров конфигурации CDR в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fef49-102">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fef49-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="fef49-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="fef49-p101">Регистрация вызовов (CDR) позволяет отслеживать использование таких возможностей, как сеансы однорангового обмена мгновенными сообщениями, телефонные звонки по протоколу VoIP и конференц-связь. Эти сведения об использовании включают информацию о том, кто и кому звонил, время и длительность звонков.</span><span class="sxs-lookup"><span data-stu-id="fef49-p101">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="fef49-106">При установке Microsoft Lync Server 2013 создается отдельная глобальная коллекция параметров конфигурации CDR.</span><span class="sxs-lookup"><span data-stu-id="fef49-106">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="fef49-107">Администраторы также имеют возможность создания пользовательских параметров на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="fef49-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="fef49-108">При использовании эти параметров уровня сайта имеют приоритет над глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="fef49-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="fef49-109">Например, если вы создаете параметры уровня сайта для сайта Redmond, то эти параметры (а не глобальные параметры) будут использоваться для управления CDR в Редмонде.</span><span class="sxs-lookup"><span data-stu-id="fef49-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="fef49-110">Параметры конфигурации CDR можно создать с помощью панели управления Lync Server или командлета [New – CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="fef49-110">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="fef49-111">С помощью панели управления Lync Server или командлета [Set – CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) можно изменять существующие параметры.</span><span class="sxs-lookup"><span data-stu-id="fef49-111">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="fef49-112">Если вы используете панель управления Lync Server для создания или изменения параметров, будут доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="fef49-112">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fef49-113">Параметр пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="fef49-113">UI Setting</span></span></th>
<th><span data-ttu-id="fef49-114">Параметр PowerShell</span><span class="sxs-lookup"><span data-stu-id="fef49-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="fef49-115">Описание</span><span class="sxs-lookup"><span data-stu-id="fef49-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fef49-116">Имя</span><span class="sxs-lookup"><span data-stu-id="fef49-116">Name</span></span></p></td>
<td><p><span data-ttu-id="fef49-117">Удостоверение</span><span class="sxs-lookup"><span data-stu-id="fef49-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="fef49-118">Уникальный идентификатор создаваемых параметров конфигурации CDR.</span><span class="sxs-lookup"><span data-stu-id="fef49-118">Unique identifier for the CDR configuration settings being created.</span></span> <span data-ttu-id="fef49-119">Эти параметры можно создавать только на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="fef49-119">These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef49-120">Включение мониторинга CDRs</span><span class="sxs-lookup"><span data-stu-id="fef49-120">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="fef49-121">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="fef49-121">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="fef49-122">Указывает, включен ли мониторинг регистрации вызовов (CDR).</span><span class="sxs-lookup"><span data-stu-id="fef49-122">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef49-123">Включение очистки CDRs</span><span class="sxs-lookup"><span data-stu-id="fef49-123">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="fef49-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="fef49-124">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="fef49-125">Указывает, будут ли записи CDR периодически удаляться из базы данных CDR.</span><span class="sxs-lookup"><span data-stu-id="fef49-125">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fef49-126">Хранить CDRs для максимальной продолжительности (дней)</span><span class="sxs-lookup"><span data-stu-id="fef49-126">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="fef49-127">кипкаллдетаилфордайс</span><span class="sxs-lookup"><span data-stu-id="fef49-127">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="fef49-128">Указывает количество дней, в течение которых записи CDR будут храниться в базе данных CDR.</span><span class="sxs-lookup"><span data-stu-id="fef49-128">Indicates the number of days that CDR records will be kept in the CDR database.</span></span> <span data-ttu-id="fef49-129">Все записи старше указанного числа дней будут автоматически удалены.</span><span class="sxs-lookup"><span data-stu-id="fef49-129">Any records older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="fef49-130">(Обратите внимание на то, что очистка будет выполняться только в том случае, если очистка включена.)</span><span class="sxs-lookup"><span data-stu-id="fef49-130">(Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fef49-131">Хранить данные отчета об ошибках для максимальной длительности (дней)</span><span class="sxs-lookup"><span data-stu-id="fef49-131">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="fef49-132">киперроррепортфордайс</span><span class="sxs-lookup"><span data-stu-id="fef49-132">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="fef49-133">Указывает количество дней, в течение которых хранятся отчеты об ошибках CDR.</span><span class="sxs-lookup"><span data-stu-id="fef49-133">Indicates the number of days that CDR error reports are kept.</span></span> <span data-ttu-id="fef49-134">Все отчеты старше указанного числа дней будут автоматически удалены.</span><span class="sxs-lookup"><span data-stu-id="fef49-134">Any reports older than the specified number of days will automatically be deleted.</span></span> <span data-ttu-id="fef49-135">Отчеты об ошибках CDR — это диагностические отчеты, отправляемые клиентскими приложениями.</span><span class="sxs-lookup"><span data-stu-id="fef49-135">CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="fef49-136">Командлеты New – CsCdrConfiguration и Set – CsCdrConfiguration включают дополнительные параметры, недоступные в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fef49-136">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="fef49-137">Для получения дополнительных сведений просмотрите разделы справки <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New – CsCdrConfiguration</A> и <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set – CsCdrConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="fef49-137">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="fef49-138">Создание параметров конфигурации CDR с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="fef49-138">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fef49-139">В панели управления Lync Server щелкните **мониторинг и архивация**.</span><span class="sxs-lookup"><span data-stu-id="fef49-139">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="fef49-140">На вкладке **Регистрация вызовов** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="fef49-140">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="fef49-141">В диалоговом окне **Выбор сайта** выберите сайт, в котором будут созданы новые параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="fef49-141">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created.</span></span> <span data-ttu-id="fef49-142">Если диалоговое окно пусто, это означает, что всем сайтам уже назначена коллекция параметров конфигурации CDR.</span><span class="sxs-lookup"><span data-stu-id="fef49-142">If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings.</span></span> <span data-ttu-id="fef49-143">Каждый сайт может иметь только одну такую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="fef49-143">Each site is limited to a single such collection.</span></span> <span data-ttu-id="fef49-144">В этом случае можно либо удалить, либо повторно создать параметры, или просто изменить существующие параметры.</span><span class="sxs-lookup"><span data-stu-id="fef49-144">In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="fef49-145">В диалоговом окне **новый параметр записи сведений о вызовах (CDR)** выберите нужные параметры и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fef49-145">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="fef49-146">Изменение существующих параметров конфигурации CDR с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="fef49-146">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="fef49-147">В панели управления Lync Server щелкните **мониторинг и архивация**.</span><span class="sxs-lookup"><span data-stu-id="fef49-147">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="fef49-148">Дважды щелкните изменяемую коллекцию параметров или выберите коллекцию, нажмите кнопку **изменить**, а затем щелкните **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="fef49-148">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="fef49-149">Обратите внимание на то, что вы можете изменять только одну коллекцию за раз.</span><span class="sxs-lookup"><span data-stu-id="fef49-149">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="fef49-150">Чтобы внести одни и те же изменения в несколько коллекций, используйте командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fef49-150">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="fef49-151">В диалоговом окне **изменение параметров записи сведений о вызовах (CDR)** выберите нужные параметры и нажмите кнопку **сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fef49-151">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="fef49-152">Создание параметров конфигурации CDR с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fef49-152">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="fef49-153">Вы также можете создать параметры конфигурации CDR с помощью Windows PowerShell и командлета **New – CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="fef49-153">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="fef49-154">Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="fef49-154">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="fef49-155">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="fef49-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="fef49-156">Создание новой коллекции параметров конфигурации CDR</span><span class="sxs-lookup"><span data-stu-id="fef49-156">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="fef49-157">Эта команда создает новую коллекцию параметров конфигурации CDR, применяемых к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="fef49-157">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="fef49-158">Создание коллекции параметров конфигурации CDR, которые отключают регистрацию вызовов</span><span class="sxs-lookup"><span data-stu-id="fef49-158">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="fef49-159">Поскольку в предыдущей команде не было указано никаких параметров, кроме обязательного параметра Identity, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств.</span><span class="sxs-lookup"><span data-stu-id="fef49-159">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> <span data-ttu-id="fef49-160">Чтобы создать параметры, использующие другие значения свойств, просто включите соответствующий параметр и его значение.</span><span class="sxs-lookup"><span data-stu-id="fef49-160">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="fef49-161">Например, чтобы создать коллекцию параметров конфигурации сведений о вызовах, которые по умолчанию позволяют отключить регистрацию сведений о вызовах, используйте команду следующим образом:</span><span class="sxs-lookup"><span data-stu-id="fef49-161">For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="fef49-162">Указание нескольких значений свойств при создании новой коллекции параметров конфигурации CDR</span><span class="sxs-lookup"><span data-stu-id="fef49-162">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="fef49-163">Можно изменить несколько значений свойств, включив несколько параметров.</span><span class="sxs-lookup"><span data-stu-id="fef49-163">You can modify multiple property values by including multiple parameters.</span></span> <span data-ttu-id="fef49-164">Например, эта команда настраивает новые параметры для сохранения записей о вызовах в течение 30 дней и отчетов об ошибках в течение 90 дней:</span><span class="sxs-lookup"><span data-stu-id="fef49-164">For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="fef49-165">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [New – CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="fef49-165">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

