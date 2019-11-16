---
title: Общие сведения об управлении комнатами Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
ms.date: 5/10/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
description: Общие сведения об управлении комнатами Microsoft Teams.
ms.openlocfilehash: cff0b300dc6cc9f3c15e21163554571d49e6540c
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "38675817"
---
# <a name="management-overview"></a><span data-ttu-id="4fd08-103">Обзор управления</span><span class="sxs-lookup"><span data-stu-id="4fd08-103">Management overview</span></span>

<span data-ttu-id="4fd08-104">Важно, чтобы вы разработали и выполняли текущее обслуживание и операции, чтобы убедиться в том, что системы комнат Microsoft Teams доступны для ваших пользователей, и обеспечьте удобное взаимодействие с пользователями.</span><span class="sxs-lookup"><span data-stu-id="4fd08-104">It’s essential that you develop and execute ongoing maintenance and operations to ensure that your Microsoft Teams Rooms systems are available for your users and deliver a great user experience.</span></span> 

## <a name="monitoring"></a><span data-ttu-id="4fd08-105">Мониторинг</span><span class="sxs-lookup"><span data-stu-id="4fd08-105">Monitoring</span></span> 

<span data-ttu-id="4fd08-106">Наблюдение за системами комнат Microsoft Teams состоит из двух ключевых действий:</span><span class="sxs-lookup"><span data-stu-id="4fd08-106">Monitoring Microsoft Teams Rooms systems consists of two key activities:</span></span>

- <span data-ttu-id="4fd08-107">Мониторинг устройства, приложения и периферийных устройств</span><span class="sxs-lookup"><span data-stu-id="4fd08-107">Device, application, and peripheral device monitoring</span></span>
- <span data-ttu-id="4fd08-108">Мониторинг качества и надежности (CQD)</span><span class="sxs-lookup"><span data-stu-id="4fd08-108">Quality and reliability monitoring (CQD)</span></span>

### <a name="microsoft-teams-rooms-device-application-and-peripheral-device-monitoring"></a><span data-ttu-id="4fd08-109">Microsoft Teams — комнаты, мониторинг устройства, приложения и периферийных устройств</span><span class="sxs-lookup"><span data-stu-id="4fd08-109">Microsoft Teams Rooms device, application, and peripheral device monitoring</span></span>

<span data-ttu-id="4fd08-110">Чтобы убедиться в том, что пользователи смогут использовать единицы комнат Microsoft Teams, они должны быть включены, подключены к сети с помощью приложения Microsoft Teams и быть подключены к работающим периферийным устройствам.</span><span class="sxs-lookup"><span data-stu-id="4fd08-110">To ensure that users are able to use the Microsoft Teams Rooms units, the units must be on, connected to the network with the Microsoft Teams Rooms application correctly configured, and be connected to functioning peripheral devices.</span></span> 

<span data-ttu-id="4fd08-111">Сведения о состоянии приложения Microsoft Teams комнаты, а также подключенных периферийных устройств записываются в журнал событий Windows с помощью приложения комнаты Microsoft Teams и задокументированы в разделе [Знакомство с записями в журнале](azure-monitor-manage.md#understand-the-log-entries).</span><span class="sxs-lookup"><span data-stu-id="4fd08-111">Information about the state of the Microsoft Teams Rooms application and connected peripheral devices is written by the Microsoft Teams Rooms application to the Windows event log and documented in [Understand the log entries](azure-monitor-manage.md#understand-the-log-entries).</span></span> 

|<span data-ttu-id="4fd08-112">**Параметрами**</span><span class="sxs-lookup"><span data-stu-id="4fd08-112">**Setting**</span></span>|<span data-ttu-id="4fd08-113">**Можете**</span><span class="sxs-lookup"><span data-stu-id="4fd08-113">**Allows**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4fd08-114">HKLM\SOFTWARE\Microsoft\Windows Нт\куррентверсион\винлогон Аутоадминлогон = (DWORD) 1</span><span class="sxs-lookup"><span data-stu-id="4fd08-114">HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon AutoAdminLogon = (dword) 1</span></span>  <br/> |<span data-ttu-id="4fd08-115">Включает комнаты Microsoft Teams для загрузки</span><span class="sxs-lookup"><span data-stu-id="4fd08-115">Enables Microsoft Teams Rooms to boot up</span></span>  <br/> |
|<span data-ttu-id="4fd08-116">Управление питанием\> в сети переменного тока, отключение экрана через 10 минут</span><span class="sxs-lookup"><span data-stu-id="4fd08-116">Power Management -\> On AC, turn screen off after 10 minutes</span></span>  <br/> <span data-ttu-id="4fd08-117">Управление питанием\> — вкл., не переводит систему в спящий режим</span><span class="sxs-lookup"><span data-stu-id="4fd08-117">Power Management -\> On AC, never put system to sleep</span></span>  <br/> |<span data-ttu-id="4fd08-118">Позволяет комнатам Microsoft Teams отключить подключенные дисплеи и автоматически выключаться из спящего режима</span><span class="sxs-lookup"><span data-stu-id="4fd08-118">Enables Microsoft Teams Rooms to turn off attached displays and wake up automatically</span></span>  <br/> |
|<span data-ttu-id="4fd08-119">net accounts /maxpwage:unlimited</span><span class="sxs-lookup"><span data-stu-id="4fd08-119">net accounts /maxpwage:unlimited</span></span>  <br/> <span data-ttu-id="4fd08-120">Или аналогичный способ отключения срока действия пароля в локальной учетной записи.</span><span class="sxs-lookup"><span data-stu-id="4fd08-120">Or equivalent means of disabling password expiration on the local account.</span></span> <span data-ttu-id="4fd08-121">Невыполнение этого действия приводит к тому, что учетной записи Skype не удается войти в систему с нарушением пароля.</span><span class="sxs-lookup"><span data-stu-id="4fd08-121">Failure to do this will eventually cause the Skype account to fail logon complaining about an expired password.</span></span> <span data-ttu-id="4fd08-122">Обратите внимание, что это влияет на все локальные учетные записи на компьютере, поэтому при установке этого флажка также может возникнуть срок действия административной учетной записи в поле.</span><span class="sxs-lookup"><span data-stu-id="4fd08-122">Note that this impacts all local accounts on the machine, and thus failure to set this will also cause the administrative account on the box to eventually expire as well.</span></span>  <br/> |<span data-ttu-id="4fd08-123">Позволяет учетной записи Skype всегда выполнять вход.</span><span class="sxs-lookup"><span data-stu-id="4fd08-123">Enables Skype account to always log in</span></span>  <br/> |

<span data-ttu-id="4fd08-124">Передача файлов с помощью групповых политик рассматривается в разделе [Настройка элемента файла](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="4fd08-124">Transferring files using Group Policies is discussed in [Configure a File Item](https://technet.microsoft.com/library/cc772536%28v=ws.11%29.aspx).</span></span>
  
## <a name="remote-management-using-powershell"></a><span data-ttu-id="4fd08-125">Удаленное управление с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="4fd08-125">Remote Management using PowerShell</span></span>
<span data-ttu-id="4fd08-126"><a name="RemotePS"> </a></span><span class="sxs-lookup"><span data-stu-id="4fd08-126"></span></span>

<span data-ttu-id="4fd08-127">Мы рекомендуем использовать Microsoft Operations Manager Suite для наблюдения за системами комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4fd08-127">We recommend that you use Microsoft Operations Manager Suite to monitor your Microsoft Teams Rooms systems.</span></span> <span data-ttu-id="4fd08-128">Инструкции по настройке мониторинга и базовому оповещению можно найти в статье [Развертывание управления комнатами Microsoft Teams с помощью монитора Azure](azure-monitor-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="4fd08-128">For guidance on how to set up monitoring and basic alerting, see [Deploy Microsoft Teams Rooms management with Azure Monitor](azure-monitor-deploy.md).</span></span> 

<span data-ttu-id="4fd08-129">С помощью этого руководства вы можете создать простую информационную панель для выявления проблем, связанных с единицами комнат Microsoft Teams во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="4fd08-129">Using this guidance, you can create a simple-to-use dashboard to identify any issues with your Microsoft Teams Rooms units across your deployment.</span></span> 

|    |     |
|-----------|------------|
|![](../media/audio_conferencing_image7.png) <br/><span data-ttu-id="4fd08-130">Точки принятия решений</span><span class="sxs-lookup"><span data-stu-id="4fd08-130">Decision points</span></span>|<ul><li><span data-ttu-id="4fd08-131">Убедитесь, что вы используете набор Operations Management Suite для наблюдения за развертыванием комнат Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4fd08-131">Confirm that you'll use Operations Management Suite to monitor your Microsoft Teams Rooms deployment.</span></span></li><li><span data-ttu-id="4fd08-132">Определите целевой список рассылки, который будет использоваться для отправки оповещений по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="4fd08-132">Decide the target distribution list you’ll use for email alerts.</span></span></li></ul>|
|![](../media/audio_conferencing_image9.png)<br/><span data-ttu-id="4fd08-133">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="4fd08-133">Next steps</span></span>|<ul><li><span data-ttu-id="4fd08-134">Определите качество и уровень контроля надежности.</span><span class="sxs-lookup"><span data-stu-id="4fd08-134">Define your quality and reliability monitoring approach.</span></span></li></ul>|

## <a name="quality-and-reliability-monitoring-cqd"></a><span data-ttu-id="4fd08-135">Мониторинг качества и надежности (CQD)</span><span class="sxs-lookup"><span data-stu-id="4fd08-135">Quality and reliability monitoring (CQD)</span></span>

<span data-ttu-id="4fd08-136">Мы рекомендуем реализовать текущие процедуры контроля качества и надежности в рамках развертывания, чтобы отслеживать изменения качества звонка и собраний, а также надежность, определяя любые области проблемы и применяя разрешение.</span><span class="sxs-lookup"><span data-stu-id="4fd08-136">We recommend that you implement ongoing operational quality and reliability monitoring procedures as part of your deployment to monitor the trending of call and meeting quality and reliability, identifying any areas of concern and working toward a resolution.</span></span> 

<span data-ttu-id="4fd08-137">Когда вы загружаете свою информацию в CQD, вы можете исследовать тенденции качества связи и надежности на уровне здания, что упрощает сравнение зданий и привлечение внимания к определенным проблемам.</span><span class="sxs-lookup"><span data-stu-id="4fd08-137">When you upload your building information to CQD you can investigate call quality and reliability trends on a per-building level, which makes it easy to compare buildings and focus your attention on specific problems.</span></span>

<span data-ttu-id="4fd08-138">Для выявления тенденций качества и надежности и создания плана действий для их устранения рекомендуется проанализировать и выполнить [руководство по пересмотру качества](https://aka.ms/qerguide) .</span><span class="sxs-lookup"><span data-stu-id="4fd08-138">We recommend that you review and follow the [Quality of Experience Review Guide](https://aka.ms/qerguide) to identify quality and reliability trends, and create an action plan to resolve them.</span></span> 

## <a name="updating-the-microsoft-teams-rooms-os-and-microsoft-teams-rooms-application"></a><span data-ttu-id="4fd08-139">Обновление приложения для операционной системы Microsoft Teams и комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4fd08-139">Updating the Microsoft Teams Rooms OS and Microsoft Teams Rooms application</span></span>

<span data-ttu-id="4fd08-140">Рекомендуется обновить приложение Microsoft Teams OS и комнаты Microsoft Teams, чтобы получить преимущества от обновлений и улучшений продукта.</span><span class="sxs-lookup"><span data-stu-id="4fd08-140">We recommend that you update the Microsoft Teams Rooms OS and Microsoft Teams Rooms application to benefit from product updates and improvements.</span></span> <span data-ttu-id="4fd08-141">Подробные инструкции можно найти в статье [Управление комнатами Microsoft Teams](room-systems-v2-operations.md#software-updates).</span><span class="sxs-lookup"><span data-stu-id="4fd08-141">For detailed guidance, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#software-updates).</span></span> 

## <a name="windows-updates"></a><span data-ttu-id="4fd08-142">Обновления Windows</span><span class="sxs-lookup"><span data-stu-id="4fd08-142">Windows Updates</span></span>

<span data-ttu-id="4fd08-143">Комнаты Microsoft Teams работают в Windows 10 Корпоративная IoT или Windows 10 Enterprise (Корпоративная лицензия) и получают одинаковые обновления Windows и операционные системы для обычных рабочих столов.</span><span class="sxs-lookup"><span data-stu-id="4fd08-143">Microsoft Teams Rooms runs on Windows 10 Enterprise IoT or Windows 10 Enterprise (VL) and receives the same Windows Updates and OS builds as a standard desktop.</span></span> <span data-ttu-id="4fd08-144">Дополнительные сведения в разделе [Управление обновлениями Windows](updates.md) .</span><span class="sxs-lookup"><span data-stu-id="4fd08-144">See [Manage Windows Updates](updates.md) for details.</span></span>


## <a name="troubleshooting"></a><span data-ttu-id="4fd08-145">Поиск и устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="4fd08-145">Troubleshooting</span></span>

<span data-ttu-id="4fd08-146">Рекомендуется настроить оповещение Operations Management Suite в соответствии с приведенным выше разделом, чтобы Группа операций и служба поддержки могли получать уведомления о проблемах в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4fd08-146">We recommend that you set up Operations Management Suite alerting as described in the section above so that your operations team and helpdesk will be alerted to any Microsoft Teams Rooms issues.</span></span> <span data-ttu-id="4fd08-147">Параметры удаленного управления PowerShell описаны в разделе [Удаленное управление с помощью PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="4fd08-147">The options you have for PowerShell remote management are described in [Remote Management using PowerShell](room-systems-v2-operations.md#remote-management-using-powershell).</span></span> <span data-ttu-id="4fd08-148">При отключении периферийного устройства может потребоваться полагаться на локальную "интеллектуальную руки" или на службу поддержки, чтобы исследовать и повторно подключать устройства.</span><span class="sxs-lookup"><span data-stu-id="4fd08-148">In the event that a peripheral device is disconnected, you might need to rely on local “smart hands” or IT support to investigate and reconnect the devices.</span></span> 

<span data-ttu-id="4fd08-149">Дополнительные сведения о том, как устранять неполадки и в режиме администратора, приведены в разделе [Управление комнатами Microsoft Teams](room-systems-v2-operations.md#admin-mode-and-device-management).</span><span class="sxs-lookup"><span data-stu-id="4fd08-149">For more information about troubleshooting and admin mode, see [Manage Microsoft Teams Rooms](room-systems-v2-operations.md#admin-mode-and-device-management).</span></span> 


## <a name="see-also"></a><span data-ttu-id="4fd08-150">См. также</span><span class="sxs-lookup"><span data-stu-id="4fd08-150">See also</span></span>

[<span data-ttu-id="4fd08-151">Справка по приложению "Комнаты Microsoft Teams"</span><span class="sxs-lookup"><span data-stu-id="4fd08-151">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="4fd08-152">Планирование комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4fd08-152">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)

[<span data-ttu-id="4fd08-153">Развертывание комнат Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4fd08-153">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)

[<span data-ttu-id="4fd08-154">Настройка консоли Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4fd08-154">Configure a Microsoft Teams Rooms console</span></span>](console.md)

[<span data-ttu-id="4fd08-155">Удаленное управление параметрами консоли Microsoft Teams с помощью XML-файла конфигурации</span><span class="sxs-lookup"><span data-stu-id="4fd08-155">Manage a Microsoft Teams Rooms console settings remotely with an XML configuration file</span></span>](xml-config-file.md)
