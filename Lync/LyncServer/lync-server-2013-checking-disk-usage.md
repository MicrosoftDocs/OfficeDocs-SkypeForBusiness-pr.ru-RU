---
title: 'Lync Server 2013: Проверка использования диска'
description: 'Lync Server 2013: Проверка использования места на диске.'
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
ms.openlocfilehash: 7eddde772d156f0a416dab381efe1ab33ee202f9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571005"
---
# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="de99f-103">Проверка использования диска в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de99f-103">Checking disk usage in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de99f-104">_**Последнее изменение темы:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="de99f-104">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="de99f-105">Диски с жесткими дисками являются важным компонентом развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de99f-105">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="de99f-106">Без достаточного свободного дискового тома операционная система и базы данных Lync Server 2013 могут работать неправильно.</span><span class="sxs-lookup"><span data-stu-id="de99f-106">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="de99f-107">Необходимо ежедневно отслеживать фоновую статистику базы данных Lync Server 2013, чтобы убедиться, что на серверах не хватает дискового пространства, и при необходимости подготовить ресурсы хранилища.</span><span class="sxs-lookup"><span data-stu-id="de99f-107">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="de99f-108">Помимо проверки места на дисках, на которых размещается операционная система, файлы программ, базы данных и журналы транзакций (Lync Server 2013 Back), следует также отслеживать использование файловой системы, в том числе дискового пространства для файловых ресурсов, содержащих следующие важные данные:</span><span class="sxs-lookup"><span data-stu-id="de99f-108">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="de99f-109">Содержимое собрания</span><span class="sxs-lookup"><span data-stu-id="de99f-109">Meeting content</span></span>

  - <span data-ttu-id="de99f-110">Метаданные контента собраний</span><span class="sxs-lookup"><span data-stu-id="de99f-110">Meeting content metadata</span></span>

  - <span data-ttu-id="de99f-111">Журналы соответствия требованиям для собраний</span><span class="sxs-lookup"><span data-stu-id="de99f-111">Meeting compliance logs</span></span>

  - <span data-ttu-id="de99f-112">Файлы данных приложения (внутренне используются компонентом сервера приложений)</span><span class="sxs-lookup"><span data-stu-id="de99f-112">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="de99f-113">Веб-служба сервера группового чата и папки соответствия требованиям (для хранения файлов, отправленных в веб-службу чата)</span><span class="sxs-lookup"><span data-stu-id="de99f-113">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="de99f-114">Групповые XML-файлы соответствия групповой беседы (содержащие записи о соответствии группового чата)</span><span class="sxs-lookup"><span data-stu-id="de99f-114">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="de99f-115">Обновление файлов (для службы обновления устройств)</span><span class="sxs-lookup"><span data-stu-id="de99f-115">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="de99f-116">Файлы адресной книги</span><span class="sxs-lookup"><span data-stu-id="de99f-116">Address Book files</span></span>

<span data-ttu-id="de99f-117">Lync Server 2013 требует жесткого диска для хранения баз данных и журналов транзакций в дополнение к файлам в общих файловых ресурсах, перечисленных выше.</span><span class="sxs-lookup"><span data-stu-id="de99f-117">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="de99f-118">Следует регулярно отслеживать дисковое пространство, чтобы обеспечить неблагоприятное влияние развертывания Lync Server 2013 из-за недостатка ресурсов хранилища.</span><span class="sxs-lookup"><span data-stu-id="de99f-118">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="de99f-119">Сравните и настройте статистические сведения о доступном дисковом пространстве на каждом томе Lync Server 2013 и ожидаемом росте баз данных и файлов журналов транзакций.</span><span class="sxs-lookup"><span data-stu-id="de99f-119">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="de99f-120">Это помогает при планировании емкости и добавлении хранилища, когда требуются ресурсы хранилища.</span><span class="sxs-lookup"><span data-stu-id="de99f-120">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="de99f-121">Чтобы обеспечить устранение неполадок и аварийное восстановление, рекомендуется, чтобы свободное место на диске было равно или превышать 110 процентов от размера базы данных.</span><span class="sxs-lookup"><span data-stu-id="de99f-121">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="de99f-122">Проверить наличие свободного места на диске можно описанными ниже способами.</span><span class="sxs-lookup"><span data-stu-id="de99f-122">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="de99f-123">**System Center Operations Manager**     System Center Operations Manager можно использовать для предупреждения администраторов о ограничении объема громкости.</span><span class="sxs-lookup"><span data-stu-id="de99f-123">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="de99f-124">**Выполнение скрипта**     Отслеживайте дисковое пространство, выполнив сценарий, который отправляет вам сообщение, если объем свободного места на жестком диске падает ниже 20 процентов.</span><span class="sxs-lookup"><span data-stu-id="de99f-124">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="de99f-125">Пример скрипта можно найти в центре сценариев Майкрософт на сайте TechNet, изучите следующее: [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="de99f-125">You can find a sample script on Microsoft Script Center on TechNet, examine: [https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](https://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="de99f-126">**Проводник Windows**     Используйте проводник Windows, чтобы проверить наличие дискового пространства на томах, в которых хранятся журналы и базы данных Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de99f-126">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

