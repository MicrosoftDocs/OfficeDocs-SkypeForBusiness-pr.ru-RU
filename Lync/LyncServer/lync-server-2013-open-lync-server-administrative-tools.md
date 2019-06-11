---
title: 'Lync Server 2013: открытие средств администрирования Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa84c132061cb599448b78cf7d4ffcc6bd7fa3d5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826019"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="open-lync-server-2013-administrative-tools"></a><span data-ttu-id="e5268-102">Открытие меню администрирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5268-102">Open Lync Server 2013 administrative tools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5268-103">_**Тема последнего изменения:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="e5268-103">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="e5268-104">Процедуры, описанные в этом разделе, можно использовать для запуска средств администрирования для развертывания, настройки и устранения неполадок в топологии Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5268-104">You can use the procedures in this topic to open administrative tools to deploy, configure, or troubleshoot your Lync Server 2013 topology.</span></span>

  - <span data-ttu-id="e5268-105">Мастер развертывания</span><span class="sxs-lookup"><span data-stu-id="e5268-105">Deployment Wizard</span></span>

  - <span data-ttu-id="e5268-106">топологий</span><span class="sxs-lookup"><span data-stu-id="e5268-106">Topology Builder</span></span>

  - <span data-ttu-id="e5268-107">Панель управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="e5268-107">Lync Server Control Panel</span></span>

  - <span data-ttu-id="e5268-108">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="e5268-108">Lync Server Management Shell</span></span>

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="e5268-109">Мастер развертывания</span><span class="sxs-lookup"><span data-stu-id="e5268-109">Deployment Wizard</span></span>

<span data-ttu-id="e5268-110">Используйте описанную ниже процедуру, чтобы запустить мастер развертывания локально, чтобы добавить или удалить файлы компонентов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5268-110">Use the following procedure to start the Deployment Wizard locally to add or remove Lync Server 2013 component files.</span></span>

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a><span data-ttu-id="e5268-111">Запуск мастера развертывания Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5268-111">To start Lync Server 2013 Deployment Wizard</span></span>

1.  <span data-ttu-id="e5268-112">Войдите в систему на компьютере, на котором установлен мастер развертывания Lync Server, в группе Администраторы домена и в группу Рткуниверсалсерверадминс.</span><span class="sxs-lookup"><span data-stu-id="e5268-112">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="e5268-113">Нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Мастер развертывания Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e5268-113">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a><span data-ttu-id="e5268-114">топологий</span><span class="sxs-lookup"><span data-stu-id="e5268-114">Topology Builder</span></span>

<span data-ttu-id="e5268-115">Используйте описанную ниже процедуру, чтобы открыть построитель топологии, чтобы определить серверы, которые нужно развернуть в топологии Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5268-115">Use the following procedure to open the Topology Builder to define the servers that you want to deploy in your Lync Server 2013 topology.</span></span>

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a><span data-ttu-id="e5268-116">Открытие построителя топологии Lync Server 2013 для создания топологии</span><span class="sxs-lookup"><span data-stu-id="e5268-116">To open Lync Server 2013 Topology Builder to design the topology</span></span>

1.  <span data-ttu-id="e5268-117">Войдите на компьютер, где установлен построитель топологий, с использованием учетной записи, входящей в группу администраторов домена и группу RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="e5268-117">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e5268-118">Вы можете определить топологию с помощью учетной записи, которая является членом локальной группы пользователей, но для чтения, публикации или включения топологии, необходимой для установки Lync Server 2013 на сервере, необходимо использовать учетную запись, которая входит в группу администраторов домена и Рткунив Ерсалсерверадминс, и у него есть разрешения на полный доступ (то есть чтение, запись и изменение) в общей папке, которую вы собираетесь использовать в хранилище файлов для архивации, чтобы построитель топологии мог настроить требуемый список управления доступом на уровне пользователей (DACL), или учетной записи с эквивалентными правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="e5268-118">You can define a topology by using an account that is a member of the local Users group, but to read, publish, or enable a topology, which is required to install Lync Server 2013 on a server, you must use an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group, and that has full control permissions (that is, read, write, and modify) on the file share that you are going to use for the archiving file store so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent user rights.</span></span>

    
    </div>

2.  <span data-ttu-id="e5268-119">Запустить построитель топологии: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Lync Server 2013**и нажмите кнопку Построитель **топологии Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="e5268-119">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a><span data-ttu-id="e5268-120">управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5268-120">Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="e5268-121">Чтобы открыть панель управления Lync Server 2013 для управления конфигурацией серверов, пользователей, клиентов и устройств в среде, воспользуйтесь одной из приведенных ниже процедур.</span><span class="sxs-lookup"><span data-stu-id="e5268-121">Use one of the following procedures to open Lync Server 2013 Control Panel to manage the configuration of servers, users, clients, and devices in your environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5268-122">Вы можете использовать учетную запись пользователя, назначенную роли Ксадминистратор, для выполнения любой задачи в панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5268-122">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="e5268-123">Вы можете использовать другие роли для входа в панель управления Lync Server 2013 для выполнения конкретных задач администрирования, зависящие от задачи, которую необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="e5268-123">You can use other roles to log on to Lync Server 2013 Control Panel to perform specific administration tasks, dependent on the task you need to perform.</span></span> <span data-ttu-id="e5268-124">Например, вы можете использовать Ксарчивингадминистратор для управления архивацией на панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5268-124">For example, you can use CSArchivingAdministrator to administer Archiving in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="e5268-125">Сведения о ролях можно найти <A href="lync-server-2013-planning-for-role-based-access-control.md">в разделе Планирование управления доступом на основе ролей в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e5268-125">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="e5268-126">Подробные сведения о ролях, которые можно использовать для выполнения определенной задачи, описаны в документации по задаче.</span><span class="sxs-lookup"><span data-stu-id="e5268-126">For details about the roles that you can use to perform a specific task, see the documentation for the task.</span></span>



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a><span data-ttu-id="e5268-127">Открытие панели управления Lync Server 2013 с любого компьютера в брандмауэре организации</span><span class="sxs-lookup"><span data-stu-id="e5268-127">To open Lync Server 2013 Control Panel from any computer inside your organization’s firewall</span></span>

1.  <span data-ttu-id="e5268-128">Войдите в учетную запись пользователя, которой назначена роль Ксадминистратор или другая роль, которая имеет соответствующие права и разрешения для выполнения задачи, выполните вход на любом компьютере во внутренней среде с минимальным разрешением экрана 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="e5268-128">From a user account that is assigned to the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to any computer in your internal deployment with a minimum screen resolution of 1024 x 768.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e5268-129">Если вы настроили адрес URL для администрирования, вы можете получить доступ к панели управления Lync Server 2013 из Интернет-браузера, который запущен на любом компьютере в брандмауэре организации.</span><span class="sxs-lookup"><span data-stu-id="e5268-129">If you have configured an administration simple uniform resource locator (URL), you can access Lync Server 2013 Control Panel from an Internet browser that is running on any computer within your organization’s firewall.</span></span> <span data-ttu-id="e5268-130">Подробнее о настройке простого URL-адреса администрирования можно узнать в разделе <A href="lync-server-2013-planning-for-simple-urls.md">планирование простых URL-адресов в Lync server 2013</A> в документации по планированию, а <A href="lync-server-2013-edit-or-configure-simple-urls.md">также изменить или настроить простые URL-адреса в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="e5268-130">For details about configuring the administration simple URL, see <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A> in the Planning documentation and <A href="lync-server-2013-edit-or-configure-simple-urls.md">Edit or configure simple URLs in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

2.  <span data-ttu-id="e5268-131">Откройте окно браузера и введите URL-адрес администратора, настроенный для Организации.</span><span class="sxs-lookup"><span data-stu-id="e5268-131">Open a browser window, and then enter the Admin URL configured for your organization.</span></span>

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a><span data-ttu-id="e5268-132">Открытие панели управления Lync Server 2013 на компьютере с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5268-132">To open Lync Server 2013 Control Panel on a computer running Lync Server 2013</span></span>

1.  <span data-ttu-id="e5268-133">Войдите в систему с учетной записью пользователя, которая является членом роли Ксадминистратор или другой роли, обладающей необходимыми правами и разрешениями для выполнения задачи, выполните вход на компьютер, на котором установлен Lync Server 2013 или, по крайней мере, для Lync Server 2013 для администрирования полученные инструменты.</span><span class="sxs-lookup"><span data-stu-id="e5268-133">From a user account that is a member of the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to a computer on which you have installed Lync Server 2013 or, at a minimum, the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="e5268-134">Для настройки параметров на компьютере должно быть установлено минимальное разрешение экрана 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="e5268-134">To configure settings, the computer must have a minimum screen resolution of 1024 x 768.</span></span>

2.  <span data-ttu-id="e5268-135">Откройте панель управления Lync Server 2013: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Администрирование**, наведите указатель мыши на **Microsoft Lync Server 2013**и выберите пункт **Панель управления Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="e5268-135">Start Lync Server 2013 Control Panel: Click **Start**, click **All Programs**, point to **Administrative Tools**, point to **Microsoft Lync Server 2013**, and then click **Lync Server 2013 Control Panel**.</span></span>

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a><span data-ttu-id="e5268-136">командная консоль Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5268-136">Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="e5268-137">Выполните указанные ниже действия, чтобы открыть командную консоль Lync Server 2013 для управления серверами, пользователями, клиентами и устройствами в среде с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="e5268-137">Use the following procedure to open Lync Server 2013 Management Shell to administer servers, users, clients, and devices in your environment by using the command line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e5268-138">Вы можете использовать учетную запись пользователя, назначенную роли Ксадминистратор, для выполнения любой задачи в командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5268-138">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="e5268-139">Вы можете войти в систему, используя другие роли для выполнения конкретных задач администрирования, в зависимости от задачи, которую необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="e5268-139">You can log on using other roles to perform specific administration tasks, depending on the task you need to perform.</span></span> <span data-ttu-id="e5268-140">Например, для запуска командлетов, связанных с администрированием архивации, можно использовать Ксарчивингадминистратор.</span><span class="sxs-lookup"><span data-stu-id="e5268-140">For example, you can use CSArchivingAdministrator to run cmdlets related to Archiving administration.</span></span> <span data-ttu-id="e5268-141">Сведения о ролях можно найти <A href="lync-server-2013-planning-for-role-based-access-control.md">в разделе Планирование управления доступом на основе ролей в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="e5268-141">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="e5268-142">Подробные сведения о ролях, которые можно использовать для выполнения определенного командлета, описаны в документации для командлета.</span><span class="sxs-lookup"><span data-stu-id="e5268-142">For details about the roles that you can use to run a specific cmdlet, see the documentation for the cmdlet.</span></span><BR><span data-ttu-id="e5268-143">Вы также можете запускать определенные командлеты с помощью учетной записи пользователя в группах Рткуниверсалсерверадминс, Рткуниверсалусерадминс или Рткуниверсалреадонлядминс, в зависимости от командлета.</span><span class="sxs-lookup"><span data-stu-id="e5268-143">You can also run certain cmdlets by using a user account in the RTCUniversalServerAdmins, RTCUniversalUserAdmins, or RTCUniversalReadOnlyAdmins groups, depending on the cmdlet.</span></span>



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a><span data-ttu-id="e5268-144">Открытие управляющей оболочки Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5268-144">To open the Lync Server 2013 Management Shell</span></span>

  - <span data-ttu-id="e5268-145">Если вы открыли окно Windows PowerShell вместо командной консоли Lync Server 2013, по умолчанию не удается запустить командлеты Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e5268-145">If you open a Windows PowerShell window rather than the Lync Server 2013 Management Shell, by default you cannot run the Lync Server 2013 cmdlets.</span></span> <span data-ttu-id="e5268-146">Чтобы запустить командлеты Lync Server 2013 из Windows PowerShell, введите следующую команду в командной строке Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="e5268-146">To run the Lync Server 2013 cmdlets from within Windows PowerShell, type the following at the Windows PowerShell command prompt:</span></span>
    
    `Import-Module Lync`

  - <span data-ttu-id="e5268-147">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="e5268-147">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e5268-148">См. также</span><span class="sxs-lookup"><span data-stu-id="e5268-148">See Also</span></span>


[<span data-ttu-id="e5268-149">Установка средств администрирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5268-149">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)  


[<span data-ttu-id="e5268-150">Средства администрирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5268-150">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

