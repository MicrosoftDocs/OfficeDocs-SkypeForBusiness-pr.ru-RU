---
title: 'Lync Server 2013: Проверка использования диска'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Checking disk usage
ms:assetid: 0f0cb9bf-3f11-43ff-be10-5c8e1b5c4f08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720908(v=OCS.15)
ms:contentKeyID: 63969578
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0cb167d2a7aed3f5c107d4beba568c00ac501e0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="68288-102">Проверка использования диска в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="68288-102">Checking disk usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68288-103">_**Последнее изменение темы:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="68288-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="68288-104">Диски с жесткими дисками являются важным компонентом развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68288-104">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="68288-105">Без достаточного свободного дискового тома операционная система и базы данных Lync Server 2013 могут работать неправильно.</span><span class="sxs-lookup"><span data-stu-id="68288-105">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="68288-106">Необходимо ежедневно отслеживать фоновую статистику базы данных Lync Server 2013, чтобы убедиться, что на серверах не хватает дискового пространства, и при необходимости подготовить ресурсы хранилища.</span><span class="sxs-lookup"><span data-stu-id="68288-106">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="68288-107">Помимо проверки места на дисках, на которых размещается операционная система, файлы программ, базы данных и журналы транзакций (Lync Server 2013 Back), следует также следить за использованием файловой системы, включающей дисковое пространство для файловых ресурсов, содержащих следующие важные данным</span><span class="sxs-lookup"><span data-stu-id="68288-107">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="68288-108">Содержимое собрания</span><span class="sxs-lookup"><span data-stu-id="68288-108">Meeting content</span></span>

  - <span data-ttu-id="68288-109">Метаданные контента собраний</span><span class="sxs-lookup"><span data-stu-id="68288-109">Meeting content metadata</span></span>

  - <span data-ttu-id="68288-110">Журналы соответствия требованиям для собраний</span><span class="sxs-lookup"><span data-stu-id="68288-110">Meeting compliance logs</span></span>

  - <span data-ttu-id="68288-111">Файлы данных приложения (внутренне используются компонентом сервера приложений)</span><span class="sxs-lookup"><span data-stu-id="68288-111">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="68288-112">Веб-служба сервера группового чата и папки соответствия требованиям (для хранения файлов, отправленных в веб-службу чата)</span><span class="sxs-lookup"><span data-stu-id="68288-112">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="68288-113">Групповые XML-файлы соответствия групповой беседы (содержащие записи о соответствии группового чата)</span><span class="sxs-lookup"><span data-stu-id="68288-113">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="68288-114">Обновление файлов (для службы обновления устройств)</span><span class="sxs-lookup"><span data-stu-id="68288-114">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="68288-115">Файлы адресной книги</span><span class="sxs-lookup"><span data-stu-id="68288-115">Address Book files</span></span>

<span data-ttu-id="68288-116">Lync Server 2013 требует жесткого диска для хранения баз данных и журналов транзакций в дополнение к файлам в общих файловых ресурсах, перечисленных выше.</span><span class="sxs-lookup"><span data-stu-id="68288-116">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="68288-117">Следует регулярно отслеживать дисковое пространство, чтобы обеспечить неблагоприятное влияние развертывания Lync Server 2013 из-за недостатка ресурсов хранилища.</span><span class="sxs-lookup"><span data-stu-id="68288-117">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="68288-118">Сравните и настройте статистические сведения о доступном дисковом пространстве на каждом томе Lync Server 2013 и ожидаемом росте баз данных и файлов журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="68288-118">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="68288-119">Это помогает при планировании емкости и добавлении хранилища, когда требуются ресурсы хранилища.</span><span class="sxs-lookup"><span data-stu-id="68288-119">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="68288-120">Чтобы обеспечить устранение неполадок и аварийное восстановление, рекомендуется, чтобы свободное место на диске было равно или превышать 110 процентов от размера базы данных.</span><span class="sxs-lookup"><span data-stu-id="68288-120">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="68288-121">Проверить наличие свободного места на диске можно описанными ниже способами.</span><span class="sxs-lookup"><span data-stu-id="68288-121">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="68288-122">**System Center Operations**   Manager System Center Operations Manager можно использовать для предупреждения администраторов о ограничении объема громкости.</span><span class="sxs-lookup"><span data-stu-id="68288-122">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="68288-123">**Выполнив сценарий**, который отправляет вам сообщение, если объем свободного места на жестком диске падает ниже 20 процентов.   </span><span class="sxs-lookup"><span data-stu-id="68288-123">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="68288-124">Пример скрипта можно найти в центре сценариев Майкрософт на сайте TechNet, изучите следующее:[https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="68288-124">You can find a sample script on Microsoft Script Center on TechNet, examine: [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="68288-125">**Проводник**   Windows используйте проводник Windows, чтобы проверить наличие дискового пространства на томах, в которых хранятся журналы и базы данных Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="68288-125">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

