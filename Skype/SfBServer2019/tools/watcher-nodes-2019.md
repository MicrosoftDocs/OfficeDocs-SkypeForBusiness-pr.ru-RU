---
title: Настройка компьютеров Skype для бизнеса Server, которые будут отслеживаться
ms.reviewer: ''
ms.author: v-lanac
author: LanaChin
manager: serdars
ms.date: 11/7/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Сводка: Установка файлов агента Operations Manager на компьютере Skype для бизнеса Server 2019 для мониторинга и Настройка компьютера для работы в качестве прокси-сервера System Center.'
ms.openlocfilehash: 062dfeb4b03cbe68de21bcb4ea8722bf0f666070
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150490"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a><span data-ttu-id="21efa-103">Настройка компьютеров Skype для бизнеса Server, которые будут отслеживаться</span><span class="sxs-lookup"><span data-stu-id="21efa-103">Configure the Skype for Business Server computers that will be monitored</span></span>

<span data-ttu-id="21efa-104">**Сводка:** Установка файлов агента Operations Manager на компьютере Skype для бизнеса Server 2019 для мониторинга и Настройка компьютера для работы в качестве прокси-сервера System Center.</span><span class="sxs-lookup"><span data-stu-id="21efa-104">**Summary:** Install the Operations Manager agent files on the Skype for Business Server 2019 computer to be monitored, and configure the computer to act as a System Center proxy.</span></span>

<span data-ttu-id="21efa-105">Каждый компьютер Skype для бизнеса Server 2019, который необходимо отслеживать, должен иметь возможность самостоятельного отчета о существовании сервера управления.</span><span class="sxs-lookup"><span data-stu-id="21efa-105">Each Skype for Business Server 2019 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="21efa-106">Чтобы включить этот процесс, необходимо установить файлы агента Operations Manager на каждом компьютере, который будет отслеживаться.</span><span class="sxs-lookup"><span data-stu-id="21efa-106">To enable this process, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="21efa-107">После установки файлов агента необходимо настроить компьютер для работы в качестве прокси-сервера System Center.</span><span class="sxs-lookup"><span data-stu-id="21efa-107">After installing the agent files, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="21efa-108">Перед выполнением этих процедур убедитесь в том, что на этих компьютерах установлен и настроен Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="21efa-108">Be sure that you have first installed and configured Skype for Business Server on these computers before carrying out these procedures.</span></span>

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a><span data-ttu-id="21efa-109">Установка сертификата на узел-наблюдатель, расположенный вне сети периметра</span><span class="sxs-lookup"><span data-stu-id="21efa-109">Installing a Certificate on a Watcher Node Located Outside the Perimeter Network</span></span>
<span data-ttu-id="21efa-110"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="21efa-110"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="21efa-111">Агенты System Center Operations Manager, работающие в сети периметра (например, на пограничном сервере Skype для бизнеса Server), вне Организации (например, на внешнем виртуальном узле-наблюдателе транзакций) или на границе доверия Active Directory могут потребовать Конфигурация сервера шлюза System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="21efa-111">System Center Operations Manager agents running in a perimeter network (such as a Skype for Business Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory trust boundary, may require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="21efa-112">Эта роль сервера позволяет агентам, не имеющим отношения доверия с корневым сервером управления, создавать оповещения.</span><span class="sxs-lookup"><span data-stu-id="21efa-112">This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="21efa-113">Дополнительные сведения см. [в статье Управление серверами шлюза в Operations Manager 2012](https://technet.microsoft.com/library/hh212823.aspx).</span><span class="sxs-lookup"><span data-stu-id="21efa-113">For details, see [Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/library/hh212823.aspx).</span></span>

<span data-ttu-id="21efa-114">Если вы развертываете агент в одном из этих расположений, вам также потребуется запросить и настроить сертификат, который позволяет узлу-наблюдателю отправлять оповещения в System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="21efa-114">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="21efa-115">Чтобы упростить этот процесс, группа разработчиков Operations Manager создала набор вспомогательных программ, позволяющих запрашивать и устанавливать нужный тип сертификата на компьютера узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="21efa-115">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="21efa-116">Для получения дополнительных сведений и загрузки этих служебных программ ознакомьтесь [со статьей получение сертификатов для агентов, не присоединенных к домену, которые просты в работе с мастером создания сертификатов](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="21efa-116">For details, and to download these utilities, see [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span></span>

### <a name="installing-the-operation-manager-agent-files"></a><span data-ttu-id="21efa-117">Установка файлов агента Operation Manager</span><span class="sxs-lookup"><span data-stu-id="21efa-117">Installing the Operation Manager Agent Files</span></span>

1. <span data-ttu-id="21efa-118">На установочном носителе System Center дважды щелкните файл **Setup. exe**.</span><span class="sxs-lookup"><span data-stu-id="21efa-118">On your System Center setup media, double-click **Setup.exe**.</span></span>

2. <span data-ttu-id="21efa-119">В мастере установки System Center Operations Manager щелкните **установить агент Operations Manager**, от установки агента в разделе необязательные установки</span><span class="sxs-lookup"><span data-stu-id="21efa-119">In the System Center Operation Manager setup wizard, click **Install Operations Manager Agent**, from Install Agent under Optional Installations</span></span>

3. <span data-ttu-id="21efa-120">В мастере установки System Center на странице Добро пожаловать в мастер установки System Center Operations Manager нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="21efa-120">In the System Center setup wizard, on the Welcome to the System Center Operations Manager Setup wizard page, click **Next**.</span></span>

4. <span data-ttu-id="21efa-121">На странице Конечная папка выберите папку, в которую будут установлены файлы агента Operations Manager, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="21efa-121">On the Destination Folder page, select the folder where the Operations Manager Agent files will be installed and click **Next**.</span></span>

5. <span data-ttu-id="21efa-122">На странице "Конфигурация группы управления" выберите **указать сведения о группе управления** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="21efa-122">On the Management Group Configuration page, select **Specify Management Group information** and click **Next**.</span></span>

6. <span data-ttu-id="21efa-123">На странице Конфигурация группы управления в поле **Имя группы управления** введите имя группы управления Operations Manager, а в поле **Сервер управления** введите имя узла сервера Operations Manager (например, atl-scom-001).</span><span class="sxs-lookup"><span data-stu-id="21efa-123">On the Management Group Configuration page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="21efa-124">Если вы изменили номер порта, используемый Operations Manager, введите новый номер порта в поле **порт сервера управления** .</span><span class="sxs-lookup"><span data-stu-id="21efa-124">If you changed the port number used by Operations Manager, enter the new port number in the **Management Server Port** box.</span></span> <span data-ttu-id="21efa-125">В противном случае оставьте значение порта по умолчанию 5723 и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="21efa-125">Otherwise, leave the port at the default value of 5723, and then click **Next**.</span></span>

7. <span data-ttu-id="21efa-126">На странице Учетная запись действия агента выберите пункт **Локальная система** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="21efa-126">On the Agent Action Account page, select **Local System** and click **Next**.</span></span>

8. <span data-ttu-id="21efa-127">На странице центра обновления Майкрософт установите флажок **я не хочу использовать обновление Майкрософт** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="21efa-127">On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.</span></span>

9. <span data-ttu-id="21efa-128">На странице "Все готово для установки" нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="21efa-128">On the Ready to Install page, click **Install**.</span></span>

10. <span data-ttu-id="21efa-129">На странице Завершение работы мастера установки System Center Operations Manager нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="21efa-129">On the Completing the System Center Operations Manager Setup wizard page, click **Finish**.</span></span>

11. <span data-ttu-id="21efa-130">Щелкните **Exit**.</span><span class="sxs-lookup"><span data-stu-id="21efa-130">Click **Exit**.</span></span>

<span data-ttu-id="21efa-131">Для System Center 2012 можно проверить, был ли создан агент, нажав кнопку **Пуск**, выбрав **все программы**, затем **System Center Operations Manager 2012**и выбрав пункт **Operations 2012 Manager Shell**.</span><span class="sxs-lookup"><span data-stu-id="21efa-131">For System Center 2012, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2012**, and then clicking **Operations 2012 Manager Shell**.</span></span> <span data-ttu-id="21efa-132">В командной консоли Operations Manager введите следующую команду Windows PowerShell и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="21efa-132">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>
```PowerShell
Get-SCOMAgent
```

<span data-ttu-id="21efa-133">Появится список всех агентов Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="21efa-133">A list of all your Operations Manager agents will appear.</span></span>
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="21efa-134">Настройка компьютера Skype для бизнеса Server для участия в обнаружении System Center</span><span class="sxs-lookup"><span data-stu-id="21efa-134">Configuring the Skype for Business Server Computer to Participate in System Center Discovery</span></span>
<span data-ttu-id="21efa-135"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="21efa-135"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="21efa-136">Чтобы убедиться, что новый агент Skype для бизнеса Server участвует в процессе обнаружения для System Center Operations Manager, необходимо выполнить следующую процедуру на каждом компьютере, на котором установлена консоль System Center Operations Manager:</span><span class="sxs-lookup"><span data-stu-id="21efa-136">To make sure that your new Skype for Business Server agent participates in the discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1. <span data-ttu-id="21efa-137">На вкладке Администрирование выберите **Управляемые агентом**.</span><span class="sxs-lookup"><span data-stu-id="21efa-137">On the Administration tab, click **Agent Managed**.</span></span>

2. <span data-ttu-id="21efa-138">Нажмите **Мастер обнаружения** и завершите работу мастера для компьютера, который будет обнаружен.</span><span class="sxs-lookup"><span data-stu-id="21efa-138">Click on **Discovery Wizard** and complete the wizard for the computer to be discovered.</span></span>

3. <span data-ttu-id="21efa-139">Перезапустите службу агента работоспособности.</span><span class="sxs-lookup"><span data-stu-id="21efa-139">Reboot the Health Agent service.</span></span> <span data-ttu-id="21efa-140">При перезагрузке службы будет принудительно обнаружена новая машина.</span><span class="sxs-lookup"><span data-stu-id="21efa-140">Rebooting the service will force discovery of the new machine.</span></span> <span data-ttu-id="21efa-141">Если вы не перезагрузите службу, система System Center Operations Manager будет обнаруживать новый компьютер в течение 4 часов.</span><span class="sxs-lookup"><span data-stu-id="21efa-141">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.</span></span>

4. <span data-ttu-id="21efa-142">Убедитесь, что в журнале событий Operations Manager не было записано никаких событий об ошибках.</span><span class="sxs-lookup"><span data-stu-id="21efa-142">Verify that no error events were recorded in the Operations Manager event log.</span></span>

5. <span data-ttu-id="21efa-143">Компьютер, на котором успешно назначен агент, отображается в разделе "управляемый агентом список", а компьютер, на котором установлен агент вручную, отображается в разделе "ожидающее управление", щелкните имя компьютера и подтвердите его.</span><span class="sxs-lookup"><span data-stu-id="21efa-143">The computer where the agent is pushed successfully will be shown under "Agent Managed" list and the computer where agent was installed manually will be shown under "Pending Management", click on the computer name and approve.</span></span>

6. <span data-ttu-id="21efa-144">Щелкните правой кнопкой мыши имя компьютера и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="21efa-144">Right-click the name of the computer, and then click **Properties**.</span></span> <span data-ttu-id="21efa-145">В диалоговом окне Свойства на вкладке Безопасность выберите **Разрешить агенту работать как прокси и обнаруживать управляемые объекты на других компьютерах**, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="21efa-145">In the Properties dialog box, on the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>


