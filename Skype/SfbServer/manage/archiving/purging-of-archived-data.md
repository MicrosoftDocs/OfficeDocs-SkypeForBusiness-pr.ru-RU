---
title: Управление удалением архивных данных в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: 'Сводка: сведения об управлении удалением архивных данных для сервера Skype для бизнеса Server.'
ms.openlocfilehash: f168f7fe744ef388de246cbcd2dd9de0fc2ef805
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991614"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a><span data-ttu-id="95a7a-103">Управление удалением архивных данных в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="95a7a-103">Manage purging of archived data in Skype for Business Server</span></span>

<span data-ttu-id="95a7a-104">**Сводка:** Здесь вы узнаете, как управлять удалением архивных данных в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="95a7a-104">**Summary:** Learn how to manage purging of archived data for Skype for Business Server.</span></span>
  
<span data-ttu-id="95a7a-105">База данных архивации не предназначена для долгосрочной продолжительности, и Skype для бизнеса Server не предоставляет решение для хранения архивированных данных, поэтому данные нужно переместить в другое хранилище.</span><span class="sxs-lookup"><span data-stu-id="95a7a-105">The Archiving database is not intended for long-term retention, and Skype for Business Server does not provide an e-discovery (search) solution for archived data, so data needs to be moved to other storage.</span></span> <span data-ttu-id="95a7a-106">В Skype для бизнеса Server есть средство экспорта для сеанса, которое можно использовать для экспорта архивных данных в записи для поиска.</span><span class="sxs-lookup"><span data-stu-id="95a7a-106">Skype for Business Server provides a session export tool that you can use to export archived data into searchable transcripts.</span></span> <span data-ttu-id="95a7a-107">Необходимо указать время удаления архивных и экспортированных данных.</span><span class="sxs-lookup"><span data-stu-id="95a7a-107">You need to define when to purge archived and exported data.</span></span> 
  
<span data-ttu-id="95a7a-108">Дополнительные сведения об экспорте данных с помощью командлета **Export-ксарчивингдата** см. [в разделе Экспорт архивных данных в Skype для бизнеса Server](export-archived-data.md).</span><span class="sxs-lookup"><span data-stu-id="95a7a-108">For more information about exporting data by using the **Export-CsArchivingData** cmdlet, see [Export archived data in Skype for Business Server](export-archived-data.md).</span></span>
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a><span data-ttu-id="95a7a-109">Управление удалением данных с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="95a7a-109">Manage purging of data by using the Control Panel</span></span>

<span data-ttu-id="95a7a-110">Для управления удалением данных с помощью панели управления выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="95a7a-110">To manage purging of archived data by using the Control Panel:</span></span>
  
1. <span data-ttu-id="95a7a-111">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="95a7a-111">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="95a7a-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="95a7a-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="95a7a-113">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="95a7a-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="95a7a-114">В списке конфигураций архивации щелкните имя подходящей глобальной конфигурации либо конфигурации сайта или пула, щелкните **Изменить** и **Показать подробности**, затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="95a7a-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
   - <span data-ttu-id="95a7a-115">Для включения функции удаления данных установите флажок **Разрешить удаление данных архивации**, затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="95a7a-115">To enable purging, select the **Enable purging of archiving data** check box and then do one of the following:</span></span>
    
     - <span data-ttu-id="95a7a-116">Для удаления всех записей выберите **Очищать экспортированные данные архивации, а также данные архивации по окончании максимального срока хранения (дн.)**, затем укажите количество дней.</span><span class="sxs-lookup"><span data-stu-id="95a7a-116">To purge all records, click the **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="95a7a-117">Для удаления только экспортированных данных выберите **Удалять только экспортированные данные архивации**.</span><span class="sxs-lookup"><span data-stu-id="95a7a-117">To purge only the data that has been exported, click **Purge exported archiving data only**.</span></span>
    
   - <span data-ttu-id="95a7a-118">Для отключения функции удаления данных снимите флажок **Разрешить удаление данных архивации**.</span><span class="sxs-lookup"><span data-stu-id="95a7a-118">To disable purging, clear the **Enable purging of archiving data** check box.</span></span>
    
5. <span data-ttu-id="95a7a-119">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="95a7a-119">Click **Commit**.</span></span>
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a><span data-ttu-id="95a7a-120">Управление удалением данных с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="95a7a-120">Manage purging of data by using Windows PowerShell</span></span>

<span data-ttu-id="95a7a-121">Управление удалением архивных данных осуществляется с помощью следующих командлетов Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="95a7a-121">You can manage purging of archived data by using the following Windows PowerShell cmdlets:</span></span>
  
- <span data-ttu-id="95a7a-122">Командлет **Set-CsArchivingConfiguration** с параметром EnablePurging позволяет включить или отключить функцию удаления архивных данных.</span><span class="sxs-lookup"><span data-stu-id="95a7a-122">**Set-CsArchivingConfiguration** cmdlet with the EnablePurging parameter lets you enable or disable purging of archived data.</span></span>
    
- <span data-ttu-id="95a7a-123">Командлет **Invoke-CsArchivingDatabasePurge** позволяет удалять записи из архивной базы данных вручную.</span><span class="sxs-lookup"><span data-stu-id="95a7a-123">**Invoke-CsArchivingDatabasePurge** lets you manually purge records from the Archiving database.</span></span>
    
<span data-ttu-id="95a7a-124">Например, следующая команда обеспечивает удаление вех архивных данных.</span><span class="sxs-lookup"><span data-stu-id="95a7a-124">For example, the following command enables the purging of all archived data.</span></span> <span data-ttu-id="95a7a-125">После запуска этой команды в Skype для бизнеса Server будут очищены все записи архивации, предшествующие значению, указанному в параметре Кипарчивингдатафордайс.</span><span class="sxs-lookup"><span data-stu-id="95a7a-125">After this command is run, Skype for Business Server will purge all archiving records older than the value specified for the KeepArchivingDataForDays parameter.</span></span> 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

<span data-ttu-id="95a7a-126">При выполнении следующей команды (применяется командлет **Export-CSArchivingData**) удаляются только те архивные записи, которые экспортированы в файл данных.</span><span class="sxs-lookup"><span data-stu-id="95a7a-126">The following command limits purging to archived records that have been exported to a data file (by using the **Export-CSArchivingData** cmdlet).</span></span> <span data-ttu-id="95a7a-127">Необходимо также задать для параметра PurgeExportedArchivesOnly значение True ($True).</span><span class="sxs-lookup"><span data-stu-id="95a7a-127">You must also set the PurgeExportedArchivesOnly parameter to True ($True):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

<span data-ttu-id="95a7a-128">После запуска этой команды в Skype для бизнеса Server будут очищены только записи архивации, удовлетворяющие двум условиям: 1) они старше, чем значение, указанное в параметре Кипарчивингдатафордайс; и 2) они экспортированы с помощью командлета **Export-ксарчивингдата** .</span><span class="sxs-lookup"><span data-stu-id="95a7a-128">After this command is run, Skype for Business Server will only purge archiving records that meet two criteria: 1) they are older than the value specified for the KeepArchivingDataForDays parameter; and, 2) they have been exported by using the **Export-CsArchivingData** cmdlet.</span></span>
  
<span data-ttu-id="95a7a-129">Для отключения автоматического удаления архивных записей задайте для параметра EnablePurging значение False ($False).</span><span class="sxs-lookup"><span data-stu-id="95a7a-129">To disable the automated purging of archiving records, set the EnablePurging parameter to False ($False):</span></span>
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

<span data-ttu-id="95a7a-130">В следующем примере командлет **Invoke-ксарчивингдатабасепурже** используется для очистки всех записей, не превышающих 24 часа, из базы данных архивации в ATL-SQL-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="95a7a-130">The following example uses the **Invoke-CsArchivingDatabasePurge** cmdlet to purge all the records more than 24 hours old from the archiving database on atl-sql-001.contoso.com.</span></span> <span data-ttu-id="95a7a-131">Для удаления всех, а не только экспортированных записей параметру PurgeExportedArchivesOnly присвоено значение False ($False).</span><span class="sxs-lookup"><span data-stu-id="95a7a-131">To ensure that all the records are deleted, including records that have not been exported, the PurgeExportedArchivesOnly parameter is set to False ($False):</span></span>
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
