---
title: 'Lync Server 2013: Создание параметров конфигурации качества взаимодействия'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 947fb50c057fdcc04fe7d1b30d25bc8f5a5f4a02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834777"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="4d071-102">Создание параметров конфигурации качества взаимодействия в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4d071-102">Create Quality of Experience configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4d071-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4d071-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4d071-p101">Показатели качества взаимодействия отслеживают качество аудио- и видеозвонков в вашей организации, включая число потерянных сетевых пакетов, фоновый шум и объем "дрожания" (разницы задержки пакетов). Эти показатели хранятся в базе данных отдельно от других данных (таких как записи функции регистрации вызовов), что позволяет включать и отключать запись качества взаимодействия независимо записи других данных.</span><span class="sxs-lookup"><span data-stu-id="4d071-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>

<span data-ttu-id="4d071-106">При установке Microsoft Lync Server 2013 создается единая глобальная коллекция параметров конфигурации QoE.</span><span class="sxs-lookup"><span data-stu-id="4d071-106">When you install Microsoft Lync Server 2013, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="4d071-107">Администраторы также могут создавать особые параметры на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="4d071-107">Administrators also have the option of creating custom settings at the site scope.</span></span> <span data-ttu-id="4d071-108">При использовании эти параметров уровня сайта имеют приоритет над глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="4d071-108">Whenever these site-scoped settings are used, they take precedence over the global settings.</span></span> <span data-ttu-id="4d071-109">Например, если созданы параметры уровня сайта для сайта Redmond, именно эти, а не глобальные параметры будут использоваться для управления качеством взаимодействия в сайте Redmond.</span><span class="sxs-lookup"><span data-stu-id="4d071-109">For example, if you create site-scoped settings for the Redmond site then those settings (rather than the global settings) will be used to manage QoE in Redmond.</span></span>

<span data-ttu-id="4d071-110">Параметры конфигурации QoE можно создать с помощью панели управления Lync Server или командлета [New-кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="4d071-110">QoE configuration settings can be created by using either Lync Server Control Panel or the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span> <span data-ttu-id="4d071-111">Если вы используете панель управления Lync Server для создания новых параметров, вам будут доступны следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="4d071-111">If you are using Lync Server Control Panel to create new settings the following options will be available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4d071-112">Параметр пользовательского интерфейса</span><span class="sxs-lookup"><span data-stu-id="4d071-112">UI Setting</span></span></th>
<th><span data-ttu-id="4d071-113">Параметр PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d071-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="4d071-114">Описание</span><span class="sxs-lookup"><span data-stu-id="4d071-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4d071-115">Имя</span><span class="sxs-lookup"><span data-stu-id="4d071-115">Name</span></span></p></td>
<td><p><span data-ttu-id="4d071-116">Identity</span><span class="sxs-lookup"><span data-stu-id="4d071-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="4d071-p104">Уникальный идентификатор создаваемых параметров. Параметры конфигурации качества взаимодействия могут быть созданы только на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="4d071-p104">Unique identifier for the settings to be created. QoE configuration settings can only be created at the site scope.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d071-119">Разрешить отслеживание данных о качестве связи</span><span class="sxs-lookup"><span data-stu-id="4d071-119">Enable monitoring of QoE data</span></span></p></td>
<td><p><span data-ttu-id="4d071-120">EnableQoE</span><span class="sxs-lookup"><span data-stu-id="4d071-120">EnableQoE</span></span></p></td>
<td><p><span data-ttu-id="4d071-121">Указывает, будут ли записи качества взаимодействия собраны и сохранены в базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4d071-121">Specifies whether QoE records will be collected and saved to the monitoring database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4d071-122">Разрешить очистку данных о качестве связи</span><span class="sxs-lookup"><span data-stu-id="4d071-122">Enable purging of QoE data</span></span></p></td>
<td><p><span data-ttu-id="4d071-123">EnablePurging</span><span class="sxs-lookup"><span data-stu-id="4d071-123">EnablePurging</span></span></p></td>
<td><p><span data-ttu-id="4d071-124">Определяет, можно ли очищать записи после истечения периода времени, определенного в свойстве <strong>Хранить данные о качестве взаимодействия не дольше (дн.)</strong>.</span><span class="sxs-lookup"><span data-stu-id="4d071-124">Specifies whether records will be purged after the duration defined in the <strong>Keep QoE data for a maximum duration (days)</strong> property has elapsed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4d071-125">Хранить данные о качестве взаимодействия не дольше (дн.):</span><span class="sxs-lookup"><span data-stu-id="4d071-125">Keep QoE data for maximum duration (days)</span></span></p></td>
<td><p><span data-ttu-id="4d071-126">KeepQoEDataForDays</span><span class="sxs-lookup"><span data-stu-id="4d071-126">KeepQoEDataForDays</span></span></p></td>
<td><p><span data-ttu-id="4d071-p105">Число дней хранения данных о качестве взаимодействия до удаления из базы данных. Это значение игнорируется, если очистка отключена.</span><span class="sxs-lookup"><span data-stu-id="4d071-p105">Number of days QoE data will be stored before being purged from the database. This value is ignored if purging is disabled.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="4d071-129">Командлет New-Кскоеконфигуратион содержит дополнительные параметры, недоступные на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d071-129">The New-CsQoEConfiguration cmdlet includes additional options not available in Lync Server Control Panel.</span></span> <span data-ttu-id="4d071-130">Дополнительные сведения можно найти в разделе справки, посвященных <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">новым кскоеконфигуратион</A> .</span><span class="sxs-lookup"><span data-stu-id="4d071-130">For more information, see the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</A> help topic.</span></span>



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="4d071-131">Создание параметров конфигурации QoE с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="4d071-131">To create QoE configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="4d071-132">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4d071-132">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="4d071-133">Дополнительные сведения можно найти [в разделе Делегирование разрешений на настройку в Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="4d071-133">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="4d071-134">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4d071-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4d071-135">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4d071-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4d071-136">В левой панели навигации щелкните **Мониторинг и архивация** и затем выберите **Данные о качестве взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="4d071-136">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4.  <span data-ttu-id="4d071-137">На странице **Данные качества взаимодействия** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="4d071-137">On the **Quality of Experience Data** page, click **New**.</span></span>

5.  <span data-ttu-id="4d071-138">В разделе **Выбор сайта** щелкните сайт, к которому должна применяться эта политика, и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4d071-138">In **Select a Site**, click the site to which the policy is to be applied, and click **OK**.</span></span>

6.  <span data-ttu-id="4d071-139">На странице **Новый параметр качества обслуживания** сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="4d071-139">In **New Quality of Experience Setting**, do the following:</span></span>
    
      - <span data-ttu-id="4d071-140">Выберите пункт **Включить мониторинг данных качества обслуживания (CDR)**, чтобы включить мониторинг.</span><span class="sxs-lookup"><span data-stu-id="4d071-140">Select **Enable monitoring of QoE data** to turn on monitoring.</span></span>
    
      - <span data-ttu-id="4d071-141">Выберите пункт **Включить очистку данных качества обслуживания (CDR)**.</span><span class="sxs-lookup"><span data-stu-id="4d071-141">Select **Enable purging of QoE data** to turn on purging.</span></span>
    
      - <span data-ttu-id="4d071-142">В поле **Хранить записи сведений о звонках в течение (дней)** выберите максимальное количество дней, в течение которого должны храниться записи сведений о звонках.</span><span class="sxs-lookup"><span data-stu-id="4d071-142">In **Keep QoE for maximum duration (days)**, select the maximum number of days that QoE records should be retained.</span></span>

7.  <span data-ttu-id="4d071-143">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="4d071-143">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4d071-144">Создание параметров конфигурации QoE с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d071-144">Creating QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4d071-145">Вы можете создавать параметры конфигурации QoE с помощью Windows PowerShell и командлета New-Кскоеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="4d071-145">You can create QoE configuration settings by using Windows PowerShell and the New-CsQoEConfiguration cmdlet.</span></span> <span data-ttu-id="4d071-146">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d071-146">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4d071-147">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d071-147">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="4d071-148">Чтобы создать новую коллекцию параметров конфигурации качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="4d071-148">To create a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="4d071-149">Эта команда создает новую коллекцию параметров конфигурации качества взаимодействия, применяемую на сайте Redmond:</span><span class="sxs-lookup"><span data-stu-id="4d071-149">This command creates a new collection of QoE configuration settings applied to the Redmond site:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="4d071-150">Чтобы создать новую коллекцию параметров конфигурации качества взаимодействия при отключенном мониторинге качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="4d071-150">To create a new collection of QoE configuration settings where QoE monitoring is disabled</span></span>

  - <span data-ttu-id="4d071-p110">Так как никакие параметры (кроме обязательного параметра Identity) не были указаны в приведенных ранее командах, новая коллекция параметров конфигурации будет использовать значения по умолчанию для всех своих свойств. Чтобы создать параметры, использующие другие значения свойств просто включите соответствующий параметр и его значение. Например, чтобы создать коллекцию параметров конфигурации качества взаимодействия, которые, по умолчанию, разрешают отключать запись качества взаимодействия, используйте следующую команду:</span><span class="sxs-lookup"><span data-stu-id="4d071-p110">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties. To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of Quality of Experience configuration settings that, by default, allow disable QoE recording use a command like this:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a><span data-ttu-id="4d071-154">Чтобы указать значения нескольких свойств при создании новой коллекции параметров конфигурации качества взаимодействия</span><span class="sxs-lookup"><span data-stu-id="4d071-154">To specify multiple property values when creating a new collection of QoE configuration settings</span></span>

  - <span data-ttu-id="4d071-p111">Можно задать несколько значений свойств, включив несколько параметров. Например, эта команда настраивает новые параметры для сохранения данных качества взаимодействия в течение 30 дней и очистки старых данных в 3:00:</span><span class="sxs-lookup"><span data-stu-id="4d071-p111">You can multiple property values by including multiple parameters. For example, this command configures the new settings to keep QoE data for 30 days and to purge old data at 3:00 AM:</span></span>
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

<span data-ttu-id="4d071-157">Дополнительные сведения можно найти в разделе справки по командлету [New-кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="4d071-157">For more information, see the help topic for the [New-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

