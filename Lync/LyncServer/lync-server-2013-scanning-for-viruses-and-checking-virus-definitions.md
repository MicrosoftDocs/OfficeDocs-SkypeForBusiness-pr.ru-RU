---
title: 'Lync Server 2013: Проверка наличия вирусов и определение вирусов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scanning for viruses and checking virus definitions
ms:assetid: 287c0f43-82d1-4c1d-b08f-77112fcb5bfa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720909(v=OCS.15)
ms:contentKeyID: 63969589
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb36ec86c5e9d30e6a215a89748a02e5ef355b73
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="896f8-102">Поиск вирусов и проверка определений вирусов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="896f8-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="896f8-103">_**Тема последнего изменения:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="896f8-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="896f8-104">Мы настоятельно рекомендуем установить антивирусную программу уровня сообщений.</span><span class="sxs-lookup"><span data-stu-id="896f8-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="896f8-105">Мгновенное сообщение — это известный источник для быстрого распространения вирусов и вредоносных программ в масштабах всей Организации.</span><span class="sxs-lookup"><span data-stu-id="896f8-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="896f8-106">Microsoft Forefront® Security для Lync Server обеспечивает многоядерную проверку с помощью вирусов, вредоносных программ, защиты файлов и ключевых слов и быстрой интеграции с Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="896f8-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="896f8-107">Помимо приложения Forefront Security для Lync Server, мы настоятельно рекомендуем установить антивирусную программу, которая будет использоваться для защиты файловой системы сервера.</span><span class="sxs-lookup"><span data-stu-id="896f8-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="896f8-108">Обновление антивирусных ядер и определений вирусов очень важно.</span><span class="sxs-lookup"><span data-stu-id="896f8-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="896f8-109">Настройка и наблюдение за работоспособностью обновлений убедитесь в том, что в настоящее время используются последние сведения о проверке, чтобы защитить как Office Communications Server, так и файловую систему.</span><span class="sxs-lookup"><span data-stu-id="896f8-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="896f8-110">При использовании антивирусных программ сторонних разработчиков на сервере, на котором запущены Lync Server 2013 и Forefront Security для Lync Server, убедитесь, что папки, в которых установлены программы Forefront Security для Lync Server и Lync Server, не проверяются, чтобы предотвратить их повреждения.</span><span class="sxs-lookup"><span data-stu-id="896f8-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="896f8-111">Полный список исключений можно найти в разделе <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>.</span><span class="sxs-lookup"><span data-stu-id="896f8-111">For the full list of exclusions, see <A class=uri href="http://support.microsoft.com/kb/943620">http://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

