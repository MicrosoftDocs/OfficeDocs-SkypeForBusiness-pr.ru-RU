---
title: Указание срока хранения данных CDR в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
description: 'Сводка: Сведения об управлении данных регистрации вызовов (CDR) для Скайп для Business Server.'
ms.openlocfilehash: 70fa015978b9b72d020fb52cf62ef749fabb4702
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898054"
---
# <a name="specify-retention-of-cdr-data-in-skype-for-business-server"></a><span data-ttu-id="98b31-103">Указание срока хранения данных CDR в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="98b31-103">Specify retention of CDR data in Skype for Business Server</span></span>
 
<span data-ttu-id="98b31-104">**Сводка:** Сведения об управлении данных регистрации вызовов (CDR) для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="98b31-104">**Summary:** Learn how to manage call detail recording (CDR) data for Skype for Business Server.</span></span>
  
<span data-ttu-id="98b31-p101">По умолчанию данные регистрации вызовов (CDR) удаляются по прошествии 60 дней. Можно использовать параметры на странице **Регистрация вызовов**, чтобы задать хранение данных в течение большего или меньшего времени. Если отключить CDR, то данные, которые были записаны до включения CDR, также будут удаляться.</span><span class="sxs-lookup"><span data-stu-id="98b31-p101">By default, call detail recording (CDR) data is purged after 60 days. You can use the settings on the **Call Detail Recording** page to retain the data for a longer or shorter period of time. If you disable CDR, data that was captured before CDR was enabled will also be subject to purging.</span></span>
  
> [!NOTE]
> <span data-ttu-id="98b31-p102">Необходимо настроить CDR и качество взаимодействия (QoE) для хранения данных в течении одинакового числа дней. Каждый звонок в отчетах CDR, доступных на веб-странице отчетов сервера мониторинга, включает сведения CDR и качества взаимодействия. Если время для удаления данных CDR и качества взаимодействия отличается, некоторые звонки могут содержать только данные CDR, а другие могут содержать только данные качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="98b31-p102">You should configure CDR and Quality of Experience (QoE) to retain data for the same number of days. Each call in the call detail reports (CDRs), available from the Monitoring Server Reports webpage, includes CDR and QoE information. If the purging duration for CDR and QoE is different, some calls might only include CDR data, while other may only include QoE data.</span></span> 
  
<span data-ttu-id="98b31-111">Для настройки параметров очистки данных CDR используется следующая процедура.</span><span class="sxs-lookup"><span data-stu-id="98b31-111">Use the following procedures to configure purge settings for CDR data.</span></span> 
  
### <a name="to-specify-retention-of-cdr-data"></a><span data-ttu-id="98b31-112">Настройка хранения данных CDR</span><span class="sxs-lookup"><span data-stu-id="98b31-112">To specify retention of CDR data</span></span>

1. <span data-ttu-id="98b31-113">Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server .</span><span class="sxs-lookup"><span data-stu-id="98b31-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="98b31-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="98b31-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="98b31-115">В левой панели навигации щелкните **Мониторинг и архивирование**, а затем — **Регистрация вызовов**.</span><span class="sxs-lookup"><span data-stu-id="98b31-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>
    
4. <span data-ttu-id="98b31-116">На странице **Регистрация вызовов** в таблице щелкните необходимый сайт, щелкните **Правка**, а затем — **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="98b31-116">On the **Call Detail Recording** page, click the appropriate site in the table, click **Edit**, and then click **Show Details**.</span></span>
    
5. <span data-ttu-id="98b31-117">Чтобы включить удаление, выберите параметр **Enable Purging of CDRs** (Включить очистку CDR).</span><span class="sxs-lookup"><span data-stu-id="98b31-117">To turn on purging, select **Enable purging of CDRs**.</span></span>
    
6. <span data-ttu-id="98b31-118">В параметре **Keep call detail recordings CDRs for maximum duration (days):** (Сохранять CDR не более (дней)) выберите максимальное число дней, в течение которых должны храниться данные регистрации вызовов.</span><span class="sxs-lookup"><span data-stu-id="98b31-118">In **Keep CDRs for maximum duration (days):** select the maximum number of days that call detail recordings should be retained.</span></span>
    
7. <span data-ttu-id="98b31-119">В параметре **Хранить сведения отчетов об ошибках максимум в течение (дней):** выберите максимальное число дней, в течение которых должны храниться данные отчетов об ошибках.</span><span class="sxs-lookup"><span data-stu-id="98b31-119">In **Keep error report data for maximum duration (days):** select the maximum number of days that error reports should be retained.</span></span>
    
8. <span data-ttu-id="98b31-120">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="98b31-120">Click **Commit**.</span></span>
    
## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="98b31-121">Указание параметров хранения CDR с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="98b31-121">Specifying CDR retention by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="98b31-122">Можно создавать параметры хранения CDR с помощью командлета Set-CsCdrConfiguration и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98b31-122">You can create CDR retention settings by using Windows PowerShell and the Set-CsCdrConfiguration cmdlet.</span></span> <span data-ttu-id="98b31-123">Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98b31-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="98b31-124">Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="98b31-124">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="98b31-125">Процесс одинаков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="98b31-125">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-specify-cdr-retention-for-a-specific-location"></a><span data-ttu-id="98b31-126">Задание параметров хранения CDR для конкретного расположения</span><span class="sxs-lookup"><span data-stu-id="98b31-126">To specify CDR retention for a specific location</span></span>

- <span data-ttu-id="98b31-127">Эта команда позволяет очищать данные CDR для сайта Redmond и настраивает сайт для обслуживания данных CDR и данных отчетов об ошибках в течение 20 дней.</span><span class="sxs-lookup"><span data-stu-id="98b31-127">This command enables purging of CDR data for the Redmond site, and configures the site to maintain both CDR data and error reports data for 20 days.</span></span>
    
  ```
  Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

### <a name="to-specify-cdr-retention-for-multiple-locations"></a><span data-ttu-id="98b31-128">Задание параметров хранения CDR для нескольких расположений</span><span class="sxs-lookup"><span data-stu-id="98b31-128">To specify CDR retention for multiple locations</span></span>

- <span data-ttu-id="98b31-129">Эта команда настраивает параметры хранения CDR для всех параметров конфигурации CDR, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="98b31-129">This command configures CDR retention for all the CDR configuration settings in use in an organization.</span></span>
    
  ```
  Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20
  ```

<span data-ttu-id="98b31-130">Для получения дополнительных сведений см раздел справки для командлета [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="98b31-130">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="98b31-131">См. также</span><span class="sxs-lookup"><span data-stu-id="98b31-131">See also</span></span>

[<span data-ttu-id="98b31-132">Вызовов компании recording (CDR) в Скайп for Business Server</span><span class="sxs-lookup"><span data-stu-id="98b31-132">Call detail recording (CDR) in Skype for Business Server</span></span>](call-detail-recording-cdr.md)
