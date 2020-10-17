---
title: 'Lync Server 2013: открытие средств администрирования Lync Server'
description: 'Lync Server 2013: Откройте инструменты администрирования Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Open Lync Server administrative tools
ms:assetid: 8c58de94-9e0a-4368-9e14-9afcaa1142d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195741(v=OCS.15)
ms:contentKeyID: 48184778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01cf0dc0c17686e2b1c7bee17bdc383ab6247909
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544765"
---
# <a name="open-lync-server-2013-administrative-tools"></a><span data-ttu-id="861f1-103">Откройте Lync Server 2013 администрирование</span><span class="sxs-lookup"><span data-stu-id="861f1-103">Open Lync Server 2013 administrative tools</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="861f1-104">_**Последнее изменение темы:** 2012-06-28_</span><span class="sxs-lookup"><span data-stu-id="861f1-104">_**Topic Last Modified:** 2012-06-28_</span></span>

<span data-ttu-id="861f1-105">С помощью процедур, описанных в этом разделе, можно открывать средства администрирования для развертывания, настройки или устранения неполадок в топологии Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="861f1-105">You can use the procedures in this topic to open administrative tools to deploy, configure, or troubleshoot your Lync Server 2013 topology.</span></span>

  - <span data-ttu-id="861f1-106">Мастер развертывания</span><span class="sxs-lookup"><span data-stu-id="861f1-106">Deployment Wizard</span></span>

  - <span data-ttu-id="861f1-107">Построитель топологий</span><span class="sxs-lookup"><span data-stu-id="861f1-107">Topology Builder</span></span>

  - <span data-ttu-id="861f1-108">Панель управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="861f1-108">Lync Server Control Panel</span></span>

  - <span data-ttu-id="861f1-109">Командная консоль Lync Server</span><span class="sxs-lookup"><span data-stu-id="861f1-109">Lync Server Management Shell</span></span>

<span id="BKMK_OpenDeploymentWizard"></span>

<div>

## <a name="deployment-wizard"></a><span data-ttu-id="861f1-110">Мастер развертывания</span><span class="sxs-lookup"><span data-stu-id="861f1-110">Deployment Wizard</span></span>

<span data-ttu-id="861f1-111">Используйте следующую процедуру, чтобы запустить мастер развертывания локально, чтобы добавить или удалить файлы компонентов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="861f1-111">Use the following procedure to start the Deployment Wizard locally to add or remove Lync Server 2013 component files.</span></span>

<div>

## <a name="to-start-lync-server-2013-deployment-wizard"></a><span data-ttu-id="861f1-112">Запуск мастера развертывания Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="861f1-112">To start Lync Server 2013 Deployment Wizard</span></span>

1.  <span data-ttu-id="861f1-113">Выполните вход на компьютер, на котором установлен мастер развертывания Lync Server, в качестве члена группы администраторов домена и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="861f1-113">Log on to the computer where the Lync Server Deployment Wizard is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>

2.  <span data-ttu-id="861f1-114">Нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Мастер развертывания Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="861f1-114">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Deployment Wizard**.</span></span>

</div>

</div>

<span id="BKMK_OpenTopologyBuilder"></span>

<div>

## <a name="topology-builder"></a><span data-ttu-id="861f1-115">Построитель топологий</span><span class="sxs-lookup"><span data-stu-id="861f1-115">Topology Builder</span></span>

<span data-ttu-id="861f1-116">Используйте следующую процедуру, чтобы открыть построитель топологий, чтобы определить серверы, которые необходимо развернуть в топологии Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="861f1-116">Use the following procedure to open the Topology Builder to define the servers that you want to deploy in your Lync Server 2013 topology.</span></span>

<div>

## <a name="to-open-lync-server-2013-topology-builder-to-design-the-topology"></a><span data-ttu-id="861f1-117">Открытие построителя топологий Lync Server 2013 для создания топологии</span><span class="sxs-lookup"><span data-stu-id="861f1-117">To open Lync Server 2013 Topology Builder to design the topology</span></span>

1.  <span data-ttu-id="861f1-118">Войдите в систему компьютера, на котором построитель топологий установлен как член группы администраторов доменов и группы RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="861f1-118">Log on to the computer where Topology Builder is installed as a member of the Domain Admins group and the RTCUniversalServerAdmins group.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="861f1-119">Вы можете определить топологию с помощью учетной записи, которая является членом локальной группы "Пользователи", но для чтения, публикации или включения топологии, необходимой для установки Lync Server 2013 на сервере, необходимо использовать учетную запись, входящую в группу "Администраторы домена" и группу RTCUniversalServerAdmins, которая имеет разрешения полного доступа ( , чтение, запись и изменение в общей папке, которую вы собираетесь использовать для архивного хранилища файлов, чтобы построитель топологий мог настроить необходимый избирательный список управления доступом (DACL) или учетную запись с эквивалентными правами пользователя.</span><span class="sxs-lookup"><span data-stu-id="861f1-119">You can define a topology by using an account that is a member of the local Users group, but to read, publish, or enable a topology, which is required to install Lync Server 2013 on a server, you must use an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group, and that has full control permissions (that is, read, write, and modify) on the file share that you are going to use for the archiving file store so that Topology Builder can configure the required discretionary access control list (DACLs), or an account with equivalent user rights.</span></span>

    
    </div>

2.  <span data-ttu-id="861f1-120">Запустите построитель топологий: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Microsoft Lync Server 2013**и **Построитель топологий Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="861f1-120">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

</div>

</div>

<span id="BKMK_OpenControlPanel"></span>

<div>

## <a name="lync-server-2013-control-panel"></a><span data-ttu-id="861f1-121">Панель управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="861f1-121">Lync Server 2013 Control Panel</span></span>

<span data-ttu-id="861f1-122">Используйте одну из следующих процедур, чтобы открыть панель управления Lync Server 2013 для управления конфигурацией серверов, пользователей, клиентов и устройств в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="861f1-122">Use one of the following procedures to open Lync Server 2013 Control Panel to manage the configuration of servers, users, clients, and devices in your environment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="861f1-123">С помощью учетной записи пользователя, назначенной роли CsAdministrator, можно выполнять какие-либо задачи в панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="861f1-123">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="861f1-124">С помощью других ролей можно войти на панель управления Lync Server 2013, чтобы выполнять определенные задачи администрирования, зависящие от задачи, которую необходимо выполнить.</span><span class="sxs-lookup"><span data-stu-id="861f1-124">You can use other roles to log on to Lync Server 2013 Control Panel to perform specific administration tasks, dependent on the task you need to perform.</span></span> <span data-ttu-id="861f1-125">Например, вы можете использовать роли csarchivingadministrator для управления архивацией в панели управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="861f1-125">For example, you can use CSArchivingAdministrator to administer Archiving in Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="861f1-126">Сведения о ролях приведены в статье <A href="lync-server-2013-planning-for-role-based-access-control.md">Планирование управления доступом на основе ролей в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="861f1-126">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="861f1-127">Подробные сведения о ролях, которые можно использовать для выполнения особых задач, см. в документации по этим задачам.</span><span class="sxs-lookup"><span data-stu-id="861f1-127">For details about the roles that you can use to perform a specific task, see the documentation for the task.</span></span>



</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-from-any-computer-inside-your-organizations-firewall"></a><span data-ttu-id="861f1-128">Открытие панели управления Lync Server 2013 с любого компьютера в брандмауэре организации</span><span class="sxs-lookup"><span data-stu-id="861f1-128">To open Lync Server 2013 Control Panel from any computer inside your organization’s firewall</span></span>

1.  <span data-ttu-id="861f1-129">С помощью учетной записи, которой назначена роль CsAdministrator или другая роль с соответствующими правами и разрешениями для выполняемой задачи, войдите в любой компьютер во внутреннем развертывании, разрешение экрана которого не ниже 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="861f1-129">From a user account that is assigned to the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to any computer in your internal deployment with a minimum screen resolution of 1024 x 768.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="861f1-130">Если вы настроили простой URL-адрес администрирования, вы можете получить доступ к панели управления Lync Server 2013 из Интернет-браузера, запущенного на любом компьютере в брандмауэре организации.</span><span class="sxs-lookup"><span data-stu-id="861f1-130">If you have configured an administration simple uniform resource locator (URL), you can access Lync Server 2013 Control Panel from an Internet browser that is running on any computer within your organization’s firewall.</span></span> <span data-ttu-id="861f1-131">Подробнее о настройке простого URL-адреса администрирования можно узнать в статье <A href="lync-server-2013-planning-for-simple-urls.md">планирование простых URL-адресов в Lync Server 2013</A> в документации по планированию, а <A href="lync-server-2013-edit-or-configure-simple-urls.md">также изменить или настроить простые URL-адреса в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="861f1-131">For details about configuring the administration simple URL, see <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A> in the Planning documentation and <A href="lync-server-2013-edit-or-configure-simple-urls.md">Edit or configure simple URLs in Lync Server 2013</A> in the Deployment documentation.</span></span>

    
    </div>

2.  <span data-ttu-id="861f1-132">Откройте окно браузера и введите URL-адрес администрирования, настроенный для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="861f1-132">Open a browser window, and then enter the Admin URL configured for your organization.</span></span>

</div>

<div>

## <a name="to-open-lync-server-2013-control-panel-on-a-computer-running-lync-server-2013"></a><span data-ttu-id="861f1-133">Открытие панели управления Lync Server 2013 на компьютере, на котором запущен Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="861f1-133">To open Lync Server 2013 Control Panel on a computer running Lync Server 2013</span></span>

1.  <span data-ttu-id="861f1-134">С учетной записью пользователя, которая является участником роли CsAdministrator или другой роли с соответствующими правами и разрешениями для выполняемой задачи, выполните вход на компьютер, на котором установлен Lync Server 2013 или, по крайней мере, с помощью средств администрирования Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="861f1-134">From a user account that is a member of the CsAdministrator role or other role that has appropriate user rights and permissions for the task to be performed, log on to a computer on which you have installed Lync Server 2013 or, at a minimum, the Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="861f1-135">Для настройки параметров разрешение экрана компьютера должно быть не ниже 1024 x 768.</span><span class="sxs-lookup"><span data-stu-id="861f1-135">To configure settings, the computer must have a minimum screen resolution of 1024 x 768.</span></span>

2.  <span data-ttu-id="861f1-136">Запустите Lync Server 2013 панель управления: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **администрирование**, **Microsoft Lync server 2013**и **Панель управления Lync Server 2013**.</span><span class="sxs-lookup"><span data-stu-id="861f1-136">Start Lync Server 2013 Control Panel: Click **Start**, click **All Programs**, point to **Administrative Tools**, point to **Microsoft Lync Server 2013**, and then click **Lync Server 2013 Control Panel**.</span></span>

</div>

</div>

<span id="BKMK_OpenManagementShell"></span>

<div>

## <a name="lync-server-2013-management-shell"></a><span data-ttu-id="861f1-137">Lync Server 2013 Management Shell</span><span class="sxs-lookup"><span data-stu-id="861f1-137">Lync Server 2013 Management Shell</span></span>

<span data-ttu-id="861f1-138">Используйте следующую процедуру, чтобы открыть консоль управления Lync Server 2013 для администрирования серверов, пользователей, клиентов и устройств в вашей среде с помощью командной строки.</span><span class="sxs-lookup"><span data-stu-id="861f1-138">Use the following procedure to open Lync Server 2013 Management Shell to administer servers, users, clients, and devices in your environment by using the command line.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="861f1-139">С помощью учетной записи пользователя, назначенной роли CsAdministrator, можно выполнять какие-либо задачи в среде управления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="861f1-139">You can use a user account that is assigned to the CsAdministrator role to perform any task in Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="861f1-140">Для выполнения особых административных задач можно использовать для входа другие роли, в зависимости от конкретной задачи.</span><span class="sxs-lookup"><span data-stu-id="861f1-140">You can log on using other roles to perform specific administration tasks, depending on the task you need to perform.</span></span> <span data-ttu-id="861f1-141">Например, роль CSArchivingAdministrator можно использовать для запуска командлетов, имеющих отношение к администрированию архивации.</span><span class="sxs-lookup"><span data-stu-id="861f1-141">For example, you can use CSArchivingAdministrator to run cmdlets related to Archiving administration.</span></span> <span data-ttu-id="861f1-142">Сведения о ролях приведены в статье <A href="lync-server-2013-planning-for-role-based-access-control.md">Планирование управления доступом на основе ролей в Lync Server 2013</A> в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="861f1-142">For details about roles, see <A href="lync-server-2013-planning-for-role-based-access-control.md">Planning for role-based access control in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="861f1-143">Подробные сведения о ролях, которые можно использовать для выполнения конкретных командлетов, см. в документации по этим командлетам.</span><span class="sxs-lookup"><span data-stu-id="861f1-143">For details about the roles that you can use to run a specific cmdlet, see the documentation for the cmdlet.</span></span><BR><span data-ttu-id="861f1-144">Определенные командлеты можно также выполнять с помощью пользовательской учетной записи, входящей в группу RTCUniversalServerAdmins, RTCUniversalUserAdmins или RTCUniversalReadOnlyAdmins, в зависимости от командлета.</span><span class="sxs-lookup"><span data-stu-id="861f1-144">You can also run certain cmdlets by using a user account in the RTCUniversalServerAdmins, RTCUniversalUserAdmins, or RTCUniversalReadOnlyAdmins groups, depending on the cmdlet.</span></span>



</div>

<div>

## <a name="to-open-the-lync-server-2013-management-shell"></a><span data-ttu-id="861f1-145">Открытие консоли управления Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="861f1-145">To open the Lync Server 2013 Management Shell</span></span>

  - <span data-ttu-id="861f1-146">Если открыть окно Windows PowerShell, а не среду управления Lync Server 2013, по умолчанию командлеты Lync Server 2013 выполнить невозможно.</span><span class="sxs-lookup"><span data-stu-id="861f1-146">If you open a Windows PowerShell window rather than the Lync Server 2013 Management Shell, by default you cannot run the Lync Server 2013 cmdlets.</span></span> <span data-ttu-id="861f1-147">Чтобы запустить командлеты Lync Server 2013 в Windows PowerShell, введите в командной строку Windows PowerShell следующую команду:</span><span class="sxs-lookup"><span data-stu-id="861f1-147">To run the Lync Server 2013 cmdlets from within Windows PowerShell, type the following at the Windows PowerShell command prompt:</span></span>
    
    `Import-Module Lync`

  - <span data-ttu-id="861f1-148">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="861f1-148">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="861f1-149">См. также</span><span class="sxs-lookup"><span data-stu-id="861f1-149">See Also</span></span>


[<span data-ttu-id="861f1-150">Установка средств администрирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="861f1-150">Install Lync Server 2013 administrative tools</span></span>](lync-server-2013-install-lync-server-administrative-tools.md)  


[<span data-ttu-id="861f1-151">Lync Server 2013 административные средства</span><span class="sxs-lookup"><span data-stu-id="861f1-151">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

