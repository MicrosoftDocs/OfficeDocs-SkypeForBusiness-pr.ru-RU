---
title: Управление удалением архивных данных в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Сводка: Сведения об управлении Удаление архивных данных для Скайп для Business Server 2015.'
ms.openlocfilehash: caeddcd927c20f0622cbd45b6d93abb2bf5d6618
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server-2015"></a><span data-ttu-id="6cc47-103">Управление удалением архивных данных в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="6cc47-103">Manage purging of archived data in Skype for Business Server 2015</span></span>

<span data-ttu-id="6cc47-104">**Сводка:** Сведения об управлении Удаление архивных данных для Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6cc47-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6cc47-105">Базы данных архивирования не предназначен для долгосрочного хранения и Скайп для Business Server 2015 не предоставляет решения на базе электронных документов (поиск) для архивных данных, требуется ли переместить другие хранилища данных.</span><span class="sxs-lookup"><span data-stu-id="6cc47-105">The Archiving database is not intended for long-term retention, and Skype for Business Server 2015 does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="6cc47-106">Скайп для Business Server предоставляет средство экспорта сеанса, которые можно использовать для экспорта архивированных данных в текст для поиска записей.</span><span class="sxs-lookup"><span data-stu-id="6cc47-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="6cc47-107">Необходимо указать время удаления архивных и экспортированных данных.</span><span class="sxs-lookup"><span data-stu-id="6cc47-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="6cc47-108">Дополнительные сведения о Экспорт данных с помощью командлета **Export-CsArchivingData** [Экспорт архивированных данных в Скайп для Business Server 2015](export-archived-data.md)см.</span><span class="sxs-lookup"><span data-stu-id="6cc47-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server 2015](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="6cc47-109">Управление удалением данных с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="6cc47-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="6cc47-110">Для управления удалением данных с помощью панели управления выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6cc47-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="6cc47-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6cc47-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="6cc47-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="6cc47-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="6cc47-113">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="6cc47-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="6cc47-114">В списке конфигураций архивации щелкните имя подходящей глобальной конфигурации либо конфигурации сайта или пула, щелкните **Изменить** и **Показать подробности**, затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="6cc47-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="6cc47-115">Для включения функции удаления данных установите флажок **Разрешить удаление данных архивации**, затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="6cc47-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="6cc47-116">Для удаления всех записей выберите **Очищать экспортированные данные архивации, а также данные архивации по окончании максимального срока хранения (дн.)**, затем укажите количество дней.</span><span class="sxs-lookup"><span data-stu-id="6cc47-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="6cc47-117">Для удаления только экспортированных данных выберите **Удалять только экспортированные данные архивации**.</span><span class="sxs-lookup"><span data-stu-id="6cc47-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="6cc47-118">Для отключения функции удаления данных снимите флажок **Разрешить удаление данных архивации**.</span><span class="sxs-lookup"><span data-stu-id="6cc47-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="6cc47-119">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="6cc47-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="6cc47-120">Управление удалением данных с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6cc47-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="6cc47-121">Управление удалением архивных данных осуществляется с помощью следующих командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6cc47-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="6cc47-122">Командлет **Set-CsArchivingConfiguration** с параметром EnablePurging позволяет включить или отключить функцию удаления архивных данных.</span><span class="sxs-lookup"><span data-stu-id="6cc47-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="6cc47-123">Командлет **Invoke-CsArchivingDatabasePurge** позволяет удалять записи из архивной базы данных вручную.</span><span class="sxs-lookup"><span data-stu-id="6cc47-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="6cc47-124">Например, следующая команда обеспечивает удаление вех архивных данных.</span><span class="sxs-lookup"><span data-stu-id="6cc47-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="6cc47-125">После выполнения этой команды Скайп для Business Server будет ежедневно очищать все записи архивации превышает значение, указанное для параметра KeepArchivingDataForDays.</span><span class="sxs-lookup"><span data-stu-id="6cc47-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="6cc47-126">При выполнении следующей команды (применяется командлет **Export-CSArchivingData**) удаляются только те архивные записи, которые экспортированы в файл данных.</span><span class="sxs-lookup"><span data-stu-id="6cc47-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="6cc47-127">Необходимо также задать для параметра PurgeExportedArchivesOnly значение True ($True).</span><span class="sxs-lookup"><span data-stu-id="6cc47-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="6cc47-128">После выполнения этой команды Скайп для Business Server только будет ежедневно очищать архивации записей, необходимых для двух условий: 1) они старее чем значение, указанное для параметра KeepArchivingDataForDays; и, 2) они были экспортированы с помощью командлета **Export-CsArchivingData** .</span><span class="sxs-lookup"><span data-stu-id="6cc47-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="6cc47-129">Для отключения автоматического удаления архивных записей задайте для параметра EnablePurging значение False ($False).</span><span class="sxs-lookup"><span data-stu-id="6cc47-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="6cc47-130">В следующем примере используется командлет **Invoke-CsArchivingDatabasePurge** , чтобы очистить все записи более 24 часов назад из базы данных архивации на atl-sql-001.contoso.com. Чтобы убедиться, что удаляются все записи, включая записи, которые не были экспортированы, PurgeExportedArchivesOnly параметру присвоено значение False ($False):</span><span class="sxs-lookup"><span data-stu-id="6cc47-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com. To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```