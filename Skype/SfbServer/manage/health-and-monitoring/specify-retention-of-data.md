---
title: Настройка хранения данных CDR в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Сводка: сведения о том, как управлять данными записи сведений о вызовах (CDR) для Skype для бизнеса Server.'
ms.openlocfilehash: ec24b5b1901bec053417c3a938c688cd4692f1c9
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991724"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="9fff4-103">Настройка хранения данных CDR в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9fff4-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="9fff4-104">**Сводка:** Сведения о том, как управлять данными записи сведений о вызовах (CDR) для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9fff4-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="9fff4-p101">По умолчанию данные регистрации вызовов (CDR) удаляются по прошествии 60 дней. Можно использовать параметры на странице **Регистрация вызовов**, чтобы задать хранение данных в течение большего или меньшего времени. Если отключить CDR, то данные, которые были записаны до включения CDR, также будут удаляться.</span><span class="sxs-lookup"><span data-stu-id="9fff4-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9fff4-p102">Необходимо настроить CDR и качество взаимодействия (QoE) для хранения данных в течении одинакового числа дней. Каждый звонок в отчетах CDR, доступных на веб-странице отчетов сервера мониторинга, включает сведения CDR и качества взаимодействия. Если время для удаления данных CDR и качества взаимодействия отличается, некоторые звонки могут содержать только данные CDR, а другие могут содержать только данные качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="9fff4-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="9fff4-111">Для настройки параметров очистки данных CDR используется следующая процедура.</span><span class="sxs-lookup"><span data-stu-id="9fff4-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="9fff4-112">Настройка хранения данных CDR</span><span class="sxs-lookup"><span data-stu-id="9fff4-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="9fff4-113">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="9fff4-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="9fff4-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9fff4-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="9fff4-115">В левой панели навигации щелкните **Мониторинг и архивирование**, а затем — **Регистрация вызовов**.</span><span class="sxs-lookup"><span data-stu-id="9fff4-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="9fff4-116">На странице **Регистрация вызовов** в таблице щелкните необходимый сайт, щелкните **Правка**, а затем — **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="9fff4-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="9fff4-117">Чтобы включить удаление, выберите параметр **Enable Purging of CDRs** (Включить очистку CDR).</span><span class="sxs-lookup"><span data-stu-id="9fff4-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="9fff4-118">В параметре **Keep call detail recordings CDRs for maximum duration (days):** (Сохранять CDR не более (дней)) выберите максимальное число дней, в течение которых должны храниться данные регистрации вызовов.</span><span class="sxs-lookup"><span data-stu-id="9fff4-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="9fff4-119">В параметре **Хранить сведения отчетов об ошибках максимум в течение (дней):** выберите максимальное число дней, в течение которых должны храниться данные отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="9fff4-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="9fff4-120">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="9fff4-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9fff4-121">Указание хранения CDR с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9fff4-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="9fff4-122">Вы можете создать параметры хранения CDR с помощью Windows PowerShell и командлета Set-Кскдрконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="9fff4-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="9fff4-123">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9fff4-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9fff4-124">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="9fff4-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="9fff4-125">Этот процесс одинаков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="9fff4-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="9fff4-126">Задание параметров хранения CDR для конкретного расположения</span><span class="sxs-lookup"><span data-stu-id="9fff4-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="9fff4-127">Эта команда позволяет очищать данные CDR для сайта Redmond и настраивает сайт для обслуживания данных CDR и данных отчетов об ошибках в течение 20 дней.</span><span class="sxs-lookup"><span data-stu-id="9fff4-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```PowerShell
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="9fff4-128">Задание параметров хранения CDR для нескольких расположений</span><span class="sxs-lookup"><span data-stu-id="9fff4-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="9fff4-129">Эта команда настраивает параметры хранения CDR для всех параметров конфигурации CDR, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="9fff4-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="9fff4-130">Дополнительные сведения можно найти в разделе справки по командлету [Set-кскдрконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9fff4-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="9fff4-131">См. также</span><span class="sxs-lookup"><span data-stu-id="9fff4-131">See also</span></span>

[<span data-ttu-id="9fff4-132">Запись сведений о звонке (CDR) в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="9fff4-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)
