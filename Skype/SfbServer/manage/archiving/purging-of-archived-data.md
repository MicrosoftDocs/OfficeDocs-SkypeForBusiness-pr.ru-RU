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
description: Сводка. Узнайте, как управлять процессом с помощью skype для бизнеса Server, чтобы управлять процессом с помощью архивных данных.
ms.openlocfilehash: aecc78f84b3cd4b745a96e534535c98c1739c156
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828539"
---
# <a name="manage-purging-of-archived-data-in-skype-for-business-server"></a>Управление purging архивных данных в Skype для бизнеса Server

**Сводка:** Learn how to manage purging of archived data for Skype for Business Server.
  
База данных архивирования не предназначена для долгосрочного хранения, и Skype для бизнеса Server не предоставляет решение обнаружения электронных данных (поиска) для архивных данных, поэтому данные необходимо перемещать в другое хранилище. Skype для бизнеса Server предоставляет средство экспорта сеансов, которое можно использовать для экспорта архивных данных в записи с возможностью поиска. Необходимо определить время очистки архивных и экспортных данных. 
  
Дополнительные сведения об экспорте данных с помощью cmdlet **Export-CsArchivingData** см. в экспорте архивных данных [в Skype для бизнеса Server.](export-archived-data.md)
  
## <a name="manage-purging-of-data-by-using-the-control-panel"></a>Управление purging данных с помощью панели управления

Для управления с помощью панели управления для управления архивными данными с помощью панели управления:
  
1. Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator. 
    
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 
    
3. В левой панели навигации щелкните **"Мониторинг** и архивация" и выберите **"Конфигурация архивации".**
    
4. В списке конфигураций архивации выберите название соответствующей глобальной конфигурации, конфигурации узла или пула, в меню **Правка** выберите пункт **Показать подробности** и затем сделайте следующее.
    
   - Чтобы включить очистку, установите флажок **Включить очистку данных архивации** и выполните одно из следующих действий.
    
     - Чтобы очистить все записи, щелкните **Очищать экспортированные и сохраненные данные архивации после максимального срока (дней)** и укажите число дней.
    
     - Чтобы очистить только экспортированные данные, щелкните **Очищать только экспортированные данные архивации**.
    
   - Чтобы отключить очистку, снимите флажок **Включить очистку данных архивации**.
    
5. Нажмите кнопку **Сохранить**.
    
## <a name="manage-purging-of-data-by-using-windows-powershell"></a>Управление с помощью Windows PowerShell

Вы можете управлять с помощью следующих Windows PowerShell данных:
  
- **С помощью cmdlet Set-CsArchivingConfiguration** с параметром EnablePurging можно включить или отключить дефис архивных данных.
    
- **Invoke-CsArchivingDatabasePurge** позволяет вручную очищать записи из базы данных архива.
    
Например, следующая команда позволяет с помощью этой команды совать все архивные данные. После запуска этой команды Skype для бизнеса Server очищает все записи архивации старше значения, указанного для параметра KeepArchivingDataForDays. 
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
```

Следующая команда ограничивает объем архивных записей, экспортданных в файл данных (с помощью командлета **Export-CSArchivingData).** Также необходимо установить для параметра PurgeExportedArchivesOnly $True):
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
```

После запуска этой команды Skype для бизнеса Server будет очищать только записи архивации, которые соответствуют двум критериям: 1) они старше значения, указанного для параметра KeepArchivingDataForDays; и 2) они были экспортироваться с помощью **cmdlet Export-CsArchivingData.**
  
Чтобы отключить автоматическую purging записей архива, установите для параметра EnablePurging $False:
  
```PowerShell
Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False
```

В следующем примере используется cmdlet **Invoke-CsArchivingDatabasePurge** для очистки всех записей старше 24 часов из базы данных архивов в atl-sql-001.contoso.com. Чтобы убедиться, что все записи удалены, в том числе не экспортируются, параметру PurgeExportedArchivesOnly задано $False:
  
```PowerShell
Invoke-CsArchivingDatabasePurge -Identity "service:ArchivingDatabase:atl-sql-001.contoso.com" -PurgeArchivingDataOlderThanHours 24 -PurgeExportedArchivesOnly $False
```
