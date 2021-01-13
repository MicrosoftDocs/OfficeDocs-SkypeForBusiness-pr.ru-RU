---
title: Управление purging архивных данных в Skype для бизнеса Server
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
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: Сводка. Узнайте, как управлять с помощью Skype для бизнеса Server, чтобы управлять процессом с помощью архивных данных.
ms.openlocfilehash: aecc78f84b3cd4b745a96e534535c98c1739c156
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828539"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="6b180-103">Управление purging архивных данных в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6b180-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="6b180-104">**Сводка:** Learn how to manage purging of archived data for Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6b180-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="6b180-105">База данных архивирования не предназначена для долгосрочного хранения, и Skype для бизнеса Server не предоставляет решение обнаружения электронных данных (поиска) для архивных данных, поэтому данные необходимо перемещать в другое хранилище.</span><span class="sxs-lookup"><span data-stu-id="6b180-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="6b180-106">Skype для бизнеса Server предоставляет средство экспорта сеансов, которое можно использовать для экспорта архивных данных в записи с возможностью поиска.</span><span class="sxs-lookup"><span data-stu-id="6b180-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="6b180-107">Необходимо определить время очистки архивных и экспортных данных.</span><span class="sxs-lookup"><span data-stu-id="6b180-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="6b180-108">Дополнительные сведения об экспорте данных с помощью cmdlet **Export-CsArchivingData** см. в экспорте архивных данных [в Skype для бизнеса Server.](export-archived-data.md)</span><span class="sxs-lookup"><span data-stu-id="6b180-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="6b180-109">Управление purging данных с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="6b180-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="6b180-110">Для управления с помощью панели управления для управления архивными данными с помощью панели управления:</span><span class="sxs-lookup"><span data-stu-id="6b180-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="6b180-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6b180-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="6b180-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6b180-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="6b180-113">В левой панели навигации щелкните **"Мониторинг** и архивация" и выберите **"Конфигурация архивации".**</span><span class="sxs-lookup"><span data-stu-id="6b180-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="6b180-114">В списке конфигураций архивации выберите название соответствующей глобальной конфигурации, конфигурации узла или пула, в меню **Правка** выберите пункт **Показать подробности** и затем сделайте следующее.</span><span class="sxs-lookup"><span data-stu-id="6b180-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="6b180-115">Чтобы включить очистку, установите флажок **Включить очистку данных архивации** и выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="6b180-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="6b180-116">Чтобы очистить все записи, щелкните **Очищать экспортированные и сохраненные данные архивации после максимального срока (дней)** и укажите число дней.</span><span class="sxs-lookup"><span data-stu-id="6b180-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="6b180-117">Чтобы очистить только экспортированные данные, щелкните **Очищать только экспортированные данные архивации**.</span><span class="sxs-lookup"><span data-stu-id="6b180-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="6b180-118">Чтобы отключить очистку, снимите флажок **Включить очистку данных архивации**.</span><span class="sxs-lookup"><span data-stu-id="6b180-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="6b180-119">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="6b180-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="6b180-120">Управление purging данных с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6b180-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="6b180-121">Вы можете управлять purging архивных данных с помощью следующих Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6b180-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="6b180-122">**С помощью cmdlet Set-CsArchivingConfiguration** с параметром EnablePurging можно включить или отключить дефис архивных данных.</span><span class="sxs-lookup"><span data-stu-id="6b180-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="6b180-123">**Invoke-CsArchivingDatabasePurge** позволяет вручную очищать записи из базы данных архива.</span><span class="sxs-lookup"><span data-stu-id="6b180-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="6b180-124">Например, следующая команда позволяет с помощью этой команды совать все архивные данные.</span><span class="sxs-lookup"><span data-stu-id="6b180-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="6b180-125">После запуска этой команды Skype для бизнеса Server очищает все записи архивации старше значения, указанного для параметра KeepArchivingDataForDays.</span><span class="sxs-lookup"><span data-stu-id="6b180-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="6b180-126">Следующая команда ограничивает объем архивных записей, экспортданных в файл данных (с помощью командлета **Export-CSArchivingData).**</span><span class="sxs-lookup"><span data-stu-id="6b180-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="6b180-127">Также необходимо установить для параметра PurgeExportedArchivesOnly $True):</span><span class="sxs-lookup"><span data-stu-id="6b180-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="6b180-128">После запуска этой команды Skype для бизнеса Server будет очищать только записи архивации, которые соответствуют двум критериям: 1) они старше значения, указанного для параметра KeepArchivingDataForDays; и 2) они экспортируются с помощью **cmdlet Export-CsArchivingData.**</span><span class="sxs-lookup"><span data-stu-id="6b180-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="6b180-129">Чтобы отключить автоматическую purging записей архива, установите для параметра EnablePurging $False:</span><span class="sxs-lookup"><span data-stu-id="6b180-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="6b180-130">В следующем примере используется cmdlet **Invoke-CsArchivingDatabasePurge** для очистки всех записей старше 24 часов из базы данных архивов в atl-sql-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6b180-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="6b180-131">Чтобы убедиться, что все записи удалены, в том числе не экспортируются, параметру PurgeExportedArchivesOnly задано $False):</span><span class="sxs-lookup"><span data-stu-id="6b180-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
