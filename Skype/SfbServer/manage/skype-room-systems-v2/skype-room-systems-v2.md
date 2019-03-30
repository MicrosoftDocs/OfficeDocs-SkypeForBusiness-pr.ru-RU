---
title: Общие сведения об управлении для комнат группами Майкрософт
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 5/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection: M365-voice
description: Общие сведения об управлении группами комнат Microsoft.
ms.openlocfilehash: a06ffc6bb0aa69b493c95a516946c322034913f8
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012495"
---
# <a name="management-overview"></a><span data-ttu-id="c5b45-103">Обзор управления</span><span class="sxs-lookup"><span data-stu-id="c5b45-103">Management overview</span></span> 

<span data-ttu-id="c5b45-104">Важно, что разработка и выполнение текущего обслуживания и операции, убедитесь, что системы комнат группами Майкрософт, доступны для пользователей и доставлять удобные пользовательские взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="c5b45-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="c5b45-105">Мониторинг</span><span class="sxs-lookup"><span data-stu-id="c5b45-105">Monitoring</span></span> 

<span data-ttu-id="c5b45-106">Мониторинг систем Microsoft группами комнат состоит из двух ключевые действия:</span><span class="sxs-lookup"><span data-stu-id="c5b45-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

-  <span data-ttu-id="c5b45-107">Устройство, приложения и мониторинг периферийных устройств</span><span class="sxs-lookup"><span data-stu-id="c5b45-107">Device, application, and peripheral device monitoring</span></span>

-  <span data-ttu-id="c5b45-108">Качество и надежность monitoring (CQD)</span><span class="sxs-lookup"><span data-stu-id="c5b45-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="c5b45-109">Устройство комнат группами Майкрософт, приложения и мониторинг периферийных устройств</span><span class="sxs-lookup"><span data-stu-id="c5b45-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="c5b45-110">Чтобы убедиться, что пользователи могут использовать единицы комнат группами Майкрософт, единицы измерения должны находиться, подключения к сети с приложением Microsoft группами комнат правильно настроен и подключенных к работает периферийных устройств.</span><span class="sxs-lookup"><span data-stu-id="c5b45-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 


<span data-ttu-id="c5b45-111">Сведения о состоянии приложения Microsoft группами комнат и подключенных внешних устройств созданным приложения комнат группами Майкрософт в журнал событий Windows и описаны в [понять записей журнала](azure-monitor.md#understand-the-log-entries).</span><span class="sxs-lookup"><span data-stu-id="c5b45-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="c5b45-112">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="c5b45-112">**Setting**</span></span>|<span data-ttu-id="c5b45-113">**Позволяет**</span><span class="sxs-lookup"><span data-stu-id="c5b45-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c5b45-114">HKLM\SOFTWARE\Microsoft\Windows программы AutoAdminLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="c5b45-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="c5b45-115">Позволяет комнат группами Майкрософт загружать</span><span class="sxs-lookup"><span data-stu-id="c5b45-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="c5b45-116">Power Management -\> от сети, отключить экран после 10 минут</span><span class="sxs-lookup"><span data-stu-id="c5b45-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="c5b45-117">Power Management -\> от сети, никогда не создавать системы в спящий режим</span><span class="sxs-lookup"><span data-stu-id="c5b45-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="c5b45-118">Позволяет комнат группами Майкрософт отключение вложенные отображает и спящего режима автоматически</span><span class="sxs-lookup"><span data-stu-id="c5b45-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="c5b45-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="c5b45-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="c5b45-120">Или эквивалентный означает, что отключения истечение срока действия пароля на локальной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="c5b45-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="c5b45-121">Для этого в конце концов вызывает учетной записи Скайп Сбой входа жалуется пароль с истекшим сроком действия.</span><span class="sxs-lookup"><span data-stu-id="c5b45-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="c5b45-122">Обратите внимание на то, что это влияет на всех локальных учетных записей на компьютере, и таким образом не удалось установить это также будет происходить учетную запись администратора на поле в конечном счете срок действия которых истекает также.</span><span class="sxs-lookup"><span data-stu-id="c5b45-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="c5b45-123">Позволяет учетной записи Skype всегда выполнять вход.</span><span class="sxs-lookup"><span data-stu-id="c5b45-123">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="c5b45-124">Передача файлов с помощью групповых политик рассматривается в статье [Настройка файла элемента](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c5b45-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="c5b45-125">Удаленное управление с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c5b45-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="c5b45-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="c5b45-126"></span></span>

<span data-ttu-id="c5b45-127">Мы рекомендуем использовать набора Microsoft Operations Manager для мониторинга системы комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c5b45-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="c5b45-128">Инструкции по настройке мониторинга и основные предупреждения в разделе [Управление развертывание комнат группы Microsoft Azure монитор](../../deploy/deploy-clients/azure-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="c5b45-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](../../deploy/deploy-clients/azure-monitor.md).</span></span> 

<span data-ttu-id="c5b45-129">Данное руководство можно создать простой в использовании панели мониторинга для выявления проблем с единиц комнат группами Майкрософт в развертывании.</span><span class="sxs-lookup"><span data-stu-id="c5b45-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/><span data-ttu-id="c5b45-130">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="c5b45-130">Decision points</span></span>|<ul><li><span data-ttu-id="c5b45-131">Убедитесь, что пакет управления Operations используется для наблюдения за развертывание комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c5b45-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="c5b45-132">Выбор целевого списка рассылки, которые будут использоваться для оповещения по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="c5b45-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/><span data-ttu-id="c5b45-133">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="c5b45-133">Next steps</span></span>|<ul><li><span data-ttu-id="c5b45-134">Определение качества и надежности, мониторинг подход.</span><span class="sxs-lookup"><span data-stu-id="c5b45-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="c5b45-135">Качество и надежность monitoring (CQD)</span><span class="sxs-lookup"><span data-stu-id="c5b45-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="c5b45-136">Рекомендуется реализовать текущие эксплуатационные качества и надежности, мониторинг процедур, описанных в процессе развертывания для отслеживания прибора вызовов и качества собрания и надежности, идентифицирующий любой областей и работает над разрешением.</span><span class="sxs-lookup"><span data-stu-id="c5b45-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="c5b45-137">При передаче сведений о построения CQD могут исследовать тенденции качество и надежность звонок на уровне каждого построения, который позволяет сравнить зданий и сосредоточиться на конкретные проблемы.</span><span class="sxs-lookup"><span data-stu-id="c5b45-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span> <span data-ttu-id="c5b45-138">Для получения дополнительных сведений загрузите [Монитор CQD для Скайп для доставки Online бизнеса и руководство пользователя](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span><span class="sxs-lookup"><span data-stu-id="c5b45-138">For more information, download the [Monitor-CQD for Skype for Business Online-Delivery and Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span></span> 

<span data-ttu-id="c5b45-139">Рекомендуется просмотреть и следуйте [Quality of просмотрите руководство по работе](https://aka.ms/qerguide) для определения качества и надежности тенденции и создания плана действий по их устранению.</span><span class="sxs-lookup"><span data-stu-id="c5b45-139">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="c5b45-140">Обновление приложения операционная система Microsoft группами комнат и комнаты группы Microsoft</span><span class="sxs-lookup"><span data-stu-id="c5b45-140">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="c5b45-141">Рекомендуется обновить приложение операционная система комнат группы Microsoft и комнат группами Майкрософт, чтобы использовать обновлений и улучшений.</span><span class="sxs-lookup"><span data-stu-id="c5b45-141">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="c5b45-142">Подробные инструкции в разделе [Управление группами комнат Microsoft](room-systems-v2-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="c5b45-142">For detailed guidance, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="c5b45-143">Обновления Windows</span><span class="sxs-lookup"><span data-stu-id="c5b45-143">Windows Updates</span></span>

<span data-ttu-id="c5b45-144">Комнат группами Майкрософт запускается на Windows 10 Enterprise IoT или Windows 10 Enterprise Корпоративная лицензия и получает же обновления Windows и операционная система построения как стандартный рабочий стол.</span><span class="sxs-lookup"><span data-stu-id="c5b45-144">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="c5b45-145">В статье [Управление обновления Windows](updates.md) для получения дополнительных сведений.</span><span class="sxs-lookup"><span data-stu-id="c5b45-145">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="c5b45-146">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="c5b45-146">Troubleshooting</span></span>

<span data-ttu-id="c5b45-147">Рекомендуется настроить пакет управления Operations предупреждения, как описано в предыдущем разделе, чтобы группы операций и служба технической поддержки получать уведомления о проблемам комнат группами Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c5b45-147">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="c5b45-148">Параметры, которые имеют для удаленного управления PowerShell, описаны в [удаленное управление с помощью PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="c5b45-148">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="c5b45-149">В случае, если периферийный устройству, может потребоваться зависеть от локального «смарт-руки» или поддержку для исследования и подключите устройство.</span><span class="sxs-lookup"><span data-stu-id="c5b45-149">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="c5b45-150">Дополнительные сведения о режиме администрирования и устранения неполадок можно [Управлять группами комнат Microsoft](room-systems-v2-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="c5b45-150">For more information about troubleshooting and admin mode, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="c5b45-151">См. также</span><span class="sxs-lookup"><span data-stu-id="c5b45-151">See also</span></span>

[<span data-ttu-id="c5b45-152">Справка по Microsoft группами комнат</span><span class="sxs-lookup"><span data-stu-id="c5b45-152">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="c5b45-153">Планирование для групп Майкрософт комнат</span><span class="sxs-lookup"><span data-stu-id="c5b45-153">Plan for Microsoft Teams Rooms</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="c5b45-154">Развертывание групп Майкрософт комнат</span><span class="sxs-lookup"><span data-stu-id="c5b45-154">Deploy Microsoft Teams Rooms</span></span>](../../deploy/deploy-clients/room-systems-v2.md)

[<span data-ttu-id="c5b45-155">Настройка консоли комнат группами Майкрософт</span><span class="sxs-lookup"><span data-stu-id="c5b45-155">Configure a Microsoft Teams Rooms console</span></span>](../../deploy/deploy-clients/console.md)

[<span data-ttu-id="c5b45-156">Удаленное управление параметры консоли комнат группами Майкрософт с помощью XML-файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="c5b45-156">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
