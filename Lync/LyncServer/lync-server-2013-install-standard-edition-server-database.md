---
title: 'Lync Server 2013: для установка базы данных сервера Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Standard Edition server database
ms:assetid: 0bd3a804-aad6-48cb-981b-54725af032db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398167(v=OCS.15)
ms:contentKeyID: 48183385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63f2ef304b1a603203d09f260b8d3c7c46e23ccf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="9afc1-102">Установка базы данных сервера Standard Edition для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9afc1-102">Install Standard Edition server database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9afc1-103">_**Тема последнего изменения:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9afc1-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9afc1-104">Настройка стандартного сервера выпусков в качестве единственного сервера в инфраструктуре, которой пользователи не отличаются от других установок сервера в том случае, если у вас есть выбор в **мастере развертывания** специально для настройки первоначального сервера.</span><span class="sxs-lookup"><span data-stu-id="9afc1-104">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="9afc1-105">Установка сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="9afc1-105">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="9afc1-106">Войдите на сервер, на котором вы собираетесь установить стандартный выпуск для локального администратора или эквивалент домена.</span><span class="sxs-lookup"><span data-stu-id="9afc1-106">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="9afc1-107">Если вы не предготовили доменные службы Active Directory, сначала выполните эти действия.</span><span class="sxs-lookup"><span data-stu-id="9afc1-107">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="9afc1-108">Дополнительные сведения можно найти в разделе [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="9afc1-108">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="9afc1-109">В мастере развертывания Lync Server нажмите кнопку **подготовить первый сервер Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="9afc1-109">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="9afc1-110">На странице **подготовить один стандартный выпуск на сервере** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="9afc1-110">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="9afc1-111">На странице **выполнение команд** сервер SQL Server 2012 Express установлен в качестве хранилища центрального управления.</span><span class="sxs-lookup"><span data-stu-id="9afc1-111">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="9afc1-112">Создаются необходимые правила брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="9afc1-112">Necessary firewall rules are created.</span></span> <span data-ttu-id="9afc1-113">После завершения установки базы данных и необходимого программного обеспечения нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="9afc1-113">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9afc1-114">Начальная установка может занять некоторое время и не отменять заметные обновления экрана сводки вывода команды.</span><span class="sxs-lookup"><span data-stu-id="9afc1-114">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="9afc1-115">Это происходит из-за установки SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="9afc1-115">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="9afc1-116">Если вам нужно наблюдать за установкой базы данных, используйте диспетчер задач для наблюдения за настройкой.</span><span class="sxs-lookup"><span data-stu-id="9afc1-116">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="9afc1-117">На странице мастера развертывания Lync Server щелкните **установить построитель топологии** , если вы ранее не установили средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="9afc1-117">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="9afc1-118">Подробности можно найти в разделе [Установка средств администрирования Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9afc1-118">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="9afc1-119">Убедитесь, что рядом с пунктом "Подготовка Active Directory" установлены зеленые галочки, "подготовить первый сервер Standard Edition" и "установить построитель топологии".</span><span class="sxs-lookup"><span data-stu-id="9afc1-119">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

