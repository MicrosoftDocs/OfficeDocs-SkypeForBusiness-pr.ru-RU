---
title: Настройка компьютеров Skype для бизнеса Server для мониторинга
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/7/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: 'Сводка: Установить файлы агента Operations Manager на Скайп для компьютера Business Server 2019 для мониторинга и настроить компьютер в качестве прокси-сервер System Center.'
ms.openlocfilehash: 3f2e17dcaa32a37f0ae7b5ef73cd6f351c9d4bc1
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "26536071"
---
# <a name="configure-the-skype-for-business-server-computers-that-will-be-monitored"></a><span data-ttu-id="80e77-103">Настройка компьютеров Skype для бизнеса Server для мониторинга</span><span class="sxs-lookup"><span data-stu-id="80e77-103">Configure the Skype for Business Server computers that will be monitored</span></span>

<span data-ttu-id="80e77-104">**Сводка:** Установить файлы агента Operations Manager на Скайп для компьютера Business Server 2019 для мониторинга и настроить компьютер в качестве прокси-сервер System Center.</span><span class="sxs-lookup"><span data-stu-id="80e77-104">**Summary:** Install the Operations Manager agent files on the Skype for Business Server 2019 computer to be monitored, and configure the computer to act as a System Center proxy.</span></span>

<span data-ttu-id="80e77-105">Каждый Скайп для компьютера Business Server 2019, которую необходимо отслеживать должны иметь возможность самостоятельно сообщить о его существования на сервере управления.</span><span class="sxs-lookup"><span data-stu-id="80e77-105">Each Skype for Business Server 2019 computer that you want to monitor must be able to self-report its existence to the management server.</span></span> <span data-ttu-id="80e77-106">Этот процесс возможен только после установки файлов агента Operations Manager на каждом из таких компьютеров.</span><span class="sxs-lookup"><span data-stu-id="80e77-106">To enable this process, you must install the Operations Manager agent files on each of the computers to be monitored.</span></span> <span data-ttu-id="80e77-107">После установки файлов агента необходимо настроить компьютер для работы в качестве прокси-сервера System Center.</span><span class="sxs-lookup"><span data-stu-id="80e77-107">After installing the agent files, you must configure the computer to act as a System Center proxy.</span></span> <span data-ttu-id="80e77-108">Убедитесь, что вы сначала установки и настройки Скайп для Business Server на следующих компьютерах перед выполнением этих процедур.</span><span class="sxs-lookup"><span data-stu-id="80e77-108">Be sure that you have first installed and configured Skype for Business Server on these computers before carrying out these procedures.</span></span>

## <a name="installing-a-certificate-on-a-watcher-node-located-outside-the-perimeter-network"></a><span data-ttu-id="80e77-109">Установка сертификата на узел-наблюдатель, расположенный вне сети периметра</span><span class="sxs-lookup"><span data-stu-id="80e77-109">Installing a Certificate on a Watcher Node Located Outside the Perimeter Network</span></span>
<span data-ttu-id="80e77-110"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="80e77-110"></span></span>

<span data-ttu-id="80e77-111">System Center Operations Manager агентов в демилитаризованной зоны сети (например, Скайп для пограничного сервера Business Server), за пределами организации (например, узел-наблюдатель внешних искусственная транзакция), или через доверия Active Directory может потребоваться границы Конфигурация шлюза системы центр Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="80e77-111">System Center Operations Manager agents running in a perimeter network (such as a Skype for Business Server Edge Server), outside of the enterprise (such as an external synthetic transaction watcher node), or across an Active Directory trust boundary, may require the configuration of a System Center Operations Manager Gateway Server.</span></span> <span data-ttu-id="80e77-112">This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts.</span><span class="sxs-lookup"><span data-stu-id="80e77-112">This server role enables agents that do not have a trust relationship with the Root Management Server to raise alerts.</span></span> <span data-ttu-id="80e77-113">For details, see [Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).</span><span class="sxs-lookup"><span data-stu-id="80e77-113">For details, see [Managing Gateway Servers in Operations Manager 2012](https://technet.microsoft.com/en-us/library/hh212823.aspx).</span></span>

<span data-ttu-id="80e77-114">Если развернуть агент в одном из этих расположений, также необходимо запрос и Настройка сертификата, который позволяет узла-наблюдателя для отправки оповещений для System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="80e77-114">If you deploy an agent in one of these locations, you will also need to request and configure a certificate that enables the watcher node to send alerts to System Center Operations Manager.</span></span> <span data-ttu-id="80e77-115">Чтобы упростить этот процесс, Operations Manager создала набор служебных программ, которые позволяют запросить и установить правильный тип сертификата на компьютере узла-наблюдателя.</span><span class="sxs-lookup"><span data-stu-id="80e77-115">To simplify this process, the Operations Manager team has created a set of utilities that enable you to request and install the correct type of certificate on the watcher node computer.</span></span> <span data-ttu-id="80e77-116">Дополнительные сведения и инструкции по загрузке этих служебных программ см. в разделе [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span><span class="sxs-lookup"><span data-stu-id="80e77-116">For details, and to download these utilities, see [Obtaining Certificates for Non-Domain Joined Agents Made Easy with Certificate Generation Wizard](https://go.microsoft.com/fwlink/p/?LinkID=267421&amp;amp;clcid=0x409).</span></span>

### <a name="installing-the-operation-manager-agent-files"></a><span data-ttu-id="80e77-117">Установка файлов агента Operation Manager</span><span class="sxs-lookup"><span data-stu-id="80e77-117">Installing the Operation Manager Agent Files</span></span>

1. <span data-ttu-id="80e77-118">В установочном носителе System Center дважды щелкните **SetupOM.exe**.</span><span class="sxs-lookup"><span data-stu-id="80e77-118">On your System Center setup media, double-click **Setup.exe**.</span></span>

2. <span data-ttu-id="80e77-119">В мастере установки System Center Operation Manager выберите **Установить агент Operations Manager**, из установить агент в разделе необязательные установок</span><span class="sxs-lookup"><span data-stu-id="80e77-119">In the System Center Operation Manager setup wizard, click **Install Operations Manager Agent**, from Install Agent under Optional Installations</span></span>

3. <span data-ttu-id="80e77-120">В мастере установки System Center на начальной странице мастера установки System Center Operations Manager нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="80e77-120">In the System Center setup wizard, on the Welcome to the System Center Operations Manager Setup wizard page, click **Next**.</span></span>

4. <span data-ttu-id="80e77-121">На странице папка назначения выберите папку, где должны устанавливаться файлы агента Operations Manager и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="80e77-121">On the Destination Folder page, select the folder where the Operations Manager Agent files will be installed and click **Next**.</span></span>

5. <span data-ttu-id="80e77-122">На странице "Конфигурация группы управления" выберите **Указать сведения о группе управления** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="80e77-122">On the Management Group Configuration page, select **Specify Management Group information** and click **Next**.</span></span>

6. <span data-ttu-id="80e77-123">На странице Конфигурация группы управления введите имя своей группы управления Operations Manager в поле **Имя группы управления** , а затем введите имя узла сервера Operations Manager (например, atl-scom-001) в \*\*Management Server \*\*поле.</span><span class="sxs-lookup"><span data-stu-id="80e77-123">On the Management Group Configuration page, type the name of your Operations Manager Management Group in the **Management Group Name** box, and then type the host name of your Operations Manager server (for example, atl-scom-001) in the **Management Server** box.</span></span> <span data-ttu-id="80e77-124">Если номер порта, используемый программой Operations Manager, изменен, введите новый номер порта в поле **Порт сервера управления**.</span><span class="sxs-lookup"><span data-stu-id="80e77-124">If you changed the port number used by Operations Manager, enter the new port number in the **Management Server Port** box.</span></span> <span data-ttu-id="80e77-125">В противном случае оставьте для порта значение по умолчанию 5723, затем нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="80e77-125">Otherwise, leave the port at the default value of 5723, and then click **Next**.</span></span>

7. <span data-ttu-id="80e77-126">На странице "Учетная запись действий агента" выберите **Локальная система** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="80e77-126">On the Agent Action Account page, select **Local System** and click **Next**.</span></span>

8. <span data-ttu-id="80e77-127">On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.</span><span class="sxs-lookup"><span data-stu-id="80e77-127">On the Microsoft Update page, select **I don't want to use Microsoft Update** and click **Next**.</span></span>

9. <span data-ttu-id="80e77-128">На странице "Все готово для установки" нажмите кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="80e77-128">On the Ready to Install page, click **Install**.</span></span>

10. <span data-ttu-id="80e77-129">На странице завершения работы мастера установки System Center Operations Manager нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="80e77-129">On the Completing the System Center Operations Manager Setup wizard page, click **Finish**.</span></span>

11. <span data-ttu-id="80e77-130">Нажмите кнопку **Выход**.</span><span class="sxs-lookup"><span data-stu-id="80e77-130">Click **Exit**.</span></span>

<span data-ttu-id="80e77-131">Для System Center 2012 вы можете проверить, что агент была создана, и нажмите кнопку **Пуск**, **Все программы**, **System Center Operations Manager 2012**и **Оболочка Operations Manager 2012 г.**</span><span class="sxs-lookup"><span data-stu-id="80e77-131">For System Center 2012, you can verify that the agent has been created by clicking **Start**, clicking **All Programs**, clicking **System Center Operations Manager 2012**, and then clicking **Operations 2012 Manager Shell**.</span></span> <span data-ttu-id="80e77-132">В оболочке Operations Manager введите следующую команду Windows PowerShell, затем нажмите клавишу Enter:</span><span class="sxs-lookup"><span data-stu-id="80e77-132">In the Operations Manager Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>
```
Get-SCOMAgent
```

<span data-ttu-id="80e77-133">Отображается список всех агентов Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="80e77-133">A list of all your Operations Manager agents will appear.</span></span>
## <a name="configuring-the-skype-for-business-server-computer-to-participate-in-system-center-discovery"></a><span data-ttu-id="80e77-134">Настройка компьютера Skype для бизнеса Server для участия в обнаружении System Center</span><span class="sxs-lookup"><span data-stu-id="80e77-134">Configuring the Skype for Business Server Computer to Participate in System Center Discovery</span></span>
<span data-ttu-id="80e77-135"><a name="watcher_node_outside"> </a></span><span class="sxs-lookup"><span data-stu-id="80e77-135"></span></span>

<span data-ttu-id="80e77-136">Чтобы убедиться в том, что ваш новый Скайп для агента Business Server участвует в процессе обнаружения для System Center Operations Manager, необходимо выполнить следующую процедуру на каждом компьютере, где была установлена консоль System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="80e77-136">To make sure that your new Skype for Business Server agent participates in the discovery process for System Center Operations Manager, you must complete the following procedure on each computer where the System Center Operations Manager console has been installed:</span></span>

1. <span data-ttu-id="80e77-137">На вкладке "Администрирование" щелкните **Управляемые агентом**.</span><span class="sxs-lookup"><span data-stu-id="80e77-137">On the Administration tab, click **Agent Managed**.</span></span>

2. <span data-ttu-id="80e77-138">Щелкните **мастер обнаружения** обнаружьте компьютер с помощью мастера.</span><span class="sxs-lookup"><span data-stu-id="80e77-138">Click on **Discovery Wizard** and complete the wizard for the computer to be discovered.</span></span>

3. <span data-ttu-id="80e77-139">Перезапустите службу агента работоспособности.</span><span class="sxs-lookup"><span data-stu-id="80e77-139">Reboot the Health Agent service.</span></span> <span data-ttu-id="80e77-140">При перезапуске службы принудительно выполняется обнаружение нового компьютера.</span><span class="sxs-lookup"><span data-stu-id="80e77-140">Rebooting the service will force discovery of the new machine.</span></span> <span data-ttu-id="80e77-141">Если вы не перезагрузите службу, может получить до 4 часов до обнаружения новый компьютер с System Center Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="80e77-141">If you do not reboot the service, it could take as long as 4 hours before the new machine is discovered by System Center Operations Manager.</span></span>

4. <span data-ttu-id="80e77-142">Проверьте отсутствие записей об ошибках в журнале событий Operations Manager.</span><span class="sxs-lookup"><span data-stu-id="80e77-142">Verify that no error events were recorded in the Operations Manager event log.</span></span>

5. <span data-ttu-id="80e77-143">Компьютер, где агент помещается успешно будут отображаться в списке «Управляемые агента» и компьютер, где была установлена агента вручную будут отображаться в разделе «Управление ожидающие», щелкните имя компьютера и утверждение.</span><span class="sxs-lookup"><span data-stu-id="80e77-143">The computer where the agent is pushed successfully will be shown under "Agent Managed" list and the computer where agent was installed manually will be shown under "Pending Management", click on the computer name and approve.</span></span>

6. <span data-ttu-id="80e77-p107">	Right-click the name of the computer, and then click *\*Properties*\*. In the Properties dialog box, on the Security tab, select *\*Allow this agent to act as a proxy and discover managed objects on other computers*\*, and then click *\*OK*\*.</span><span class="sxs-lookup"><span data-stu-id="80e77-p107">Right-click the name of the computer, and then click **Properties**. In the Properties dialog box, on the Security tab, select **Allow this agent to act as a proxy and discover managed objects on other computers**, and then click **OK**.</span></span>


