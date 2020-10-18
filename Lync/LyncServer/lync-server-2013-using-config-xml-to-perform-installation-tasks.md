---
title: 'Lync Server 2013: использование Config.xml для выполнения задач установки'
description: 'Lync Server 2013: использование Config.xml для выполнения задач установки.'
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
ms.openlocfilehash: 22fff14e21a120c3a0ee2cd6432fd1eba2bbee5f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580405"
---
# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a><span data-ttu-id="6d01d-103">Использование Config.xml для выполнения задач установки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6d01d-103">Using Config.xml to perform installation tasks in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d01d-104">_**Последнее изменение темы:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6d01d-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6d01d-p101">Хотя Центр развертывания Office является основным средством настраиваемой установки, администраторы могут использовать файл Config.xml, чтобы задать для установки дополнительные инструкции, недоступные в Центре развертывания Office. Следующие настройки выполнимы только с помощью файла Config.xml:</span><span class="sxs-lookup"><span data-stu-id="6d01d-p101">Although the Office Customization Tool (OCT) is the primary tool for customization installation, administrators can use the Config.xml file to specify additional installation instructions that are not available in the OCT. The following customizations can only be made by using the Config.xml file:</span></span>

  - <span data-ttu-id="6d01d-107">задание пути для точки сетевой установки;</span><span class="sxs-lookup"><span data-stu-id="6d01d-107">Specify the path of the network installation point.</span></span>

  - <span data-ttu-id="6d01d-108">выбор устанавливаемых продуктов;</span><span class="sxs-lookup"><span data-stu-id="6d01d-108">Select the products to install.</span></span>

  - <span data-ttu-id="6d01d-109">настройка ведения журнала и местоположения файла настроек установки и обновлений ПО;</span><span class="sxs-lookup"><span data-stu-id="6d01d-109">Configure logging and the location of the Setup customization file and software updates.</span></span>

  - <span data-ttu-id="6d01d-110">задание параметров установки, таких как имя пользователя;</span><span class="sxs-lookup"><span data-stu-id="6d01d-110">Specify installation options, such as user name.</span></span>

  - <span data-ttu-id="6d01d-111">копирование локального источника установки на компьютер пользователя без установки Office;</span><span class="sxs-lookup"><span data-stu-id="6d01d-111">Copy the local installation source (LIS) to the user's computer without installing Office.</span></span>

  - <span data-ttu-id="6d01d-112">Добавление или удаление устанавливаемых языков.</span><span class="sxs-lookup"><span data-stu-id="6d01d-112">Add or remove languages from the installation.</span></span>

<span data-ttu-id="6d01d-113">Рекомендуется использовать файл Config.xml для настройки автоматической установки Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6d01d-113">We recommend that you use the Config.xml file to configure Lync 2013 silent installation.</span></span>

<span data-ttu-id="6d01d-114">По умолчанию файл Config.xml, хранящийся в основной папке продукта (например, \\ Product. WW) направляет программу установки для установки этого продукта.</span><span class="sxs-lookup"><span data-stu-id="6d01d-114">By default, the Config.xml file that is stored in the core product folder (for example, \\product.WW) directs Setup to install that product.</span></span> <span data-ttu-id="6d01d-115">Например, файл Config.xml в следующей папке устанавливает Lync 2013:</span><span class="sxs-lookup"><span data-stu-id="6d01d-115">For example, the Config.xml file in the following folder installs Lync 2013:</span></span>

  - <span data-ttu-id="6d01d-116">\\\\\\общий доступ к серверу \\ Lync15 \\ Lync. WW \\Config.xml</span><span class="sxs-lookup"><span data-stu-id="6d01d-116">\\\\server\\share\\Lync15\\Lync.WW \\Config.xml</span></span>

<span data-ttu-id="6d01d-117">Элементы Config.xml, наиболее часто используемые для установки Lync 2013, перечислены в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6d01d-117">The Config.xml elements most commonly used for Lync 2013 installation are listed in the following table.</span></span>

### <a name="configxml-elements"></a><span data-ttu-id="6d01d-118">Элементы Config.xml</span><span class="sxs-lookup"><span data-stu-id="6d01d-118">Config.xml elements</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6d01d-119">Элемент</span><span class="sxs-lookup"><span data-stu-id="6d01d-119">Element</span></span></th>
<th><span data-ttu-id="6d01d-120">Описание</span><span class="sxs-lookup"><span data-stu-id="6d01d-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6d01d-121">Конфигурация</span><span class="sxs-lookup"><span data-stu-id="6d01d-121">Configuration</span></span></p></td>
<td><p><span data-ttu-id="6d01d-p103">Элемент верхнего уровня (обязательный). Содержит атрибут Product, например: Product=Lync</span><span class="sxs-lookup"><span data-stu-id="6d01d-p103">Top-level element (required). Contains the Product attribute, for example: Product=Lync</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d01d-124">OptionState</span><span class="sxs-lookup"><span data-stu-id="6d01d-124">OptionState</span></span></p></td>
<td><p><span data-ttu-id="6d01d-125">Определяет, как при установке будут обрабатываться компоненты конкретного продукта.</span><span class="sxs-lookup"><span data-stu-id="6d01d-125">Specifies how specific product features are handled during installation.</span></span> <span data-ttu-id="6d01d-126">Используйте следующие атрибуты для предотвращения установки служб Business Connectivity Services, в том числе общих компонентов, которые мешают работе с Outlook 2010:</span><span class="sxs-lookup"><span data-stu-id="6d01d-126">Use the following attributes to prevent installation of Business Connectivity Services, which includes shared components that interfere with Outlook 2010:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d01d-127">ID = &quot; лобимаин&quot;</span><span class="sxs-lookup"><span data-stu-id="6d01d-127">Id=&quot;LOBiMain&quot;</span></span></p></li>
<li><p><span data-ttu-id="6d01d-128">State = &quot; отсутствует&quot;</span><span class="sxs-lookup"><span data-stu-id="6d01d-128">State=&quot;Absent&quot;</span></span></p></li>
<li><p><span data-ttu-id="6d01d-129">Дети = &quot; Force&quot;</span><span class="sxs-lookup"><span data-stu-id="6d01d-129">Children=&quot;Force&quot;</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d01d-130">Отображение</span><span class="sxs-lookup"><span data-stu-id="6d01d-130">Display</span></span></p></td>
<td><p><span data-ttu-id="6d01d-p105">Уровень пользовательского интерфейса, отображаемого пользователю программой установки. Обычно используются следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="6d01d-p105">The level of UI that Setup displays to the user. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d01d-133">CompletionNotice = &quot; Да &quot;  |  &quot; нет &quot; (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6d01d-133">CompletionNotice=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
<li><p><span data-ttu-id="6d01d-134">AcceptEula = &quot; Да &quot;  |  &quot; нет &quot; (по умолчанию)</span><span class="sxs-lookup"><span data-stu-id="6d01d-134">AcceptEula=&quot;Yes&quot; | &quot;No&quot;(default)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d01d-135">Ведение журнала</span><span class="sxs-lookup"><span data-stu-id="6d01d-135">Logging</span></span></p></td>
<td><p><span data-ttu-id="6d01d-p106">Параметры ведения журнала программой установки. Обычно используются следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="6d01d-p106">Options for the kind of logging that Setup performs. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d01d-138">Тип = &quot; &quot;  |  &quot; Standard &quot; (по умолчанию) | &quot; Verbose&quot;</span><span class="sxs-lookup"><span data-stu-id="6d01d-138">Type =&quot;Off&quot; | &quot;Standard&quot;(default) | &quot;Verbose&quot;</span></span></p></li>
<li><p><span data-ttu-id="6d01d-139">Template=”имя файла.txt” (имя файла журнала)</span><span class="sxs-lookup"><span data-stu-id="6d01d-139">Template=”filename.txt” (the name of the log file)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6d01d-140">Параметр</span><span class="sxs-lookup"><span data-stu-id="6d01d-140">Setting</span></span></p></td>
<td><p><span data-ttu-id="6d01d-p107">Определяет значения для свойств программы установщика Windows. Обычно используются следующие атрибуты:</span><span class="sxs-lookup"><span data-stu-id="6d01d-p107">Specifies values for Windows Installer properties. Typical attributes include the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d01d-143">Параметр ID = &quot; Name &quot; (имя свойства установщика Windows)</span><span class="sxs-lookup"><span data-stu-id="6d01d-143">Setting Id=&quot;name&quot; (the name of the Windows Installer property)</span></span></p></li>
<li><p><span data-ttu-id="6d01d-144">Значение = &quot; значение &quot; (значение, присваиваемое свойству)</span><span class="sxs-lookup"><span data-stu-id="6d01d-144">Value=&quot;value&quot; (the value to assign to the property)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6d01d-145">DistributionPoint</span><span class="sxs-lookup"><span data-stu-id="6d01d-145">DistributionPoint</span></span></p></td>
<td><p><span data-ttu-id="6d01d-p108">Полный доменный путь точки сетевой установки, из которой запускается установка. Содержит атрибут Location:</span><span class="sxs-lookup"><span data-stu-id="6d01d-p108">The fully qualified path of the network installation point from which the installation is to run. Includes the Location attribute:</span></span></p>
<ul>
<li><p><span data-ttu-id="6d01d-148">Location = "путь"</span><span class="sxs-lookup"><span data-stu-id="6d01d-148">Location=”path”</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="6d01d-149">В следующем примере показан файл Config.xml для типичной автоматической установки Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6d01d-149">The following example shows a Config.xml file for a typical silent installation of Lync 2013.</span></span>

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

<span data-ttu-id="6d01d-150">Подробные сведения об использовании файла Config.xml для выполнения задач установки и обслуживания Office можно найти на сайте <https://go.microsoft.com/fwlink/p/?linkid=267514> .</span><span class="sxs-lookup"><span data-stu-id="6d01d-150">Detailed information about using the Config.xml file to perform Office installation and maintenance tasks is available at <https://go.microsoft.com/fwlink/p/?linkid=267514>.</span></span>

<div>

## <a name="to-customize-the-configxml-file"></a><span data-ttu-id="6d01d-151">Изменение файла Config.xml</span><span class="sxs-lookup"><span data-stu-id="6d01d-151">To customize the Config.xml file</span></span>

1.  <span data-ttu-id="6d01d-152">Откройте файл Config.xml с помощью текстового редактора, такого как "Блокнот".</span><span class="sxs-lookup"><span data-stu-id="6d01d-152">Open the Config.xml file by using a text editor tool, such as Notepad.</span></span>

2.  <span data-ttu-id="6d01d-153">Найдите строки, содержащие элементы, которые нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="6d01d-153">Locate the lines that contain the elements you want to change.</span></span>

3.  <span data-ttu-id="6d01d-154">Измените запись для элемента, используя нужные значения параметров автоматической установки.</span><span class="sxs-lookup"><span data-stu-id="6d01d-154">Modify the element entry with the silent options that you want to use.</span></span> <span data-ttu-id="6d01d-155">Убедитесь, что вы удалили разделители комментариев, " \<\!--" and "--\> ".</span><span class="sxs-lookup"><span data-stu-id="6d01d-155">Make sure that you remove the comment delimiters, "\<\!--" and "--\>".</span></span> <span data-ttu-id="6d01d-156">Например, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="6d01d-156">For example, use the following syntax:</span></span>
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  <span data-ttu-id="6d01d-157">Сохраните файл Config.xml.</span><span class="sxs-lookup"><span data-stu-id="6d01d-157">Save the Config.xml file.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

