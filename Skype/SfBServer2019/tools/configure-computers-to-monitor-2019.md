---
title: Настройка отслеживаемых компьютеров Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Сводка. Установка файлов агента Operations Manager на отслеживаемый компьютер Skype для бизнеса Server 2019 и настройка компьютера в качестве прокси-сервера System Center.
ms.openlocfilehash: 08328e430acd4fa651fccd89b827d5c103066dd1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806079"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a><span data-ttu-id="850fd-103">Настройка отслеживаемых компьютеров Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="850fd-103">Configure the Skype for Business Server computers that will be monitored</span></span>

<span data-ttu-id="850fd-104">**Сводка:** Установите файлы агента Operations Manager на отслеживаемый компьютер Skype для бизнеса Server 2019 и настройте компьютер в качестве прокси-сервера System Center.</span><span class="sxs-lookup"><span data-stu-id="850fd-104">**Summary:** Install the Operations Manager agent files on the Skype for Business Server 2019 computer to be monitored, and configure the computer to act as a System Center proxy.</span></span>

<span data-ttu-id="850fd-105">Каждый компьютер Skype для бизнеса Server 2019, который вы хотите отслеживать, должен иметь возможность самостоятельно сообщать о своем существовании серверу управления.</span><span class="sxs-lookup"><span data-stu-id="850fd-105">Each Skype for Business Server 2019 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="850fd-106">Чтобы включить этот процесс, необходимо установить файлы агента Operations Manager на каждом отслеживаемом компьютере.</span><span class="sxs-lookup"><span data-stu-id="850fd-106">To enable this process, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="850fd-107">После установки файлов агента необходимо настроить компьютер в качестве прокси-сервера System Center.</span><span class="sxs-lookup"><span data-stu-id="850fd-107">After installing the agent files, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="850fd-108">Перед началом этих процедур убедитесь, что на этих компьютерах установлен и настроен Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="850fd-108">Be sure that you have first installed and configured Skype for Business Server on these computers before carrying out these procedures.</span></span>

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a><span data-ttu-id="850fd-109">Установка сертификата на узел-наблюдатель, расположенный вне сети периметра</span><span class="sxs-lookup"><span data-stu-id="850fd-109">Installing a Certificate on a Watcher Node Located Outside the Perimeter Network</span></span>
<span data-ttu-id="850fd-110"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="850fd-110"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="850fd-111">Агентам System Center Operations Manager, работающим в сети периметра (например, пограничном сервере Skype для бизнеса Server), за пределами предприятия (например, внешним узлом-посредником искусственных транзакций) или через границу доверия Active Directory, может потребоваться настройка сервера шлюза System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="850fd-111">System Center Operations Manager agents running in a perimeter network (such as a Skype for Business Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory trust boundary, may require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="850fd-112">Эта роль сервера позволяет агентам, которые не имеют отношения доверия с корневым сервером управления, повышать уровень оповещений.</span><span class="sxs-lookup"><span data-stu-id="850fd-112">This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="850fd-113">Подробные сведения см. в под [управлением серверов шлюзов в Operations Manager 2012.](https://technet.microsoft.com/library/hh212823.aspx)</span><span class="sxs-lookup"><span data-stu-id="850fd-113">For details, see [Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/library/hh212823.aspx).</span></span>

<span data-ttu-id="850fd-114">Если агент развернут в одном из этих местоположений, вам также потребуется запросить и настроить сертификат, который позволяет узлу-отправителю отправлять оповещения System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="850fd-114">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="850fd-115">Чтобы упростить этот процесс, группа разработчиков Operations Manager создала набор вспомогательных программ, позволяющих запрашивать и устанавливать нужный тип сертификата на компьютера узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="850fd-115">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="850fd-116">Для получения подробных сведений и загрузки этих средств см. мастер получения сертификатов для агентов, не присоединив к [домену.](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409)</span><span class="sxs-lookup"><span data-stu-id="850fd-116">For details, and to download these utilities, see [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span></span>

### <a name="installing-the-operation-manager-agent-files"></a><span data-ttu-id="850fd-117">Установка файлов агента Operation Manager</span><span class="sxs-lookup"><span data-stu-id="850fd-117">Installing the Operation Manager Agent Files</span></span>

1. <span data-ttu-id="850fd-118">На установок System Center дважды щелкните **Setup.exe.**</span><span class="sxs-lookup"><span data-stu-id="850fd-118">On your System Center setup media, double-click **Setup.exe**.</span></span>

2. <span data-ttu-id="850fd-119">В мастере установки System Center Operation Manager выберите "Установить агент **Operations Manager"** в области "Необязательные установки"</span><span class="sxs-lookup"><span data-stu-id="850fd-119">In the System Center Operation Manager setup wizard, click **Install Operations Manager Agent**, from Install Agent under Optional Installations</span></span>

3. <span data-ttu-id="850fd-120">В мастере установки System Center на странице мастера установки System Center Operations Manager нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="850fd-120">In the System Center setup wizard, on the Welcome to the System Center Operations Manager Setup wizard page, click **Next**.</span></span>

4. <span data-ttu-id="850fd-121">На странице "Папка назначения" выберите папку, в которой будут установлены файлы агента Operations Manager, и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="850fd-121">On the Destination Folder page, select the folder where the Operations Manager Agent files will be installed and click **Next**.</span></span>

5. <span data-ttu-id="850fd-122">На странице "Конфигурация группы управления" выберите **"Укажите сведения о группе управления"** и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="850fd-122">On the Management Group Configuration page, select **Specify Management Group information** and click **Next**.</span></span>

6. <span data-ttu-id="850fd-123">На странице Конфигурация группы управления в поле **Имя группы управления** введите имя группы управления Operations Manager, а в поле **Сервер управления** введите имя узла сервера Operations Manager (например, atl-scom-001).</span><span class="sxs-lookup"><span data-stu-id="850fd-123">On the Management Group Configuration page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="850fd-124">Если номер порта, используемый Operations Manager, изменен, введите новый номер порта в поле **"Порт** сервера управления".</span><span class="sxs-lookup"><span data-stu-id="850fd-124">If you changed the port number used by Operations Manager, enter the new port number in the **Management Server Port** box.</span></span> <span data-ttu-id="850fd-125">В противном случае оставьте порт значением по умолчанию 5723 и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="850fd-125">Otherwise, leave the port at the default value of 5723, and then click **Next**.</span></span>

7. <span data-ttu-id="850fd-126">На странице "Учетная запись действий агента" выберите **"Локализованная система"** и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="850fd-126">On the Agent Action Account page, select **Local System** and click **Next**.</span></span>

8. <span data-ttu-id="850fd-127">На странице "Обновление Майкрософт" выберите "Я не хочу использовать **Microsoft Update"** и нажмите кнопку **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="850fd-127">On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.</span></span>

9. <span data-ttu-id="850fd-128">На странице "Все готово для установки" нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="850fd-128">On the Ready to Install page, click **Install**.</span></span>

10. <span data-ttu-id="850fd-129">На странице Завершение работы мастера установки System Center Operations Manager нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="850fd-129">On the Completing the System Center Operations Manager Setup wizard page, click **Finish**.</span></span>

11. <span data-ttu-id="850fd-130">Щелкните **Exit**.</span><span class="sxs-lookup"><span data-stu-id="850fd-130">Click **Exit**.</span></span>

<span data-ttu-id="850fd-131">Чтобы System Center 2012, можно убедиться, что агент создан, щелкнув "Начните", "Все программы",  **"System Center Operations Manager 2012"** и "Operations **2012 Manager Shell".**</span><span class="sxs-lookup"><span data-stu-id="850fd-131">For System Center 2012, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2012**, and then clicking **Operations 2012 Manager Shell**.</span></span> <span data-ttu-id="850fd-132">В командной оболочке Operations Manager введите следующую Windows PowerShell и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="850fd-132">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>
```PowerShell
Get-SCOMAgent
```

<span data-ttu-id="850fd-133">Появится список всех агентов Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="850fd-133">A list of all your Operations Manager agents will appear.</span></span>
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="850fd-134">Настройка компьютера Skype для бизнеса Server для участия в обнаружении System Center</span><span class="sxs-lookup"><span data-stu-id="850fd-134">Configuring the Skype for Business Server Computer to Participate in System Center Discovery</span></span>
<span data-ttu-id="850fd-135"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="850fd-135"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="850fd-136">Чтобы убедиться, что новый агент Skype для бизнеса Server участвует в процессе обнаружения для System Center Operations Manager, необходимо выполнить следующую процедуру на каждом компьютере, на котором установлена консоль System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="850fd-136">To make sure that your new Skype for Business Server agent participates in the discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1. <span data-ttu-id="850fd-137">На вкладке Администрирование выберите **Управляемые агентом**.</span><span class="sxs-lookup"><span data-stu-id="850fd-137">On the Administration tab, click **Agent Managed**.</span></span>

2. <span data-ttu-id="850fd-138">Щелкните **мастер обнаружения** и завершите мастер обнаружения компьютера.</span><span class="sxs-lookup"><span data-stu-id="850fd-138">Click on **Discovery Wizard** and complete the wizard for the computer to be discovered.</span></span>

3. <span data-ttu-id="850fd-139">Перезагружает службу агента здравоохранения.</span><span class="sxs-lookup"><span data-stu-id="850fd-139">Reboot the Health Agent service.</span></span> <span data-ttu-id="850fd-140">При перезагрузке службы будет принудительно обнаружен новый компьютер.</span><span class="sxs-lookup"><span data-stu-id="850fd-140">Rebooting the service will force discovery of the new machine.</span></span> <span data-ttu-id="850fd-141">Если не перезагружать службу, обнаружение нового компьютера с помощью System Center Operations Manager может занять до 4 часов.</span><span class="sxs-lookup"><span data-stu-id="850fd-141">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.</span></span>

4. <span data-ttu-id="850fd-142">Убедитесь, что в журнал событий Operations Manager не были записаны события ошибок.</span><span class="sxs-lookup"><span data-stu-id="850fd-142">Verify that no error events were recorded in the Operations Manager event log.</span></span>

5. <span data-ttu-id="850fd-143">Компьютер, на который агент успешно перенаправился, будет показан в списке "Управляемый агентом", а компьютер, на котором агент был установлен вручную, будет показан в списке "Отложенное управление", щелкните имя компьютера и утвердим.</span><span class="sxs-lookup"><span data-stu-id="850fd-143">The computer where the agent is pushed successfully will be shown under "Agent Managed" list and the computer where agent was installed manually will be shown under "Pending Management", click on the computer name and approve.</span></span>

6. <span data-ttu-id="850fd-144">Щелкните правой кнопкой мыши имя компьютера и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="850fd-144">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="850fd-145">В диалоговом окне Свойства на вкладке Безопасность выберите **Разрешить агенту работать как прокси и обнаруживать управляемые объекты на других компьютерах**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="850fd-145">In the Properties dialog box, on the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>


