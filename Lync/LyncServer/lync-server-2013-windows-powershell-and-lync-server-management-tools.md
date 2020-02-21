---
title: 'Lync Server 2013: средства управления Windows PowerShell и Lync Server'
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
ms.openlocfilehash: c24a94bf74b2ecf911179d64691e95153acceeeb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210210"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="windows-powershell-and-lync-server-2013-management-tools"></a><span data-ttu-id="a671b-102">Средства управления Windows PowerShell и Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a671b-102">Windows PowerShell and Lync Server 2013 management tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a671b-103">_**Последнее изменение темы:** 2016-07-20_</span><span class="sxs-lookup"><span data-stu-id="a671b-103">_**Topic Last Modified:** 2016-07-20_</span></span>

<span data-ttu-id="a671b-104">В Microsoft Lync Server 2013 средства управления реализованы с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a671b-104">In Microsoft Lync Server 2013, management tools are implemented using Windows PowerShell.</span></span> <span data-ttu-id="a671b-105">Windows PowerShell включает в себя среду командной строки, зависящие от продукта команды и полный язык сценариев.</span><span class="sxs-lookup"><span data-stu-id="a671b-105">Windows PowerShell includes a command-line environment, product-specific commands, and a full scripting language.</span></span> <span data-ttu-id="a671b-106">Lync Server 2013 Tools, реализованные с помощью Windows PowerShell, включают следующие:</span><span class="sxs-lookup"><span data-stu-id="a671b-106">Lync Server 2013 tools that are implemented using Windows PowerShell include the following:</span></span>

  - <span data-ttu-id="a671b-107">**Построитель топологий**.</span><span class="sxs-lookup"><span data-stu-id="a671b-107">**Topology Builder**.</span></span> <span data-ttu-id="a671b-108">Построитель топологий используется для создания, настройки и публикации запланированной топологии, а также для проверки топологии перед началом установки сервера.</span><span class="sxs-lookup"><span data-stu-id="a671b-108">You use Topology Builder to create, adjust, and publish your planned topology, and it validates your topology before you begin server installations.</span></span> <span data-ttu-id="a671b-109">При установке Lync Server 2013 на отдельных серверах серверы просчитываются опубликованную топологию как часть процесса установки, а программа установки развертывает сервер в соответствии с топологией.</span><span class="sxs-lookup"><span data-stu-id="a671b-109">When you install Lync Server 2013 on individual servers, the servers read the published topology as part of the installation process, and the installation program deploys the server as directed in the topology.</span></span> <span data-ttu-id="a671b-110">После установки сведения о конфигурации автоматически реплицируются на все серверы.</span><span class="sxs-lookup"><span data-stu-id="a671b-110">After setup, configuration information is automatically replicated to all servers.</span></span> <span data-ttu-id="a671b-111">Компоненты можно добавлять в развертывание только с помощью построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="a671b-111">Components can be added to your deployment only by using Topology Builder.</span></span>

  - <span data-ttu-id="a671b-112">**Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a671b-112">**Lync Server Management Shell**.</span></span> <span data-ttu-id="a671b-113">Консоль управления Lync Server можно использовать для полного управления развертыванием с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="a671b-113">You can use Lync Server Management Shell for full command-line management of your deployment.</span></span>

  - <span data-ttu-id="a671b-114">**Панель управления Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a671b-114">**Lync Server Control Panel**.</span></span> <span data-ttu-id="a671b-115">Вы можете использовать пользовательский интерфейс панели управления Microsoft Lync Server 2013 для управления наиболее распространенными задачами в развертывании.</span><span class="sxs-lookup"><span data-stu-id="a671b-115">You can use the Microsoft Lync Server 2013 Control Panel user interface to manage the most common tasks in your deployment.</span></span>

<span data-ttu-id="a671b-116">Эти средства используют командлеты Windows PowerShell для управления развертыванием, в том числе с помощью командлетов, относящихся к определенному продукту 550.</span><span class="sxs-lookup"><span data-stu-id="a671b-116">These tools use Windows PowerShell cmdlets for management of your deployment, including close to 550 product-specific cmdlets.</span></span> <span data-ttu-id="a671b-117">Командлеты безопасности, включенные в Lync Server 2013, в основном используются для управления проверкой подлинности, а также правами и разрешениями пользователей.</span><span class="sxs-lookup"><span data-stu-id="a671b-117">The security cmdlets included in Lync Server 2013 are primarily used to manage authentication, and user rights and permissions.</span></span> <span data-ttu-id="a671b-118">Широкий спектр командлетов доступен для управления проверкой подлинности, включая командлеты для проверки подлинности с помощью сертификатов и персональных идентификационных номеров (ПИН-кодов).</span><span class="sxs-lookup"><span data-stu-id="a671b-118">A wide variety of cmdlets are available for managing authentication, including cmdlets for certificate and personal identification number (PIN) authentication.</span></span> <span data-ttu-id="a671b-119">Кроме того, несколько командлетов позволяют использовать новую функцию управления доступом на основе ролей (RBAC) для делегирования административного управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a671b-119">In addition, a number of cmdlets enable you to use the new Role-Based Access Control (RBAC) feature to delegate administrative control of Lync Server 2013.</span></span> <span data-ttu-id="a671b-120">Дополнительные сведения о командлетах Lync Server приведены в статье [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="a671b-120">For details about the Lync Server cmdlets, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

<span data-ttu-id="a671b-121">Функции безопасности скриптов для Windows PowerShell специально разработаны, чтобы помочь предотвратить некоторые проблемы безопасности, связанные с сценариями старых технологий, в том числе VBScript (VBScript).</span><span class="sxs-lookup"><span data-stu-id="a671b-121">The script security features for Windows PowerShell are specifically designed to help prevent some of the scripting-related security problems of older technologies, including Microsoft Visual Basic Scripting Edition (VBScript).</span></span> <span data-ttu-id="a671b-122">Функции безопасности Windows PowerShell предназначены для создания среды, в которой пользователи не могут легко или непреднамеренно запускать сценарии.</span><span class="sxs-lookup"><span data-stu-id="a671b-122">The Windows PowerShell security features are intended to create an environment in which users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="a671b-123">По умолчанию функции безопасности Windows PowerShell включены.</span><span class="sxs-lookup"><span data-stu-id="a671b-123">By default, Windows PowerShell security features are enabled.</span></span> <span data-ttu-id="a671b-124">Вы можете изменить состояние этих функций в соответствии с потребностями сценариев и различными целями обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="a671b-124">You can modify the state of those features to accommodate your scripting needs and a variety of security goals.</span></span> <span data-ttu-id="a671b-125">Это не означает, что командная консоль делает невозможной для пользователей запускать скрипты.</span><span class="sxs-lookup"><span data-stu-id="a671b-125">This is not to say that the shell makes it impossible for users to run scripts.</span></span> <span data-ttu-id="a671b-126">Вместо этого оболочка по умолчанию делает ее недостаточной, чтобы пользователи могли запускать сценарии, не зная этого.</span><span class="sxs-lookup"><span data-stu-id="a671b-126">Rather, the shell makes it difficult—by default—for users to run scripts without realizing they are doing so.</span></span> <span data-ttu-id="a671b-127">Дополнительные сведения см. в разделе Безопасность сценариев Windows [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145)PowerShell в.</span><span class="sxs-lookup"><span data-stu-id="a671b-127">For details, see Windows PowerShell Script Security at [https://go.microsoft.com/fwlink/p/?LinkId=213145](https://go.microsoft.com/fwlink/p/?linkid=213145).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

