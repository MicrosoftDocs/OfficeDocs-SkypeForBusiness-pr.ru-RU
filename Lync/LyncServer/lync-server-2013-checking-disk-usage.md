---
title: 'Lync Server 2013: Проверка использования дискового пространства'
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
ms.openlocfilehash: 554b493ba7ca837a8ea5c80f6751ddb91061c374
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="checking-disk-usage-in-lync-server-2013"></a><span data-ttu-id="db59c-102">Проверка использования диска в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db59c-102">Checking disk usage in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db59c-103">_**Тема последнего изменения:** 2014-04-30_</span><span class="sxs-lookup"><span data-stu-id="db59c-103">_**Topic Last Modified:** 2014-04-30_</span></span>

<span data-ttu-id="db59c-104">Жесткие диски — это важный компонент развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db59c-104">Hard disks drives are an important component of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="db59c-105">Без достаточного свободного места на диске ни операционная система, ни база данных Lync Server 2013 могут работать неправильно.</span><span class="sxs-lookup"><span data-stu-id="db59c-105">Without sufficient free disk volume, neither the operating system nor the Lync Server 2013 databases can function correctly.</span></span> <span data-ttu-id="db59c-106">Необходимо ежедневно отслеживать статистику базы данных Lync Server 2013, чтобы убедиться в том, что на серверах не осталось свободного места, а также для подготовки к добавлению ресурсов хранилища по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="db59c-106">You must monitor the Lync Server 2013 back-end database statistics daily to help to make sure that servers do not run out of disk space, and to prepare to add storage resources as required.</span></span>

<span data-ttu-id="db59c-107">Помимо проверки места на дисках с операционной системой, файлами программы, базой данных и журналами транзакций (Lync Server 2013 Back), необходимо также отслеживать использование файловой системы, в которой есть место для файлов, содержащих указанные ниже важные сведения. сведения</span><span class="sxs-lookup"><span data-stu-id="db59c-107">Apart from checking space on disks hosting the operating system, program files, database, and transaction logs (Lync Server 2013 Back End), you should also monitor usage of the file system that includes disk space for file shares that contain the following important data:</span></span>

  - <span data-ttu-id="db59c-108">Содержимое собрания</span><span class="sxs-lookup"><span data-stu-id="db59c-108">Meeting content</span></span>

  - <span data-ttu-id="db59c-109">Метаданные содержимого собрания</span><span class="sxs-lookup"><span data-stu-id="db59c-109">Meeting content metadata</span></span>

  - <span data-ttu-id="db59c-110">Журналы соответствия требованиям к собранию</span><span class="sxs-lookup"><span data-stu-id="db59c-110">Meeting compliance logs</span></span>

  - <span data-ttu-id="db59c-111">Файлы данных приложения (используется внутренне компонентом сервера приложений)</span><span class="sxs-lookup"><span data-stu-id="db59c-111">Application data files (used internally by the application server component)</span></span>

  - <span data-ttu-id="db59c-112">Групповая связь с веб-службой сервера и ее соответствием (для хранения файлов, отправленных в веб-службу группового чата)</span><span class="sxs-lookup"><span data-stu-id="db59c-112">Group Chat Server web service and compliance folders (to store files uploaded to the Group Chat web service)</span></span>

  - <span data-ttu-id="db59c-113">XML-файлы соответствия групповой чат (содержащие записи соответствия требованиям группового чата)</span><span class="sxs-lookup"><span data-stu-id="db59c-113">Group Chat compliance XML files (that contain Group Chat compliance records)</span></span>

  - <span data-ttu-id="db59c-114">Файлы обновления (для службы обновления устройств)</span><span class="sxs-lookup"><span data-stu-id="db59c-114">Update files (for Device Update Service)</span></span>

  - <span data-ttu-id="db59c-115">Файлы адресной книги</span><span class="sxs-lookup"><span data-stu-id="db59c-115">Address Book files</span></span>

<span data-ttu-id="db59c-116">Lync Server 2013 нуждается в жестком диске для хранения баз данных и журналов транзакций в дополнение к файлам в перечисленных выше файловых ресурсах.</span><span class="sxs-lookup"><span data-stu-id="db59c-116">Lync Server 2013 needs hard disk space to store its databases and transaction logs in addition to files on file shares previously listed.</span></span>

<span data-ttu-id="db59c-117">Чтобы убедиться в том, что развертывание Lync Server 2013 не может негативно повлиять на место на диске, необходимо регулярно следить за тем, что в этом случае недостаточно ресурсов хранилища.</span><span class="sxs-lookup"><span data-stu-id="db59c-117">You should monitor the disk space regularly to help to make sure that the Lync Server 2013 deployment is not adversely affected because of insufficient storage resources.</span></span>

<span data-ttu-id="db59c-118">Сравните и отслеживайте статистические данные о доступном дисковом пространстве на каждом томе Lync Server 2013 и ожидаемом росте баз данных и файлов журнала транзакций.</span><span class="sxs-lookup"><span data-stu-id="db59c-118">Compare and maintain statistical information about available disk space on each Lync Server 2013 volume and expected growth of the databases and transaction log files.</span></span> <span data-ttu-id="db59c-119">Это помогает при планировании мощности и добавлении хранилища, когда требуются ресурсы хранилища.</span><span class="sxs-lookup"><span data-stu-id="db59c-119">This helps with capacity planning and adding storage when the storage resources are required.</span></span>

<span data-ttu-id="db59c-120">Для устранения неполадок и аварийного восстановления рекомендуется, чтобы объем свободного места в свободном объеме не превышал 110 процента от размера базы данных.</span><span class="sxs-lookup"><span data-stu-id="db59c-120">To accommodate troubleshooting and disaster recovery situations, we recommend that available free volume space be equal or greater than 110 percent of the size of database.</span></span>

<span data-ttu-id="db59c-121">Вы можете проверить свободное место на диске, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="db59c-121">You can check free disk space by using the following methods:</span></span>

1.  <span data-ttu-id="db59c-122">**Системный центр Operations**   Manager System Center Operations Manager может использоваться для предупреждения администраторов о том, что место в томе ограничено.</span><span class="sxs-lookup"><span data-stu-id="db59c-122">**System Center Operations Manager**   System Center Operations Manager can be used to warn administrators when volume space is constrained.</span></span>

2.  <span data-ttu-id="db59c-123">**Выполнив сценарий**, который посылает вам сообщение, если объем свободного места на жестком диске падает ниже 20%.   </span><span class="sxs-lookup"><span data-stu-id="db59c-123">**Running a script**   Monitor disk space by running a script that sends you a message if the available hard disk space falls below 20 percent.</span></span> <span data-ttu-id="db59c-124">Вы можете найти образец сценария в центре сценариев Майкрософт на веб-сайте TechNet, изучите следующие сведения:[http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span><span class="sxs-lookup"><span data-stu-id="db59c-124">You can find a sample script on Microsoft Script Center on TechNet, examine: [http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard%20disk%20alert\&f%5B0%5D.Value=hard%20disk%20alert\&f%5B0%5D.Type=SearchText\&ac=5](http://gallery.technet.microsoft.com/scriptcenter/site/search?query=hard+disk+alert%26f%5b0%5d.value=hard+disk+alert%26f%5b0%5d.type=searchtext%26ac=5)</span></span>

3.  <span data-ttu-id="db59c-125">**Проводник**   Windows использует проводник для проверки места на диске для томов, в которых хранятся журналы и базы данных Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db59c-125">**Windows Explorer**   Use Windows Explorer to check for disk space on volumes that store Lync Server 2013 logs and databases.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

