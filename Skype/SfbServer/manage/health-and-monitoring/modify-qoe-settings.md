---
title: Изменение параметров качества взаимодействия в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a6b41de2-1466-4240-8a70-14ce6f0f3ddc
description: 'Сводка: Узнайте, как задание параметров хранения данных о качестве взаимодействия в Скайп для Business Server.'
ms.openlocfilehash: 743f3df6f58392e7d9107be9ae4c9313ef7a6781
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/28/2018
ms.locfileid: "23243455"
---
# <a name="modify-quality-of-experience-settings-in-skype-for-business-server"></a><span data-ttu-id="9683e-103">Изменение параметров качества взаимодействия в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="9683e-103">Modify Quality of Experience settings in Skype for Business Server</span></span>

<span data-ttu-id="9683e-104">**Сводка:** Узнайте, как задание параметров хранения данных о качестве взаимодействия в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="9683e-104">**Summary:** Learn how to specify retention of QoE data in Skype for Business Server.</span></span>

<span data-ttu-id="9683e-p101">По умолчанию данные о качестве взаимодействия удаляются каждые 60 дней. Чтобы изменить срок хранения данных, используйте параметры на странице **Данные о качестве взаимодействия**. При отключении записи данных о качестве взаимодействия все собранные ранее данные будут удалены.</span><span class="sxs-lookup"><span data-stu-id="9683e-p101">By default, Quality of Experience (QoE) data is purged after 60 days. You can use the settings on the **Quality of Experience Data** page to retain the data for a longer or shorter period of time. If you disable QoE, data that was captured before QoE was enabled will also be subject to purging.</span></span>

> [!NOTE]
> <span data-ttu-id="9683e-p102">Вам нужно задать одинаковый период хранения данных функции регистрации вызовов (CDR) и данных о качестве взаимодействия. Каждый звонок, отраженный в отчетах регистрации вызовов, доступен на домашней странице отчетов сервера мониторинга и содержит как данные функции регистрации вызовов, так и данные о качестве взаимодействия. Если сроки хранения данных функции регистрации вызовов и данных о качестве взаимодействия отличаются, то некоторые вызовы могут содержать только данные функции регистрации вызовов, а другие — только данные о качестве взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9683e-p102">You should configure call detail recording (CDR) and QoE to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Reports homepage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls may only include CDR data, while other may only include QoE data.</span></span>

<span data-ttu-id="9683e-111">Ниже даны инструкции по настройке параметров очистки данных о качестве взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9683e-111">The following procedure describes how to configure purge settings for QoE data.</span></span>

### <a name="to-specify-retention-of-qoe-data-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="9683e-112">Указание срока хранения данных о качестве взаимодействия с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="9683e-112">To specify retention of QoE data by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="9683e-113">Войдите на компьютер как член группы RTCUniversalServerAdmins или членом роли CsVoiceAdministrator, CsServerAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9683e-113">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="9683e-114">Дополнительные сведения см **Делегирование разрешений на установку**.</span><span class="sxs-lookup"><span data-stu-id="9683e-114">For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="9683e-115">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="9683e-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="9683e-116">На панели навигации слева нажмите **Мониторинг и архивация**, затем выберите **Данные о качестве взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="9683e-116">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="9683e-117">На странице **Данные о качестве взаимодействия** выберите требуемый сайт в таблице, нажмите **Изменить** и выберите **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="9683e-117">On the **Quality of Experience Data** page, click the appropriate site from the table, click **Edit**, and then click **Show Details**.</span></span>

5. <span data-ttu-id="9683e-118">Чтобы включить очистку, выберите **Разрешить очистку данных о качестве взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="9683e-118">To turn on purging, select **Enable Purging of QoE**.</span></span>

6. <span data-ttu-id="9683e-119">В поле **Хранить данные о качестве взаимодействия не дольше (дн.)** выберите максимальный срок хранения данных о качестве взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9683e-119">In **Keep QoE for maximum duration (days)** select the maximum number of days that QoE data should be retained.</span></span>

7. <span data-ttu-id="9683e-120">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="9683e-120">Click **Commit**.</span></span>

## <a name="specifying-qoe-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9683e-121">Указание способа хранения качества взаимодействия с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9683e-121">Specifying QoE Retention by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="9683e-122">Можно создать параметры хранения качества взаимодействия с помощью Windows PowerShell и командлет **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="9683e-122">You can create QoE retention settings by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="9683e-123">Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9683e-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9683e-124">Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="9683e-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="9683e-125">Процесс одинаков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="9683e-125">The process is the same in Skype for Business Server.</span></span>

### <a name="to-specify-qoe-retention-for-a-specific-location"></a><span data-ttu-id="9683e-126">Указание срока хранения данных о качестве взаимодействия для определенного расположения</span><span class="sxs-lookup"><span data-stu-id="9683e-126">To specify QoE retention for a specific location</span></span>

- <span data-ttu-id="9683e-127">Эта команда включает очистку данных о качестве взаимодействия и настраивает их хранение в течение 20 дней для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="9683e-127">This command enables purging of QoE data for the Redmond site, and configures the site to maintain QoE data for 20 days.</span></span>

  ```
  Set-CsQoeConfiguration -Identity "site:Redmond" -EnablePurging -KeepQoEDataForDays 20
  ```

### <a name="to-specify-qoe-retention-for-multiple-locations"></a><span data-ttu-id="9683e-128">Указание срока хранения данных о качестве взаимодействия для нескольких расположений</span><span class="sxs-lookup"><span data-stu-id="9683e-128">To specify QoE retention for multiple locations</span></span>

- <span data-ttu-id="9683e-129">Эта команда настраивает срок хранения для всех параметров конфигурации качества взаимодействия, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="9683e-129">This command configures QoE retention for all the QoE configuration settings in use in an organization.</span></span>

  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration-EnablePurging -KeepQoEDataForDays 20
  ```

<span data-ttu-id="9683e-130">Для получения дополнительных сведений см раздел справки для командлета [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9683e-130">For more information, see the help topic for the [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="9683e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="9683e-131">See also</span></span>

[<span data-ttu-id="9683e-132">Мониторинг развертывания</span><span class="sxs-lookup"><span data-stu-id="9683e-132">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)