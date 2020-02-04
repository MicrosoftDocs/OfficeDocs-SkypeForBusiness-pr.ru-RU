---
title: 'Lync Server 2013: журналы и файлы обновлений устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update logs and files
ms:assetid: f7f822b8-0a62-4ff2-a4cb-1ab1ed7503eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994090(v=OCS.15)
ms:contentKeyID: 51804004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170bafb3d00940995e8355c7775681c2af5fd078
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-logs-and-files-in-lync-server-2013"></a><span data-ttu-id="69d29-102">Журналы и файлы обновления устройства в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69d29-102">Device Update logs and files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69d29-103">_**Тема последнего изменения:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="69d29-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="69d29-104">Журналы обновления устройства содержат важную информацию, которую можно использовать для управления веб-службой обновления устройства и устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="69d29-104">Device update logs contain important information that you can use to manage and troubleshoot the Device Update Web service.</span></span> <span data-ttu-id="69d29-105">Вы можете изменить записи, которые записываются в журнал, и удалять журналы устройств и обновления, которые вам не нужны или больше не нужны.</span><span class="sxs-lookup"><span data-stu-id="69d29-105">You can change what is logged and remove device logs and updates that you don’t want or no longer need.</span></span> <span data-ttu-id="69d29-106">В этом разделе рассказывается о том, как можно использовать панель управления Lync Server или консоль управления Lync Server для изменения параметров ведения журнала, очистки журнала обновления устройства или удаления файлов журнала с сервера.</span><span class="sxs-lookup"><span data-stu-id="69d29-106">This section describes how you can use Lync Server Control Panel or Lync Server Management Shell to modify logging settings, clear the device update log, or remove log files from the server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69d29-107">Дополнительные сведения о файлах журнала обновления устройств можно найти в разделе <A href="http://technet.microsoft.com/en-us/library/gg398250(v=ocs.14).aspx">типы и расположения файлов журнала</A> в библиотеке TechNet Server 2010.</span><span class="sxs-lookup"><span data-stu-id="69d29-107">For details about device update log files, see <A href="http://technet.microsoft.com/en-us/library/gg398250(v=ocs.14).aspx">Log File Types and Locations</A> in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="69d29-108">(Обратите внимание, что веб-служба обновления устройства, как и все компоненты Lync Phone Edition, работает аналогично с Lync Server 2013, как это происходит в Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="69d29-108">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="69d29-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="69d29-109">In This Section</span></span>

  - [<span data-ttu-id="69d29-110">Изменение параметров для файлов журнала обновления устройства в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69d29-110">Modify settings for Device Update log files in Lync Server 2013</span></span>](lync-server-2013-modify-settings-for-device-update-log-files.md)

  - [<span data-ttu-id="69d29-111">Удаление файлов журнала обновления устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69d29-111">Delete Device Update log files in Lync Server 2013</span></span>](lync-server-2013-delete-device-update-log-files.md)

  - [<span data-ttu-id="69d29-112">Удаление файлов обновления устройства, не связанных с устройством в окне удаления файлов обновления устройства, не связанных с устройством в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69d29-112">Remove Device Update files not associated with a device in Remove Device Update files not associated with a device in Lync Server 2013</span></span>](lync-server-2013-remove-device-update-files-not-associated-with-a-device.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

