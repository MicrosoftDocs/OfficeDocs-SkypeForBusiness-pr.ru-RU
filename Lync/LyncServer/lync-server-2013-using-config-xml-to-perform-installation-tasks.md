---
title: 'Lync Server 2013: использование файла config. XML для выполнения задач установки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b6b06b270157bc1aa2387662229dbff3eb8f4d5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a><span data-ttu-id="69061-102">Использование файла config. XML для выполнения задач установки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69061-102">Using Config.xml to perform installation tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69061-103">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="69061-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="69061-p101">Хотя Центр развертывания Office является основным средством настраиваемой установки, администраторы могут использовать файл Config.xml, чтобы задать для установки дополнительные инструкции, недоступные в Центре развертывания Office. Следующие настройки выполнимы только с помощью файла Config.xml:</span><span class="sxs-lookup"><span data-stu-id="69061-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

  - <span data-ttu-id="69061-106">задание пути для точки сетевой установки;</span><span class="sxs-lookup"><span data-stu-id="69061-106">Specify the path of the network installation point.</span></span>

  - <span data-ttu-id="69061-107">выбор устанавливаемых продуктов;</span><span class="sxs-lookup"><span data-stu-id="69061-107">Select the products to install.</span></span>

  - <span data-ttu-id="69061-108">настройка ведения журнала и местоположения файла настроек установки и обновлений ПО;</span><span class="sxs-lookup"><span data-stu-id="69061-108">Configure logging and the location of the Setup customization file and software updates.</span></span>

  - <span data-ttu-id="69061-109">задание параметров установки, таких как имя пользователя;</span><span class="sxs-lookup"><span data-stu-id="69061-109">Specify installation options, such as user name.</span></span>

  - <span data-ttu-id="69061-110">копирование локального источника установки на компьютер пользователя без установки Office;</span><span class="sxs-lookup"><span data-stu-id="69061-110">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

  - <span data-ttu-id="69061-111">Добавление или удаление устанавливаемых языков.</span><span class="sxs-lookup"><span data-stu-id="69061-111">Add or remove languages from the installation.</span></span>

<span data-ttu-id="69061-112">Рекомендуется использовать файл config. XML для настройки автоматической установки Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="69061-112">We recommend that you use the Config.xml file to configure Lync 2013 silent installation.</span></span>

<span data-ttu-id="69061-113">По умолчанию файл config. XML, хранящийся в основной папке продукта (например, \\Product. WW) направляет программу установки для установки этого продукта.</span><span class="sxs-lookup"><span data-stu-id="69061-113">By default, the Config.xml file that is stored in the core product folder (for example, \\product.WW) directs Setup to install that product.</span></span> <span data-ttu-id="69061-114">Например, файл config. XML в следующей папке устанавливает Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="69061-114">For example, the Config.xml file in the following folder installs Lync 2013:</span></span>

  - <span data-ttu-id="69061-115">\\\\Общий\\доступ\\к\\серверу Lync15 Lync \\. WW config. XML</span><span class="sxs-lookup"><span data-stu-id="69061-115">\\\\server\\share\\Lync15\\Lync.WW \\Config.xml</span></span>

<span data-ttu-id="69061-116">Элементы config. XML, наиболее часто используемые для установки Lync 2013, перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="69061-116">The Config.xml elements most commonly used for Lync 2013 installation are listed in the following table.</span></span>

### <a name="configxml-elements"></a><span data-ttu-id="69061-117">Элементы Config.xml</span><span class="sxs-lookup"><span data-stu-id="69061-117">Config.xml elements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="69061-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="69061-118">Element</span></span></th>
<th><span data-ttu-id="69061-119">Описание</span><span class="sxs-lookup"><span data-stu-id="69061-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="69061-120">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="69061-120">Configuration</span></span></p></td>
<td><p><span data-ttu-id="69061-p103">Элемент верхнего уровня (обязательный). Содержит атрибут Product, например: Product=Lync</span><span class="sxs-lookup"><span data-stu-id="69061-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69061-123">OptionState</span><span class="sxs-lookup"><span data-stu-id="69061-123">OptionState</span></span></p></td>
<td><p><span data-ttu-id="69061-124">Определяет, как при установке будут обрабатываться компоненты конкретного продукта.</span><span class="sxs-lookup"><span data-stu-id="69061-124">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="69061-125">Используйте следующие атрибуты для предотвращения установки служб Business Connectivity Services, в том числе общих компонентов, которые мешают работе с Outlook 2010:</span><span class="sxs-lookup"><span data-stu-id="69061-125">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2010:</span></span></p>
<ul>
<li><p><span data-ttu-id="69061-126">ID =&quot;лобимаин&quot;</span><span class="sxs-lookup"><span data-stu-id="69061-126">Id=&quot;LOBiMain&quot;</span></span></p></li>
<li><p><span data-ttu-id="69061-127">State =&quot;отсутствует&quot;</span><span class="sxs-lookup"><span data-stu-id="69061-127">State=&quot;Absent&quot;</span></span></p></li>
<li><p><span data-ttu-id="69061-128">Дети =&quot;Force&quot;</span><span class="sxs-lookup"><span data-stu-id="69061-128">Children=&quot;Force&quot;</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69061-129">Display</span><span class="sxs-lookup"><span data-stu-id="69061-129">Display</span></span></p></td>
<td><p><span data-ttu-id="69061-p105">Уровень пользовательского интерфейса, отображаемого пользователю программой установки. Обычно используются следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="69061-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="69061-132">CompletionNotice =&quot;да&quot; | &quot;нет&quot;(по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="69061-132">CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
<li><p><span data-ttu-id="69061-133">AcceptEula =&quot;да&quot; | &quot;нет&quot;(по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="69061-133">AcceptEula=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69061-134">Ведение журнала</span><span class="sxs-lookup"><span data-stu-id="69061-134">Logging</span></span></p></td>
<td><p><span data-ttu-id="69061-p106">Параметры ведения журнала программой установки. Обычно используются следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="69061-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="69061-137">Тип&quot; | =&quot;&quot;Standard&quot;(по умолчанию) | &quot;Подробные сведения&quot;</span><span class="sxs-lookup"><span data-stu-id="69061-137">Type =&quot;Off&quot; | &quot;Standard&quot;(default) | &quot;Verbose&quot;</span></span></p></li>
<li><p><span data-ttu-id="69061-138">Template=”имя файла.txt” (имя файла журнала)</span><span class="sxs-lookup"><span data-stu-id="69061-138">Template=”filename.txt” (the name of the log file)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="69061-139">Параметр</span><span class="sxs-lookup"><span data-stu-id="69061-139">Setting</span></span></p></td>
<td><p><span data-ttu-id="69061-p107">Определяет значения для свойств программы установщика Windows. Обычно используются следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="69061-p107">Specifies values for Windows Installer properties. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="69061-142">Параметр ID =&quot;Name&quot; (имя свойства установщика Windows)</span><span class="sxs-lookup"><span data-stu-id="69061-142">Setting Id=&quot;name&quot; (the name of the Windows Installer property)</span></span></p></li>
<li><p><span data-ttu-id="69061-143">Значение =&quot;значение&quot; (значение, присваиваемое свойству)</span><span class="sxs-lookup"><span data-stu-id="69061-143">Value=&quot;value&quot; (the value to assign to the property)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="69061-144">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="69061-144">DistributionPoint</span></span></p></td>
<td><p><span data-ttu-id="69061-p108">Полный доменный путь точки сетевой установки, из которой запускается установка. Содержит атрибут Location:</span><span class="sxs-lookup"><span data-stu-id="69061-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="69061-147">Location = "путь"</span><span class="sxs-lookup"><span data-stu-id="69061-147">Location=”path”</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="69061-148">В следующем примере показан файл config. XML для типичной автоматической установки Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="69061-148">The following example shows a Config.xml file for a typical silent installation of Lync 2013.</span></span>

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

<span data-ttu-id="69061-149">Подробные сведения об использовании файла config. XML для выполнения задач установки и обслуживания Office доступны по адресу <https://go.microsoft.com/fwlink/p/?linkid=267514>.</span><span class="sxs-lookup"><span data-stu-id="69061-149">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at <https://go.microsoft.com/fwlink/p/?linkid=267514>.</span></span>

<div>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="69061-150">Изменение файла Config.xml</span><span class="sxs-lookup"><span data-stu-id="69061-150">To customize the Config.xml file</span></span>

1.  <span data-ttu-id="69061-151">Откройте файл Config.xml с помощью текстового редактора, такого как "Блокнот".</span><span class="sxs-lookup"><span data-stu-id="69061-151">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2.  <span data-ttu-id="69061-152">Найдите строки, содержащие элементы, которые нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="69061-152">Locate the lines that contain the elements you want to change.</span></span>

3.  <span data-ttu-id="69061-153">Измените запись для элемента, используя нужные значения параметров автоматической установки.</span><span class="sxs-lookup"><span data-stu-id="69061-153">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="69061-154">Убедитесь, что вы удалили разделители комментариев, "\<\!–" и "–\>".</span><span class="sxs-lookup"><span data-stu-id="69061-154">Make sure that you remove the comment delimiters, "\<\!--" and "--\>".</span></span> <span data-ttu-id="69061-155">Например, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="69061-155">For example, use the following syntax:</span></span>
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  <span data-ttu-id="69061-156">Сохраните файл Config.xml.</span><span class="sxs-lookup"><span data-stu-id="69061-156">Save the Config.xml file.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

