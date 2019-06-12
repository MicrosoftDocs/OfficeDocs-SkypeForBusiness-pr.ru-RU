---
title: 'Lync Server 2013: использование параметров командной строки для настройки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5087c8ac777e5e2fd3259f925a4217a4d47dd800
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="e5805-102">Использование параметров командной строки программы установки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5805-102">Using Setup command-line options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5805-103">_**Тема последнего изменения:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e5805-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e5805-p101">Командная строка программы установки используется для выполнения достаточно редких операций в процессе установки Office. Вместо использования параметров командной строки программы установки для установки продукта и настройки компонентов обычно используется центр развертывания Office и файл Config.xml.</span><span class="sxs-lookup"><span data-stu-id="e5805-p101">The Setup.exe command line is used for very few operations in Office setup. Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="e5805-106">Командная строка программы установки Office распознает параметры командной строки, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="e5805-106">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="e5805-107">Параметры командной строки программы установки Office</span><span class="sxs-lookup"><span data-stu-id="e5805-107">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5805-108">Параметр командной строки программы установки</span><span class="sxs-lookup"><span data-stu-id="e5805-108">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="e5805-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e5805-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5805-110">/admin</span><span class="sxs-lookup"><span data-stu-id="e5805-110">/admin</span></span></p></td>
<td><p><span data-ttu-id="e5805-111">Запускает центр развертывания Office для создания файла настройки программы установки (файла MSP).</span><span class="sxs-lookup"><span data-stu-id="e5805-111">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5805-112">/adminfile [путь]</span><span class="sxs-lookup"><span data-stu-id="e5805-112">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="e5805-p102">Применяет к установке указанный файл настройки программы установки. Можно указать путь к конкретному MSP-файлу настройки или к папке файлов настройки.</span><span class="sxs-lookup"><span data-stu-id="e5805-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5805-115">/config [путь]</span><span class="sxs-lookup"><span data-stu-id="e5805-115">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="e5805-116">Указывает файл Config.xml, который программа установки использует во время установки.</span><span class="sxs-lookup"><span data-stu-id="e5805-116">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="e5805-117">Используйте параметр/config для указания файла config. XML, настроенного для установки Lync 2013, например:<code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="e5805-117">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5805-118">/модифи Lync</span><span class="sxs-lookup"><span data-stu-id="e5805-118">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="e5805-119">Используется с модифицированным файлом Config.xml для запуска программы установки в режиме обслуживания и изменения существующей установки Office.</span><span class="sxs-lookup"><span data-stu-id="e5805-119">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation.</span></span> <span data-ttu-id="e5805-120">Например, можно использовать параметр/модифи для добавления и удаления функций Lync.</span><span class="sxs-lookup"><span data-stu-id="e5805-120">For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5805-121">/репаир Lync</span><span class="sxs-lookup"><span data-stu-id="e5805-121">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="e5805-122">Запускает программу установки с компьютера пользователя, чтобы восстановить Lync.</span><span class="sxs-lookup"><span data-stu-id="e5805-122">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5805-123">/Uninstall Lync</span><span class="sxs-lookup"><span data-stu-id="e5805-123">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="e5805-124">Запускает программу установки, чтобы удалить Lync с компьютера пользователя.</span><span class="sxs-lookup"><span data-stu-id="e5805-124">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e5805-125">Подробнее об использовании параметров командной строки Setup можно узнать в разделе <http://go.microsoft.com/fwlink/p/?linkid=267515>.</span><span class="sxs-lookup"><span data-stu-id="e5805-125">For details about using the setup command-line options, see <http://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

