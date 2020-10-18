---
title: 'Lync Server 2013: использование параметров командной строки программы установки'
description: 'Lync Server 2013: использование параметров командной строки программы установки.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15c3490ead090766462ce83cb13ffe62355032cd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48580245"
---
# <a name="using-setup-command-line-options-in-lync-server-2013"></a><span data-ttu-id="f22df-103">Использование параметров командной строки программы установки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f22df-103">Using Setup command-line options in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f22df-104">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="f22df-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="f22df-p101">Командная строка программы установки используется для выполнения достаточно редких операций в процессе установки Office. Вместо использования параметров командной строки программы установки для установки продукта и настройки компонентов обычно используется центр развертывания Office и файл Config.xml.</span><span class="sxs-lookup"><span data-stu-id="f22df-p101">The Setup.exe command line is used for very few operations in Office setup. Instead of using the Setup command-line options, you’ll typically use the Office Customization Tool and the Config.xml file for product setup and feature customization.</span></span>

<span data-ttu-id="f22df-107">Командная строка программы установки Office распознает параметры командной строки, описанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="f22df-107">The Office Setup.exe command line recognizes the command-line options described in the following table.</span></span>

### <a name="office-setup-command-line-options"></a><span data-ttu-id="f22df-108">Параметры командной строки программы установки Office</span><span class="sxs-lookup"><span data-stu-id="f22df-108">Office Setup Command-Line Options</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f22df-109">Параметр командной строки программы установки</span><span class="sxs-lookup"><span data-stu-id="f22df-109">Setup Command-Line Option</span></span></th>
<th><span data-ttu-id="f22df-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f22df-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f22df-111">/Admin</span><span class="sxs-lookup"><span data-stu-id="f22df-111">/admin</span></span></p></td>
<td><p><span data-ttu-id="f22df-112">Запускает центр развертывания Office для создания файла настройки программы установки (файла MSP).</span><span class="sxs-lookup"><span data-stu-id="f22df-112">Runs the Office Customization Tool to create a Setup customization file (.msp file).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f22df-113">/adminfile [путь]</span><span class="sxs-lookup"><span data-stu-id="f22df-113">/adminfile [path]</span></span></p></td>
<td><p><span data-ttu-id="f22df-p102">Применяет к установке указанный файл настройки программы установки. Можно указать путь к конкретному MSP-файлу настройки или к папке файлов настройки.</span><span class="sxs-lookup"><span data-stu-id="f22df-p102">Applies the specified Setup customization file to the installation. You can specify a path of a specific customization file (.msp file) or to the folder where you store customization files.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f22df-116">/config [путь]</span><span class="sxs-lookup"><span data-stu-id="f22df-116">/config [path]</span></span></p></td>
<td><p><span data-ttu-id="f22df-117">Задает файл Config.xml, который программа установки использует во время установки.</span><span class="sxs-lookup"><span data-stu-id="f22df-117">Specifies the Config.xml file that Setup uses during the installation.</span></span> <span data-ttu-id="f22df-118">Используйте параметр/config, чтобы указать Config.xml файл, который вы настроили для установок Lync 2013, например: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span><span class="sxs-lookup"><span data-stu-id="f22df-118">Use the /config option to specify the Config.xml file you customized for Lync 2013 installations, for example: <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f22df-119">/modify Lync</span><span class="sxs-lookup"><span data-stu-id="f22df-119">/modify Lync</span></span></p></td>
<td><p><span data-ttu-id="f22df-p104">Используется с модифицированным файлом Config.xml для запуска программы установки в режиме обслуживания и изменения существующей установки Office. Например, можно использовать параметр /modify для добавления или удаления компонентов Lync.</span><span class="sxs-lookup"><span data-stu-id="f22df-p104">Used with a modified Config.xml file to run Setup in maintenance mode and make changes to an existing Office installation. For example, you can use the /modify option to add or remove Lync features.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f22df-122">/repair Lync</span><span class="sxs-lookup"><span data-stu-id="f22df-122">/repair Lync</span></span></p></td>
<td><p><span data-ttu-id="f22df-123">Запускает программу установки на компьютере пользователя для восстановления Lync.</span><span class="sxs-lookup"><span data-stu-id="f22df-123">Runs Setup from the user’s computer to repair Lync.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f22df-124">/uninstall Lync</span><span class="sxs-lookup"><span data-stu-id="f22df-124">/uninstall Lync</span></span></p></td>
<td><p><span data-ttu-id="f22df-125">Запускает программу установки для удаления Lync с компьютера пользователя.</span><span class="sxs-lookup"><span data-stu-id="f22df-125">Runs Setup to remove Lync from the user’s computer.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="f22df-126">Сведения об использовании параметров командной строки программы установки приведены в разделе <https://go.microsoft.com/fwlink/p/?linkid=267515> .</span><span class="sxs-lookup"><span data-stu-id="f22df-126">For details about using the setup command-line options, see <https://go.microsoft.com/fwlink/p/?linkid=267515>.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

