---
title: 'Lync Server 2013: создание или изменение коллекции параметров конфигурации CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of CDR configuration settings
ms:assetid: c830be5a-2a82-468d-9c46-d3fec0f79fd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721878(v=OCS.15)
ms:contentKeyID: 49733812
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44ec5383a8050370ba259350aed4528765838b47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834811"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="3e728-102">Создание и изменение коллекции параметров конфигурации CDR в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e728-102">Create or modify a collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e728-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3e728-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3e728-p101">Регистрация вызовов (CDR) позволяет отслеживать использование таких возможностей, как сеансы однорангового обмена мгновенными сообщениями, телефонные звонки по протоколу VoIP и конференц-связь. Эти сведения об использовании включают информацию о том, кто и кому звонил, время и длительность звонков.</span><span class="sxs-lookup"><span data-stu-id="3e728-p101">Call detail recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="3e728-106">При установке Microsoft Lync Server 2013 создается единая глобальная коллекция параметров конфигурации CDR.</span><span class="sxs-lookup"><span data-stu-id="3e728-106">When you install Microsoft Lync Server 2013 a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="3e728-107">Администраторы также могут создавать особые параметры на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="3e728-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="3e728-108">Если такие параметры на уровне сайта используются, то они имеют преимущество перед глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="3e728-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="3e728-109">Например, если создаются параметры для сайта Redmond на уровне сайта, то эти параметры (а не глобальные параметры) будут использоваться для управления CDR на сайте Redmond.</span><span class="sxs-lookup"><span data-stu-id="3e728-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage CDR in Redmond.</span></span>

<span data-ttu-id="3e728-110">Вы можете создавать параметры конфигурации CDR с помощью либо панели управления Lync Server, либо командлета [New-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="3e728-110">You can create CDR configuration settings by using either Lync Server Control Panel or the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span> <span data-ttu-id="3e728-111">Вы можете использовать панель управления Lync Server или командлет [Set-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) для изменения существующих параметров.</span><span class="sxs-lookup"><span data-stu-id="3e728-111">You can use Lync Server Control Panel or the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet to modify existing settings.</span></span> <span data-ttu-id="3e728-112">Если вы используете панель управления Lync Server для создания и изменения параметров, вам будут доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="3e728-112">If you are using Lync Server Control Panel to create or modify settings, the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3e728-113">Параметр пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="3e728-113">UI Setting</span></span></th>
<th><span data-ttu-id="3e728-114">Параметр PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e728-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="3e728-115">Описание</span><span class="sxs-lookup"><span data-stu-id="3e728-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3e728-116">Имя</span><span class="sxs-lookup"><span data-stu-id="3e728-116">Name</span></span></p></td>
<td><p><span data-ttu-id="3e728-117">Identity</span><span class="sxs-lookup"><span data-stu-id="3e728-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="3e728-p104">Уникальный идентификатор создаваемых параметров конфигурации CDR. Эти параметры можно создавать только на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="3e728-p104">Unique identifier for the CDR configuration settings being created. These settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e728-120">Enable monitoring of CDRs (Включить мониторинг CDR)</span><span class="sxs-lookup"><span data-stu-id="3e728-120">Enable monitoring of CDRs</span></span></p></td>
<td><p><span data-ttu-id="3e728-121">EnableCDR</span><span class="sxs-lookup"><span data-stu-id="3e728-121">EnableCDR</span></span></p></td>
<td><p><span data-ttu-id="3e728-122">Указывает, включен ли CDR.</span><span class="sxs-lookup"><span data-stu-id="3e728-122">Indicates whether or not CDR is enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e728-123">Enable purging of CDRs (Включить очистку CDR)</span><span class="sxs-lookup"><span data-stu-id="3e728-123">Enable purging of CDRs</span></span></p></td>
<td><p><span data-ttu-id="3e728-124">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="3e728-124">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="3e728-125">Указывает, будут ли записи CDR периодически удаляться из базы данных CDR.</span><span class="sxs-lookup"><span data-stu-id="3e728-125">Indicates whether or not CDR records will periodically be deleted from the CDR database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3e728-126">Keep CDRs for maximum duration (days) (Сохранять CDR не более (дней))</span><span class="sxs-lookup"><span data-stu-id="3e728-126">Keep CDRs for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="3e728-127">KeepCallDetailForDays</span><span class="sxs-lookup"><span data-stu-id="3e728-127">KeepCallDetailForDays</span></span></p></td>
<td><p><span data-ttu-id="3e728-p105">Указывает число дней, в течение которых записи CDR должны храниться в базе данных CDR. Все записи старше указанного числа дней будут автоматически удаляться (обратите внимание, что удаление выполняется только при включении очистки).</span><span class="sxs-lookup"><span data-stu-id="3e728-p105">Indicates the number of days that CDR records will be kept in the CDR database. Any records older than the specified number of days will automatically be deleted. (Note that purging will take only place if purging has been enabled.)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3e728-131">Keep error report data for maximum duration (days) (Сохранять данные отчетов об ошибках не более (дней))</span><span class="sxs-lookup"><span data-stu-id="3e728-131">Keep error report data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="3e728-132">KeepErrorReportForDays</span><span class="sxs-lookup"><span data-stu-id="3e728-132">KeepErrorReportForDays</span></span></p></td>
<td><p><span data-ttu-id="3e728-p106">Указывает число дней, в течение которого сохраняются отчеты об ошибках CDR. Все отчеты старше указанного числа дней будут автоматически удаляться. Отчеты об ошибках CDR представляют собой диагностические отчеты, которые отправляют клиентские приложения.</span><span class="sxs-lookup"><span data-stu-id="3e728-p106">Indicates the number of days that CDR error reports are kept. Any reports older than the specified number of days will automatically be deleted. CDR error reports are diagnostic reports uploaded by client applications.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="3e728-136">Командлеты New-Кскдрконфигуратион и Set-Кскдрконфигуратион включают дополнительные параметры, недоступные на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e728-136">The New-CsCdrConfiguration and Set-CsCdrConfiguration cmdlets include additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="3e728-137">Для получения дополнительных сведений ознакомьтесь с разделами справки <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-кскдрконфигуратион</A> и <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-кскдрконфигуратион</A> .</span><span class="sxs-lookup"><span data-stu-id="3e728-137">See the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration">New-CsCdrConfiguration</A> and the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration">Set-CsCdrConfiguration</A> help topics for more information.</span></span>



</div>

<div>

## <a name="to-create-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="3e728-138">Создание параметров конфигурации CDR с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e728-138">To create CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3e728-139">На панели управления Lync Server откройте вкладку **наблюдение и архивация**.</span><span class="sxs-lookup"><span data-stu-id="3e728-139">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="3e728-140">На вкладке **запись сведений о звонке** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="3e728-140">On the **Call Detail Recording** tab, click **New**.</span></span>

3.  <span data-ttu-id="3e728-p108">В диалоговом окне **выбора сайта** выберите сайт, в котором должны быть созданы новые параметры конфигурации. Если диалоговое окно пустое, это означает, что всем вашим сайтам уже назначена коллекция параметров конфигурации CDR. На каждом сайте может быть только одна такая коллекция. В этом случае можно либо удалить параметры и создать их заново, либо просто изменить существующие параметры.</span><span class="sxs-lookup"><span data-stu-id="3e728-p108">In the **Select a Site** dialog box, select the site where the new configuration settings are to be created. If the dialog box is empty, that means all of your sites have already been assigned a collection of CDR configuration settings. Each site is limited to a single such collection. In that case you can either delete and then re-create the settings, or simply modify the existing settings.</span></span>

4.  <span data-ttu-id="3e728-145">В диалоговом окне **создания параметров регистрации вызовов (CDR)** установите необходимые флажки и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3e728-145">In the **New Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="to-modify-existing-cdr-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="3e728-146">Изменение существующих параметров конфигурации CDR с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="3e728-146">To modify existing CDR configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="3e728-147">На панели управления Lync Server откройте вкладку **наблюдение и архивация**.</span><span class="sxs-lookup"><span data-stu-id="3e728-147">In Lync Server Control Panel click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="3e728-148">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span><span class="sxs-lookup"><span data-stu-id="3e728-148">Double-click the collection of settings to be modified, or select the collection, click **Edit**, and then click **Show Details**.</span></span> <span data-ttu-id="3e728-149">Note that you can only modify a single collection at a time.</span><span class="sxs-lookup"><span data-stu-id="3e728-149">Note that you can only modify a single collection at a time.</span></span> <span data-ttu-id="3e728-150">Чтобы внести одни и те же изменения в несколько коллекций, вместо этого используйте командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="3e728-150">To make the same changes to multiple collections, use the Lync Server Management Shell instead.</span></span>

3.  <span data-ttu-id="3e728-151">В диалоговом окне **изменения параметров регистрации вызовов (CDR)** установите необходимые флажки и нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3e728-151">In the **Edit Call Detail Recording (CDR) Setting** dialog, make the desired selections and then click **Commit**.</span></span>

</div>

<div>

## <a name="creating-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3e728-152">Создание параметров конфигурации CDR с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3e728-152">Creating CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3e728-153">Вы также можете создавать параметры конфигурации CDR с помощью Windows PowerShell и командлета **New-кскдрконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="3e728-153">You can create CDR configuration settings can also be created by using Windows PowerShell and the **New-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="3e728-154">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e728-154">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3e728-155">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3e728-155">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="3e728-156">Создание новой коллекции параметров конфигурации CDR</span><span class="sxs-lookup"><span data-stu-id="3e728-156">To create a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="3e728-157">Следующая команда создает новую коллекцию параметров конфигурации CDR, относящуюся к сайту Redmond:</span><span class="sxs-lookup"><span data-stu-id="3e728-157">This command creates a new collection of CDR configuration settings applied to the Redmond site:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-collection-of-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="3e728-158">Создание коллекции параметров конфигурации CDR, которая отключает регистрацию вызовов</span><span class="sxs-lookup"><span data-stu-id="3e728-158">To create a collection of CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="3e728-p111">Поскольку в предыдущей команде не было указано никаких параметров, кроме обязательного параметра Identity, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств. Чтобы создать параметры, использующие другие значения свойств, просто включите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации CDR, которая по умолчанию отключает регистрацию вызовов, используйте команду, аналогичную следующей:</span><span class="sxs-lookup"><span data-stu-id="3e728-p111">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Call Detail configuration settings that, by default, allow disable Call Detail recording use a command like this:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-cdr-configuration-settings"></a><span data-ttu-id="3e728-162">Указание нескольких значений свойств при создании новой коллекции параметров конфигурации CDR</span><span class="sxs-lookup"><span data-stu-id="3e728-162">To specify multiple property values when creating a new collection of CDR configuration settings</span></span>

  - <span data-ttu-id="3e728-p112">Можно изменить несколько значений свойств, включив несколько параметров. Например, следующая команда настраивает новые параметры таким образом, чтобы записи CDR хранились 30 дней, а отчеты об ошибках 90 дней:</span><span class="sxs-lookup"><span data-stu-id="3e728-p112">You can modify multiple property values by including multiple parameters. For example, this command configures the new settings to keep Call Detail records for 30 days and error reports for 90 days:</span></span>
    
        New-CsCdrConfiguration -Identity "site:Redmond" -KeepCallDetailForDays 30 -KeepErrorReportForDays 90

</div>

<span data-ttu-id="3e728-165">Дополнительные сведения можно найти в разделе справки по командлету [New-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="3e728-165">For more information, see the help topic for the [New-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

