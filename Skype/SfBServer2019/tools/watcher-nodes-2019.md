---
title: Настройка компьютеров Skype для бизнеса Server для мониторинга
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/7/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Сводка: Установите на компьютере с операционной системой Skype для Business Server 2019 файлы агента Operations Manager и настройте компьютер так, чтобы он действовал как прокси System Center.'
ms.openlocfilehash: 162b2dc0b50b7da5246d69d64b0bdb307212c139
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799649"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a><span data-ttu-id="da5a3-103">Настройка компьютеров Skype для бизнеса Server для мониторинга</span><span class="sxs-lookup"><span data-stu-id="da5a3-103">Configure the Skype for Business Server computers that will be monitored</span></span>

<span data-ttu-id="da5a3-104">**Сводка:** Установите файлы агента Operations Manager на компьютере Skype для бизнеса Server 2019 и настройте компьютер так, чтобы он действовал как прокси System Center.</span><span class="sxs-lookup"><span data-stu-id="da5a3-104">**Summary:** Install the Operations Manager agent files on the Skype for Business Server 2019 computer to be monitored, and configure the computer to act as a System Center proxy.</span></span>

<span data-ttu-id="da5a3-105">Каждый сервер Skype для бизнеса Server 2019, на котором вы хотите наблюдать, должен иметь возможность самостоятельного отчета о существовании сервера управления.</span><span class="sxs-lookup"><span data-stu-id="da5a3-105">Each Skype for Business Server 2019 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="da5a3-106">Этот процесс возможен только после установки файлов агента Operations Manager на каждом из таких компьютеров.</span><span class="sxs-lookup"><span data-stu-id="da5a3-106">To enable this process, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="da5a3-107">После установки файлов агента необходимо настроить компьютер для работы в качестве прокси-сервера System Center.</span><span class="sxs-lookup"><span data-stu-id="da5a3-107">After installing the agent files, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="da5a3-108">Перед выполнением этих процедур убедитесь, что вы установили и настроили сервер Skype для бизнеса на этих компьютерах.</span><span class="sxs-lookup"><span data-stu-id="da5a3-108">Be sure that you have first installed and configured Skype for Business Server on these computers before carrying out these procedures.</span></span>

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a><span data-ttu-id="da5a3-109">Установка сертификата на узел-наблюдатель, расположенный вне сети периметра</span><span class="sxs-lookup"><span data-stu-id="da5a3-109">Installing a Certificate on a Watcher Node Located Outside the Perimeter Network</span></span>
<span data-ttu-id="da5a3-110"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="da5a3-110"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="da5a3-111">Агенты System Center Operations Manager, работающие в демилитаризованной зоне (например, на пограничном сервере Skype для бизнеса Server), вне Организации (например, на внешнем виртуальном узле наблюдения за транзакциями) или на границе доверия Active Directory, могут потребовать Конфигурация сервера шлюза System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="da5a3-111">System Center Operations Manager agents running in a perimeter network (such as a Skype for Business Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory trust boundary, may require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="da5a3-112">This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts.</span><span class="sxs-lookup"><span data-stu-id="da5a3-112">This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="da5a3-113">Подробные сведения можно найти [в разделе Управление серверами шлюзов в Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).</span><span class="sxs-lookup"><span data-stu-id="da5a3-113">For details, see [Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).</span></span>

<span data-ttu-id="da5a3-114">Если вы развертываете агент в одном из этих местоположений, вам также потребуется запросить и настроить сертификат, который позволит узлу-наблюдателю отправлять оповещения в System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="da5a3-114">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="da5a3-115">Для упрощения этого процесса группа Operations Manager создала набор служебных программ, которые позволят вам запросить и установить правильный тип сертификата на компьютере с узлом-наблюдателем.</span><span class="sxs-lookup"><span data-stu-id="da5a3-115">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="da5a3-116">Сведения о том, как скачать эти служебные программы, можно найти в разделе [Получение сертификатов для агентов, не присоединенных к домену, которые упрощают работу с мастером создания сертификатов](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="da5a3-116">For details, and to download these utilities, see [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span></span>

### <a name="installing-the-operation-manager-agent-files"></a><span data-ttu-id="da5a3-117">Установка файлов агента Operation Manager</span><span class="sxs-lookup"><span data-stu-id="da5a3-117">Installing the Operation Manager Agent Files</span></span>

1. <span data-ttu-id="da5a3-118">В установочном носителе System Center дважды щелкните **SetupOM.exe**.</span><span class="sxs-lookup"><span data-stu-id="da5a3-118">On your System Center setup media, double-click **Setup.exe**.</span></span>

2. <span data-ttu-id="da5a3-119">В мастере настройки System Center Operations Manager выберите команду **установить агент Operations Manager**, из установки агента в разделе необязательные установки</span><span class="sxs-lookup"><span data-stu-id="da5a3-119">In the System Center Operation Manager setup wizard, click **Install Operations Manager Agent**, from Install Agent under Optional Installations</span></span>

3. <span data-ttu-id="da5a3-120">В мастере настройки System Center на странице Добро пожаловать на страницу мастера установки System Center Operations Manager нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da5a3-120">In the System Center setup wizard, on the Welcome to the System Center Operations Manager Setup wizard page, click **Next**.</span></span>

4. <span data-ttu-id="da5a3-121">На странице Конечная папка выберите папку, в которую будут установлены файлы агента Operations Manager, и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da5a3-121">On the Destination Folder page, select the folder where the Operations Manager Agent files will be installed and click **Next**.</span></span>

5. <span data-ttu-id="da5a3-122">На странице "Конфигурация группы управления" выберите **Указать сведения о группе управления** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da5a3-122">On the Management Group Configuration page, select **Specify Management Group information** and click **Next**.</span></span>

6. <span data-ttu-id="da5a3-123">На странице Конфигурация группы управления введите имя группы управления Operations Manager в поле **имя группы управления** , а затем введите имя узла сервера Operations Manager (например, ATL-SCOM-001) в поле **сервер управления** .</span><span class="sxs-lookup"><span data-stu-id="da5a3-123">On the Management Group Configuration page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="da5a3-124">Если номер порта, используемый программой Operations Manager, изменен, введите новый номер порта в поле **Порт сервера управления**.</span><span class="sxs-lookup"><span data-stu-id="da5a3-124">If you changed the port number used by Operations Manager, enter the new port number in the **Management Server Port** box.</span></span> <span data-ttu-id="da5a3-125">В противном случае оставьте для порта значение по умолчанию 5723, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da5a3-125">Otherwise, leave the port at the default value of 5723, and then click **Next**.</span></span>

7. <span data-ttu-id="da5a3-126">На странице "Учетная запись действий агента" выберите **Локальная система** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="da5a3-126">On the Agent Action Account page, select **Local System** and click **Next**.</span></span>

8. <span data-ttu-id="da5a3-127">On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.</span><span class="sxs-lookup"><span data-stu-id="da5a3-127">On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.</span></span>

9. <span data-ttu-id="da5a3-128">На странице "Все готово для установки" нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="da5a3-128">On the Ready to Install page, click **Install**.</span></span>

10. <span data-ttu-id="da5a3-129">На странице Завершение работы мастера установки System Center Operations Manager нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="da5a3-129">On the Completing the System Center Operations Manager Setup wizard page, click **Finish**.</span></span>

11. <span data-ttu-id="da5a3-130">Нажмите кнопку **Выход**.</span><span class="sxs-lookup"><span data-stu-id="da5a3-130">Click **Exit**.</span></span>

<span data-ttu-id="da5a3-131">Чтобы проверить, создан ли агент System Center 2012, нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **System Center Operations Manager 2012**, а затем — команду **Operations 2012 Manager Shell**.</span><span class="sxs-lookup"><span data-stu-id="da5a3-131">For System Center 2012, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2012**, and then clicking **Operations 2012 Manager Shell**.</span></span> <span data-ttu-id="da5a3-132">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span><span class="sxs-lookup"><span data-stu-id="da5a3-132">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>
```PowerShell
Get-SCOMAgent
```

<span data-ttu-id="da5a3-133">Отображается список всех агентов Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="da5a3-133">A list of all your Operations Manager agents will appear.</span></span>
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="da5a3-134">Настройка компьютера Skype для бизнеса Server для участия в обнаружении System Center</span><span class="sxs-lookup"><span data-stu-id="da5a3-134">Configuring the Skype for Business Server Computer to Participate in System Center Discovery</span></span>
<span data-ttu-id="da5a3-135"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="da5a3-135"><a name="watcher_node_outside"> </a></span></span>

<span data-ttu-id="da5a3-136">Чтобы убедиться в том, что новый агент сервера Skype для бизнеса входит в процесс обнаружения для System Center Operations Manager, необходимо выполнить описанные ниже действия для каждого компьютера, на котором установлена консоль System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="da5a3-136">To make sure that your new Skype for Business Server agent participates in the discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1. <span data-ttu-id="da5a3-137">На вкладке "Администрирование" щелкните **Управляемые агентом**.</span><span class="sxs-lookup"><span data-stu-id="da5a3-137">On the Administration tab, click **Agent Managed**.</span></span>

2. <span data-ttu-id="da5a3-138">Щелкните **мастер обнаружения** обнаружьте компьютер с помощью мастера.</span><span class="sxs-lookup"><span data-stu-id="da5a3-138">Click on **Discovery Wizard** and complete the wizard for the computer to be discovered.</span></span>

3. <span data-ttu-id="da5a3-139">Перезапустите службу агента работоспособности.</span><span class="sxs-lookup"><span data-stu-id="da5a3-139">Reboot the Health Agent service.</span></span> <span data-ttu-id="da5a3-140">При перезапуске службы принудительно выполняется обнаружение нового компьютера.</span><span class="sxs-lookup"><span data-stu-id="da5a3-140">Rebooting the service will force discovery of the new machine.</span></span> <span data-ttu-id="da5a3-141">Если вы не перезагрузите службу, система System Center Operations Manager может занять до 4 часов, пока новый компьютер не будет найден.</span><span class="sxs-lookup"><span data-stu-id="da5a3-141">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.</span></span>

4. <span data-ttu-id="da5a3-142">Проверьте отсутствие записей об ошибках в журнале событий Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="da5a3-142">Verify that no error events were recorded in the Operations Manager event log.</span></span>

5. <span data-ttu-id="da5a3-143">Компьютер, на котором агент отправляется успешно, отображается в разделе "управляемый агентом список", а на компьютере, на котором установлен агент вручную, в разделе "ожидание управления" щелкните имя компьютера и подтвердите его.</span><span class="sxs-lookup"><span data-stu-id="da5a3-143">The computer where the agent is pushed successfully will be shown under "Agent Managed" list and the computer where agent was installed manually will be shown under "Pending Management", click on the computer name and approve.</span></span>

6. <span data-ttu-id="da5a3-p107">	Right-click the name of the computer, and then click *\*Properties*\*. In the Properties dialog box, on the Security tab, select *\*Allow this agent to act as a proxy and discover managed objects on other computers*\*, and then click *\*OK*\*.</span><span class="sxs-lookup"><span data-stu-id="da5a3-p107">Right-click the name of the computer, and then click **Properties**. In the Properties dialog box, on the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>


