---
title: 'Lync Server 2013: Установка базы данных сервера Standard Edition'
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
ms.openlocfilehash: 877a9b8519c6c0e8b0c3e4a92d190f5a55d8861e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197122"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="install-standard-edition-server-database-for-lync-server-2013"></a><span data-ttu-id="28d7e-102">Установка базы данных сервера Standard Edition для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28d7e-102">Install Standard Edition server database for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28d7e-103">_**Последнее изменение темы:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="28d7e-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="28d7e-104">Настройка сервера Standard Edition в качестве единственного сервера в вашей инфраструктуре, который пользователи домов отличаются от других серверных установок в том, что в **мастере развертывания** есть выбор, предназначенный для настройки начального сервера.</span><span class="sxs-lookup"><span data-stu-id="28d7e-104">Setting up a Standard Edition server as the only server in your infrastructure that homes users differs from other server installations in that there is a selection in the **Deployment Wizard** specifically for setting up the initial server.</span></span>

<div>

## <a name="to-install-a-standard-edition-server"></a><span data-ttu-id="28d7e-105">Установка сервера Standard Edition</span><span class="sxs-lookup"><span data-stu-id="28d7e-105">To install a Standard Edition server</span></span>

1.  <span data-ttu-id="28d7e-106">Выполните вход на сервер, на котором будет устанавливаться сервер Standard Edition, в качестве локального администратора или эквивалента домена.</span><span class="sxs-lookup"><span data-stu-id="28d7e-106">Log on to the server where you are going to install Standard Edition server as a local administrator or a domain equivalent.</span></span>

2.  <span data-ttu-id="28d7e-107">Если вы не подготовили доменные службы Active Directory, сначала выполните эти действия.</span><span class="sxs-lookup"><span data-stu-id="28d7e-107">If you have not prepared Active Directory Domain Services, then first perform those procedures.</span></span> <span data-ttu-id="28d7e-108">Дополнительные сведения см. в статье [Подготовка доменных служб Active Directory для Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span><span class="sxs-lookup"><span data-stu-id="28d7e-108">For details, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md).</span></span>

3.  <span data-ttu-id="28d7e-109">В мастере развертывания Lync Server нажмите кнопку **подготовить первый сервер Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="28d7e-109">In the Lync Server Deployment Wizard, click **Prepare first Standard Edition server**.</span></span>

4.  <span data-ttu-id="28d7e-110">На странице **Подготовка отдельного сервера Standard Edition** нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="28d7e-110">On the **Prepare single Standard Edition Server** page, click **Next**.</span></span>

5.  <span data-ttu-id="28d7e-111">На странице **выполнение команд** в качестве центрального хранилища управления устанавливается SQL Server 2012 Express.</span><span class="sxs-lookup"><span data-stu-id="28d7e-111">On the **Executing Commands** page, the SQL Server 2012 Express is installed as the Central Management store.</span></span> <span data-ttu-id="28d7e-112">Создаются необходимые правила брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="28d7e-112">Necessary firewall rules are created.</span></span> <span data-ttu-id="28d7e-113">После завершения установки базы данных и предварительно устанавливаемого ПО нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="28d7e-113">When the installation of the database and prerequisite software is completed, click **Finish**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="28d7e-114">При первоначальной установке может пройти некоторое время, прежде чем на экране вывода результатов команд появятся какие-либо изменения.</span><span class="sxs-lookup"><span data-stu-id="28d7e-114">The initial installation may take some time with no visible updates to the command output summary screen.</span></span> <span data-ttu-id="28d7e-115">Это обусловлено установкой SQL Server Express.</span><span class="sxs-lookup"><span data-stu-id="28d7e-115">This is due to the installation of the SQL Server Express.</span></span> <span data-ttu-id="28d7e-116">Если необходимо отслеживать установку базы данных, используйте для этого диспетчер задач.</span><span class="sxs-lookup"><span data-stu-id="28d7e-116">If you need to monitor the installation of the database, use Task Manager to monitor the setup.</span></span>

    
    </div>

6.  <span data-ttu-id="28d7e-117">На странице мастера развертывания Lync Server щелкните **установить построитель топологий** , если вы еще не установили средства администрирования.</span><span class="sxs-lookup"><span data-stu-id="28d7e-117">On the Lync Server Deployment Wizard page, click **Install Topology Builder** if you have not previously installed the administrative tools.</span></span> <span data-ttu-id="28d7e-118">Для получения дополнительных сведений ознакомьтесь со статьей [Установка средств администрирования Lync Server 2013](lync-server-2013-install-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="28d7e-118">For details, see [Install Lync Server 2013 administrative tools](lync-server-2013-install-lync-server-administrative-tools.md).</span></span>

7.  <span data-ttu-id="28d7e-119">Убедитесь, что рядом с пунктами "Подготовить Active Directory", "Подготовить первый сервер Standard Edition" и "Установить построитель топологий" стоят зеленые галочки.</span><span class="sxs-lookup"><span data-stu-id="28d7e-119">Confirm that there are green check marks next to “Prepare Active Directory,” “Prepare first Standard Edition server,” and “Install Topology Builder.”</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

