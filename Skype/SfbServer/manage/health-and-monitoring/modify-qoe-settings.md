---
title: Изменение параметров качества работы в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: Сводка. Узнайте, как указать хранение данных QoE в Skype для бизнеса Server.
ms.openlocfilehash: cba8b2b98aa809c0583ad7323ff846e654ca9ace
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118618"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="98cdd-103">Изменение параметров качества работы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="98cdd-103">Modify Quality of Experience settings in Skype for Business Server</span></span>

<span data-ttu-id="98cdd-104">**Сводка:** Узнайте, как указать хранение данных QoE в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="98cdd-104">**Summary:** Learn how to specify retention of QoE data in Skype for Business Server.</span></span>

<span data-ttu-id="98cdd-p101">По умолчанию данные о качестве взаимодействия удаляются каждые 60 дней. Чтобы изменить срок хранения данных, используйте параметры на странице **Данные о качестве взаимодействия**. При отключении записи данных о качестве взаимодействия все собранные ранее данные будут удалены.</span><span class="sxs-lookup"><span data-stu-id="98cdd-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

> [!NOTE]
> <span data-ttu-id="98cdd-p102">Вам нужно задать одинаковый период хранения данных функции регистрации вызовов (CDR) и данных о качестве взаимодействия. Каждый звонок, отраженный в отчетах регистрации вызовов, доступен на домашней странице отчетов сервера мониторинга и содержит как данные функции регистрации вызовов, так и данные о качестве взаимодействия. Если сроки хранения данных функции регистрации вызовов и данных о качестве взаимодействия отличаются, то некоторые вызовы могут содержать только данные функции регистрации вызовов, а другие — только данные о качестве взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="98cdd-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>

<span data-ttu-id="98cdd-111">Ниже даны инструкции по настройке параметров очистки данных о качестве взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="98cdd-111">The following procedure describes how to configure purge settings for QoE data.</span></span>

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="98cdd-112">Чтобы указать хранение данных QoE с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="98cdd-112">To specify retention of QoE data by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="98cdd-113">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="98cdd-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="98cdd-114">Дополнительные сведения см. в разделе **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="98cdd-114">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="98cdd-115">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="98cdd-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="98cdd-116">В левой панели навигации щелкните **Мониторинг и архивация** и затем выберите **Данные о качестве взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="98cdd-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="98cdd-117">На странице **Данные о качестве взаимодействия** выберите требуемый сайт в таблице, щелкните **Изменить** и затем щелкните **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="98cdd-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5. <span data-ttu-id="98cdd-118">Чтобы включить очистку, выберите **Разрешить очистку данных о качестве взаимодействия** .</span><span class="sxs-lookup"><span data-stu-id="98cdd-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6. <span data-ttu-id="98cdd-119">В поле **Хранить данные о качестве взаимодействия не дольше (дн.)** выберите максимальный срок хранения данных о качестве взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="98cdd-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7. <span data-ttu-id="98cdd-120">Щелкните **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="98cdd-120">Click **Commit**.</span></span>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="98cdd-121">Указание хранения QoE с помощью Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="98cdd-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="98cdd-122">Параметры хранения QoE можно создать с помощью Windows PowerShell **и комлета Set-CsQoEConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="98cdd-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="98cdd-123">Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98cdd-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="98cdd-124">Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога ["Быстрый запуск: управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell".</span><span class="sxs-lookup"><span data-stu-id="98cdd-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="98cdd-125">В Skype для бизнеса Server этот процесс является одинаковым.</span><span class="sxs-lookup"><span data-stu-id="98cdd-125">The process is the same in Skype for Business Server.</span></span>

### <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="98cdd-126">Указание срока хранения данных о качестве взаимодействия для определенного расположения</span><span class="sxs-lookup"><span data-stu-id="98cdd-126">To specify QoE retention for a specific location</span></span>

- <span data-ttu-id="98cdd-127">Эта команда включает очистку данных о качестве взаимодействия и настраивает их хранение в течение 20 дней для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="98cdd-127">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>

  ```PowerShell
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="98cdd-128">Указание срока хранения данных о качестве взаимодействия для нескольких расположений</span><span class="sxs-lookup"><span data-stu-id="98cdd-128">To specify QoE retention for multiple locations</span></span>

- <span data-ttu-id="98cdd-129">Эта команда настраивает срок хранения для всех параметров конфигурации качества взаимодействия, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="98cdd-129">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

<span data-ttu-id="98cdd-130">Дополнительные сведения см. в разделе Справка для [cmdlet Set-CsQoEConfiguration.](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="98cdd-130">For more information, see the help topic for the [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="98cdd-131">См. также</span><span class="sxs-lookup"><span data-stu-id="98cdd-131">See also</span></span>

[<span data-ttu-id="98cdd-132">Мониторинг развертывания</span><span class="sxs-lookup"><span data-stu-id="98cdd-132">Deploying Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)