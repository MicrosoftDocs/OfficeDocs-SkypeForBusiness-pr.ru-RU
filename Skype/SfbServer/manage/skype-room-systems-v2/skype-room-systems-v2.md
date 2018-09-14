---
title: Общие сведения об управлении для систем комнаты Скайп версии 2
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
description: Общие сведения об управлении систем комнаты Скайп версии 2.
ms.openlocfilehash: d79c04c69e320f404c8ce245120e9b01bd8de1ca
ms.sourcegitcommit: b265545216ff36772d5dc2df381a9046bc71098e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/13/2018
ms.locfileid: "23965658"
---
# <a name="management-overview"></a><span data-ttu-id="fc8ad-103">Общие сведения об управлении</span><span class="sxs-lookup"><span data-stu-id="fc8ad-103">Management overview</span></span> 

<span data-ttu-id="fc8ad-104">Важно, что разработка и выполнение текущего обслуживания и операции, убедитесь, что ваше Скайп комнаты v2 системы, доступные для пользователей и доставлять удобные пользовательские взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Skype Room Systems v2 systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="fc8ad-105">Мониторинг</span><span class="sxs-lookup"><span data-stu-id="fc8ad-105">Monitoring</span></span> 

<span data-ttu-id="fc8ad-106">Мониторинг версии 2 Скайп комнаты системы состоит из двух основных действий:</span><span class="sxs-lookup"><span data-stu-id="fc8ad-106">Monitoring Skype Room Systems v2 systems consists of two key activities:</span></span>

-  <span data-ttu-id="fc8ad-107">Устройство, приложения и мониторинг периферийных устройств</span><span class="sxs-lookup"><span data-stu-id="fc8ad-107">Device, application, and peripheral device monitoring</span></span>

-  <span data-ttu-id="fc8ad-108">Качество и надежность monitoring (CQD)</span><span class="sxs-lookup"><span data-stu-id="fc8ad-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="skype-room-systems-v2-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="fc8ad-109">Устройства системы комнаты Скайп версии 2, приложения и мониторинг периферийных устройств</span><span class="sxs-lookup"><span data-stu-id="fc8ad-109">Skype Room Systems v2 device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="fc8ad-110">Чтобы убедиться, что пользователи могут использовать единицы версии 2 Скайп комнаты систем, единицы измерения должны находиться, подключения к сети с приложением версии 2 Скайп комнаты систем правильно настроен и подключенных к работает периферийных устройств.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-110">To ensure that users are able to use the Skype Room Systems v2 units, the units must be on, connected to the network with the Skype Room Systems v2 application correctly configured, and be connected to functioning peripheral devices.</span></span> 


<span data-ttu-id="fc8ad-111">Сведения о состоянии системы комнаты Скайп версии 2 приложения и подключенных внешних устройств записывается приложением версии 2 Скайп комнаты систем в журнал событий Windows и в [этой статье](oms.md#understand-the-log-entries).</span><span class="sxs-lookup"><span data-stu-id="fc8ad-111">Information about the state of the Skype Room Systems v2 application and connected peripheral devices is written by the Skype Room Systems v2 application to the Windows event log and documented [in this article](oms.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="fc8ad-112">**Параметр**</span><span class="sxs-lookup"><span data-stu-id="fc8ad-112">**Setting**</span></span>|<span data-ttu-id="fc8ad-113">**Позволяет**</span><span class="sxs-lookup"><span data-stu-id="fc8ad-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fc8ad-114">HKLM\SOFTWARE\Microsoft\Windows программы AutoAdminLogon = (dword) 1</span><span class="sxs-lookup"><span data-stu-id="fc8ad-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="fc8ad-115">Версии 2 систем комнаты Скайп позволяет загружать</span><span class="sxs-lookup"><span data-stu-id="fc8ad-115">Enables Skype Room Systems v2 to boot up</span></span>  <br/> |
|<span data-ttu-id="fc8ad-116">Power Management -\> от сети, отключить экран после 10 минут</span><span class="sxs-lookup"><span data-stu-id="fc8ad-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="fc8ad-117">Power Management -\> от сети, никогда не создавать системы в спящий режим</span><span class="sxs-lookup"><span data-stu-id="fc8ad-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="fc8ad-118">Позволяет v2 систем комнаты Скайп отключение вложенные отображает и спящего режима автоматически</span><span class="sxs-lookup"><span data-stu-id="fc8ad-118">Enables Skype Room Systems v2 to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="fc8ad-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="fc8ad-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="fc8ad-p101">Или аналогичное средство отключения срока действия пароля для локальной учетной записи. В противном случае учетной записи Skype через некоторое время не удастся выполнить вход и появится сообщение о том, что срок действия пароля истек. Имейте в виду, что это относится ко всем локальным учетным записям на компьютере. Поэтому, если не задать этот параметр, срок действия учетной записи администратора также через некоторое время истечет. </span><span class="sxs-lookup"><span data-stu-id="fc8ad-p101">Or equivalent means of disabling password expiration on the local account. Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password. Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="fc8ad-123">Позволяет учетной записи Skype всегда выполнять вход.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-123">Enables Skype account to always log in</span></span>  <br/> |
   
<span data-ttu-id="fc8ad-124">Передача файлов с помощью групповых политик рассматривается в статье [Настройка файла элемента](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="fc8ad-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/en-us/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="fc8ad-125">Удаленное управление с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc8ad-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="fc8ad-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="fc8ad-126"></span></span>


<span data-ttu-id="fc8ad-127">Мы рекомендуем использовать набора Microsoft Operations Manager для отслеживания вашей Скайп комнаты v2 системы.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Skype Room Systems v2 systems.</span></span> <span data-ttu-id="fc8ad-128">Инструкции по настройке мониторинга и основные предупреждения в разделе [Управление развертывание системы комнаты Скайп версии 2 с помощью OMS](../../deploy/deploy-clients/with-oms.md).</span><span class="sxs-lookup"><span data-stu-id="fc8ad-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Skype Room Systems v2 management with OMS](../../deploy/deploy-clients/with-oms.md).</span></span> 

<span data-ttu-id="fc8ad-129">Данное руководство можно создать простой в использовании панели мониторинга для выявления проблем с вашей версии 2 единицы Скайп комнаты систем в развертывании.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Skype Room Systems v2 units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../../media/audio_conferencing_image7.png) <br/><span data-ttu-id="fc8ad-130">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="fc8ad-130">Decision points</span></span>|<ul><li><span data-ttu-id="fc8ad-131">Убедитесь, что пакет управления Operations используется для отслеживания развертывания систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-131">Confirm that you'll use Operations Management Suite to monitor your Skype Room Systems v2 deployment.</span></span></li><li><span data-ttu-id="fc8ad-132">Выбор целевого списка рассылки, которые будут использоваться для оповещения по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../../media/audio_conferencing_image9.png)<br/><span data-ttu-id="fc8ad-133">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="fc8ad-133">Next steps</span></span>|<ul><li><span data-ttu-id="fc8ad-134">Определение качества и надежности, мониторинг подход.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="fc8ad-135">Качество и надежность monitoring (CQD)</span><span class="sxs-lookup"><span data-stu-id="fc8ad-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="fc8ad-136">Рекомендуется реализовать текущие эксплуатационные качества и надежности, мониторинг процедур, описанных в процессе развертывания для отслеживания прибора вызовов и качества собрания и надежности, идентифицирующий любой областей и работает над разрешением.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="fc8ad-137">При передаче сведений о построения CQD могут исследовать тенденции качество и надежность звонок на уровне каждого построения, который позволяет сравнить зданий и сосредоточиться на конкретные проблемы.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span> <span data-ttu-id="fc8ad-138">Для получения дополнительных сведений загрузите [Монитор CQD для Скайп для доставки Online бизнеса и руководство пользователя](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span><span class="sxs-lookup"><span data-stu-id="fc8ad-138">For more information, download the [Monitor-CQD for Skype for Business Online-Delivery and Operations Guide](https://myadvisor.fasttrack.microsoft.com/CloudVoice/Downloads?SelectedIDs=6_2_0_15).</span></span> 

<span data-ttu-id="fc8ad-139">Рекомендуется просмотреть и следуйте [Quality of просмотрите руководство по работе](https://aka.ms/qerguide) для определения качества и надежности тенденции и создания плана действий по их устранению.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-139">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-skype-room-systems-v2-os-and-skype-room-systems-application"></a><span data-ttu-id="fc8ad-140">Обновление приложения Скайп комнаты системы и операционная система систем комнаты Скайп версии 2</span><span class="sxs-lookup"><span data-stu-id="fc8ad-140">Updating the Skype Room Systems v2 OS and Skype Room Systems application</span></span> 

<span data-ttu-id="fc8ad-141">Мы рекомендуем, что обновлении систем комнаты Скайп версии 2 Скайп комнаты системы и операционной системы версии 2 приложения, чтобы использовать обновлений и улучшений.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-141">We recommend that you update the Skype Room Systems v2 OS and Skype Room Systems v2 application to benefit from product updates and improvements.</span></span> <span data-ttu-id="fc8ad-142">Подробные инструкции в разделе [Управление системами комнаты Скайп версии 2](room-systems-v2-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="fc8ad-142">For detailed guidance, see [Manage Skype Room Systems v2](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="troubleshooting"></a><span data-ttu-id="fc8ad-143">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="fc8ad-143">Troubleshooting</span></span>

<span data-ttu-id="fc8ad-144">Рекомендуется настроить пакет управления Operations предупреждения, как описано в предыдущем разделе, чтобы группы операций и служба технической поддержки получать уведомления о проблемам систем комнаты Скайп версии 2.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-144">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Skype Room Systems v2 issues.</span></span> <span data-ttu-id="fc8ad-145">Параметры, которые имеют для удаленного управления PowerShell, описаны в [удаленное управление с помощью PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="fc8ad-145">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="fc8ad-146">В случае, если периферийный устройству, может потребоваться зависеть от локального «смарт-руки» или поддержку для исследования и подключите устройство.</span><span class="sxs-lookup"><span data-stu-id="fc8ad-146">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="fc8ad-147">Дополнительные сведения о режиме администрирования и устранения неполадок можно [Управление системами комнаты Скайп версии 2](room-systems-v2-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="fc8ad-147">For more information about troubleshooting and admin mode, see [Manage Skype Room Systems v2](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 

## <a name="see-also"></a><span data-ttu-id="fc8ad-148">См. также</span><span class="sxs-lookup"><span data-stu-id="fc8ad-148">See also</span></span>

[<span data-ttu-id="fc8ad-149">Справка по версии 2 Скайп комнаты систем</span><span class="sxs-lookup"><span data-stu-id="fc8ad-149">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="fc8ad-150">Планирование для Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="fc8ad-150">Plan for Skype Room Systems v2</span></span>](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[<span data-ttu-id="fc8ad-151">Развертывание Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="fc8ad-151">Deploy Skype Room Systems v2</span></span>](../../deploy/deploy-clients/room-systems-v2.md)

[<span data-ttu-id="fc8ad-152">Настройка консоли для Систем комнат Skype версии 2</span><span class="sxs-lookup"><span data-stu-id="fc8ad-152">Configure a Skype Room Systems v2 console</span></span>](../../deploy/deploy-clients/console.md)

[<span data-ttu-id="fc8ad-153">Удаленное управление параметрами консоли Систем комнат Skype версии 2 с помощью XML-файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="fc8ad-153">Manage a Skype Room Systems v2 console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
