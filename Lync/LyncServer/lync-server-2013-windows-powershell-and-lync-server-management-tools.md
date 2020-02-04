---
title: 'Lync Server 2013: средства управления для Windows PowerShell и Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell and Lync Server 2013 management tools
ms:assetid: 6a285f7c-0ef5-4cab-9976-d03be276e35d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481130(v=OCS.15)
ms:contentKeyID: 59893869
ms.date: 07/20/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dbfd15ff3c1047f04a6878b65a3d16e63bac490b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="dbc11-102">Средства управления для Windows PowerShell и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dbc11-102">Windows PowerShell and Lync Server 2013 management tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbc11-103">_**Тема последнего изменения:** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="dbc11-103">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="dbc11-104">В Microsoft Lync Server 2013 средства управления реализованы с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dbc11-104">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="dbc11-105">Windows PowerShell включает среду командной строки, команды, связанные с продуктом, и полный язык сценариев.</span><span class="sxs-lookup"><span data-stu-id="dbc11-105">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="dbc11-106">Средства Lync Server 2013, реализованные с помощью Windows PowerShell, включают следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="dbc11-106">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="dbc11-107">**Построитель топологии**.</span><span class="sxs-lookup"><span data-stu-id="dbc11-107">**Topology Builder**.</span></span> <span data-ttu-id="dbc11-108">С помощью Topology Builder вы можете создавать, изменять и публиковать плановую топологию, а также проверять топологию до начала установки сервера.</span><span class="sxs-lookup"><span data-stu-id="dbc11-108">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="dbc11-109">При установке Lync Server 2013 на отдельных серверах серверы считывают опубликованную топологию в процессе установки, и программа установки развертывает сервер в соответствии с топологией.</span><span class="sxs-lookup"><span data-stu-id="dbc11-109">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="dbc11-110">После установки сведения о конфигурации автоматически реплицируются на все серверы.</span><span class="sxs-lookup"><span data-stu-id="dbc11-110">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="dbc11-111">Компоненты можно добавлять в развертывание только с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="dbc11-111">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="dbc11-112">**Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="dbc11-112">**Lync Server Management Shell**.</span></span> <span data-ttu-id="dbc11-113">Вы можете использовать командную консоль Lync Server для управления развертыванием с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="dbc11-113">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="dbc11-114">**Панель управления Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="dbc11-114">**Lync Server Control Panel**.</span></span> <span data-ttu-id="dbc11-115">Вы можете использовать пользовательский интерфейс панели управления Microsoft Lync Server 2013 для управления наиболее распространенными задачами в развертывании.</span><span class="sxs-lookup"><span data-stu-id="dbc11-115">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="dbc11-116">Эти средства используют командлеты Windows PowerShell для управления развертыванием, в том числе с помощью командлетов для работы с конкретными продуктами 550.</span><span class="sxs-lookup"><span data-stu-id="dbc11-116">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="dbc11-117">Командлеты безопасности, включенные в Lync Server 2013, главным образом используются для управления проверкой подлинности, а также правами и разрешениями пользователей.</span><span class="sxs-lookup"><span data-stu-id="dbc11-117">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="dbc11-118">Широкий спектр командлетов доступен для управления проверкой подлинности, включая командлеты для проверки подлинности с помощью сертификатов и персональных идентификационных номеров (ПИН-кодов).</span><span class="sxs-lookup"><span data-stu-id="dbc11-118">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="dbc11-119">Кроме того, несколько командлетов позволяют использовать новую функцию управления доступом на основе ролей (RBAC) для делегирования административного управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dbc11-119">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="dbc11-120">Дополнительные сведения о командлетах Lync Server можно найти в [командной консоли Lync server 2013](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="dbc11-120">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="dbc11-121">Функции безопасности сценариев для Windows PowerShell специально разработаны для помощи в предотвращении некоторых связанных с написанием сценариев проблем безопасности старых топологий, включая сценарии VBScript.</span><span class="sxs-lookup"><span data-stu-id="dbc11-121">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="dbc11-122">Функции безопасности Windows PowerShell предназначены для создания среды, в которой пользователи не могут легко или непреднамеренно запускать сценарии.</span><span class="sxs-lookup"><span data-stu-id="dbc11-122">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="dbc11-123">По умолчанию функции безопасности Windows PowerShell включены.</span><span class="sxs-lookup"><span data-stu-id="dbc11-123">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="dbc11-124">Состояние этих функций можно изменять в соответствии с требованиями написания сценариев и различными целями безопасности.</span><span class="sxs-lookup"><span data-stu-id="dbc11-124">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="dbc11-125">Это не означает, что оболочка делает запуск сценариев невозможным для пользователей.</span><span class="sxs-lookup"><span data-stu-id="dbc11-125">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="dbc11-126">Напротив, оболочка по умолчанию затрудняет для пользователей запуск сценариев без понимания того, что они делают.</span><span class="sxs-lookup"><span data-stu-id="dbc11-126">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="dbc11-127">Дополнительные сведения можно найти в [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145)разделе Безопасность сценариев Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dbc11-127">For details, see Windows PowerShell Script Security at [http://go.microsoft.com/fwlink/p/?LinkId=213145](http://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

