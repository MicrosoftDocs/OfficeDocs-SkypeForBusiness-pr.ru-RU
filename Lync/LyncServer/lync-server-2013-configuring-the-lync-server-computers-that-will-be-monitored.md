---
title: 'Lync Server 2013: Настройка компьютеров Lync Server, которые будут отслеживаться'
description: 'Lync Server 2013: Настройка компьютеров Lync Server, которые будут отслеживаться.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computers that will be monitored
ms:assetid: 9f1b2b91-d5af-42ad-a27d-b0815f762ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205118(v=OCS.15)
ms:contentKeyID: 48184927
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 742bd8a67eb42472e598c45619514e9407cb29cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556835"
---
# <a name="configuring-the-lync-server-computers-that-will-be-monitored-in-lync-server-2013"></a><span data-ttu-id="22f1d-103">Настройка компьютеров Lync Server, которые будут отслеживаться в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22f1d-103">Configuring the Lync Server computers that will be monitored in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22f1d-104">_**Последнее изменение темы:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="22f1d-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="22f1d-105">Поскольку Lync Server 2013 не использует процесс центрального обнаружения, используемый в Microsoft Lync Server 2010, каждый компьютер Lync Server 2013, который необходимо отслеживать, должен иметь возможность самостоятельного отчета о существовании сервера управления.</span><span class="sxs-lookup"><span data-stu-id="22f1d-105">Because Lync Server 2013 does not use the central discovery process used in Microsoft Lync Server 2010, each Lync Server 2013 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="22f1d-106">Для этого необходимо установить файлы агента Operations Manager на каждый отслеживаемый компьютер.</span><span class="sxs-lookup"><span data-stu-id="22f1d-106">To make this possible, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="22f1d-107">После установки файлов агента необходимо настроить компьютер для работы в качестве прокси-сервера System Center.</span><span class="sxs-lookup"><span data-stu-id="22f1d-107">After the agent files have been installed, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="22f1d-108">Обратите внимание, что эти процедуры следует выполнять после установки и настройки сервера Lync Server на этих компьютерах.</span><span class="sxs-lookup"><span data-stu-id="22f1d-108">Note that these procedures should be carried out after you have installed and configured Lync Server on these computers.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

