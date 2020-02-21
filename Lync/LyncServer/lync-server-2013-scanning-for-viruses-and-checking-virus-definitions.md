---
title: 'Lync Server 2013: сканирование на наличие вирусов и проверка определений вирусов'
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
ms.openlocfilehash: aba7d5f1b279ba83a5a6053d2197c90253dd84ed
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182742"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scanning-for-viruses-and-checking-virus-definitions-in-lync-server-2013"></a><span data-ttu-id="0d645-102">Поиск вирусов и проверка определений вирусов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0d645-102">Scanning for viruses and checking virus definitions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d645-103">_**Последнее изменение темы:** 2014-05-01_</span><span class="sxs-lookup"><span data-stu-id="0d645-103">_**Topic Last Modified:** 2014-05-01_</span></span>

<span data-ttu-id="0d645-104">Мы настоятельно рекомендуем установить антивирусную программу уровня обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="0d645-104">We highly recommend installing an IM-level antivirus product.</span></span> <span data-ttu-id="0d645-105">Обмен мгновенными сообщениями это известный источник для быстрого распространения вирусов и вредоносных программ в Организации.</span><span class="sxs-lookup"><span data-stu-id="0d645-105">IM is a well-known source for quickly spreading both virus and malicious software throughout an organization.</span></span> <span data-ttu-id="0d645-106">Microsoft Forefront® Security для Lync Server обеспечивает сканирование нескольких модулей с использованием вирусов, вредоносных программ, защиты файлов и ключевых слов, а также полную интеграцию с Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="0d645-106">Microsoft Forefront® Security for Lync Server provides multi-engine scanning with virus, malicious software, file and keyword filter protection and seamless integration with Office Communications Server.</span></span>

<span data-ttu-id="0d645-107">Кроме Forefront Security для Lync Server, мы также настоятельно рекомендуем установить антивирусное решение для защиты файловой системы сервера.</span><span class="sxs-lookup"><span data-stu-id="0d645-107">In addition to Forefront Security for Lync Server, we also highly recommend installing a file-level, antivirus solution to protect the server’s file system.</span></span>

<span data-ttu-id="0d645-108">Обновление антивирусных ядер и определений вирусов очень важно.</span><span class="sxs-lookup"><span data-stu-id="0d645-108">Keeping scanner engines and virus definitions updated is very important.</span></span> <span data-ttu-id="0d645-109">Настройка и мониторинг работоспособности обновлений гарантирует, что для защиты Office Communications Server и файловой системы используются самые последние сведения о сканировании.</span><span class="sxs-lookup"><span data-stu-id="0d645-109">Configuring and monitoring the health of the updates makes sure that the most current scanning information is being used to protect both Office Communications Server and file-system.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0d645-110">При использовании антивирусной программы стороннего уровня на сервере, на котором работает Lync Server 2013 и Forefront Security для Lync Server, убедитесь, что папки, в которых установлены Forefront Security для Lync Server и Lync Server, не проверяются, чтобы предотвратить их повреждения.</span><span class="sxs-lookup"><span data-stu-id="0d645-110">When using a third-party, file-level antivirus software on a server that runs Lync Server 2013 and Forefront Security for Lync Server, make sure that the folders in which Forefront Security for Lync Server and the Lync Server are installed are not scanned, to prevent their corruption.</span></span> <span data-ttu-id="0d645-111">Полный список исключений приведен в разделе <A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A>.</span><span class="sxs-lookup"><span data-stu-id="0d645-111">For the full list of exclusions, see <A class=uri href="https://support.microsoft.com/kb/943620">https://support.microsoft.com/kb/943620</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

