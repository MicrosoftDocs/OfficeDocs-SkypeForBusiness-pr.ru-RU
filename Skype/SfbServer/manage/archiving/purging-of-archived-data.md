---
title: Управление чисткой архивных данных в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 14c2b4fd-f612-4909-808d-09c655fc9f8a
description: Сводка. Узнайте, как управлять чисткой архивных данных для Skype для бизнеса Server.
ms.openlocfilehash: 4050bc40d72cb8a2b306ab050298bb74b7c96dbd
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847442"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Управление чисткой архивных данных в Skype для бизнеса Server

**Сводка:** Узнайте, как управлять чисткой архивных данных для Skype для бизнеса Server.
  
База данных архивирования не предназначена для долгосрочного хранения, и Skype для бизнеса Server не предоставляет решение электронного обнаружения (поиска) для архивных данных, поэтому данные должны быть перемещены в другое хранилище. Skype для бизнеса Server предоставляет средство экспорта сеансов, которое можно использовать для экспорта архивных данных в записи, которые можно найти. Необходимо определить время очистки архивных и экспортных данных. 
  
Дополнительные сведения об экспорте данных с помощью **cmdlet Export-CsArchivingData** см. в [Skype для бизнеса Server.](export-archived-data.md)
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Управление чисткой данных с помощью панели управления

Управление чисткой архивных данных с помощью панели управления:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления. 
    
3. В левой панели навигации щелкните Мониторинг и **архивация,** а затем щелкните **конфигурацию архивации.**
    
4. В списке конфигураций архивации выберите название соответствующей глобальной конфигурации, конфигурации узла или пула, в меню **Правка** выберите пункт **Показать подробности** и затем сделайте следующее.
    
   - Чтобы включить очистку, установите флажок **Включить очистку данных архивации** и выполните одно из следующих действий.
    
     - Чтобы очистить все записи, щелкните **Очищать экспортированные и сохраненные данные архивации после максимального срока (дней)** и укажите число дней.
    
     - Чтобы очистить только экспортированные данные, щелкните **Очищать только экспортированные данные архивации**.
    
   - Чтобы отключить очистку, снимите флажок **Включить очистку данных архивации**.
    
5. Нажмите кнопку **Сохранить**.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Управление чисткой данных с помощью Windows PowerShell

Вы можете управлять чисткой архивных данных с помощью следующих Windows PowerShell:
  
- **Комлет Set-CsArchivingConfiguration** с параметром EnablePurging позволяет включить или отключить чистку архивных данных.
    
- **Invoke-CsArchivingDatabasePurge** позволяет вручную очищать записи из базы данных архива.
    
Например, в следующей команде обеспечивается чистка всех архивных данных. После запуска этой команды Skype для бизнеса Server все записи архивации старше значения, указанного для параметра KeepArchivingDataForDays. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

Следующая команда ограничивает чистку архивных записей, экспортируемых в файл данных (с помощью **командлета Export-CSArchivingData).** Необходимо также установить параметр PurgeExportedArchivesOnly для True ($True):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

После запуска этой команды Skype для бизнеса Server только записи архивации, которые соответствуют двум критериям: 1) они старше значения, указанного для параметра KeepArchivingDataForDays; и 2) они экспортируются с помощью **cmdlet Export-CsArchivingData.**
  
Чтобы отключить автоматическую чистку архивных записей, установите параметр EnablePurging false ($False):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

В следующем примере используется кодлет **Invoke-CsArchivingDatabasePurge** для очистки всех записей более 24 часов из базы данных архива на atl-sql-001.contoso.com. Чтобы убедиться, что все записи удаляются, включая записи, которые не экспортируются, параметр PurgeExportedArchivesOnly задан в false ($False):
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
