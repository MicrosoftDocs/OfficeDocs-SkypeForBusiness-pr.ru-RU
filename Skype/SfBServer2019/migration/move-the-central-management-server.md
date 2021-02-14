---
title: Перемещение центрального сервера управления
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: After migrating to Skype for Business Server 2019, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool, before you can remove the legacy server.
ms.openlocfilehash: b5412e1b538627c50c3f2a98a5b68c64364f00a9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752471"
---
# <a name="move-the-legacy-central-management-server-to-skype-for-business-server-2019"></a>Перемещение устаревшего центрального сервера управления в Skype для бизнеса Server 2019

After migrating to Skype for Business Server 2019, and before you can remove the legacy server, you need to move the Central Management Server to the Skype for Business Server 2019 Front End Server or pool. 
  
Центральный сервер управления — это единая система реплики с несколькими хозяинами, где копия базы данных для чтения и записи хранится сервером переднего сервера, который содержит центральный сервер управления. Каждый компьютер в топологии, включая сервер переднего сервера, содержащий центральный сервер управления, имеет доступную только для чтения копию данных центрального банка управления в базе данных SQL Server (с именем RTCLOCAL по умолчанию), установленной на компьютере во время установки и развертывания. Локализованная база данных получает обновления реплики с помощью агента репликатора репликации Skype для бизнеса Server, который работает как служба на всех компьютерах. Имя фактической базы данных на центральном сервере управления и локальной реплики — XDS, которая состоит из файлов xds.mdf и xds.ldf. На расположение базы данных-хозяина ссылается точка управления службой (SCP) в доменных службах Active Directory. Все средства, которые используют центральный сервер управления для управления и настройки Skype для бизнеса Server, используют SCP для поиска центрального банка управления.
  
После успешного удаления центрального сервера управления следует удалить базы данных центрального сервера управления с исходного сервера переднего сервера. Сведения об удалении баз данных центрального сервера управления см. в SQL Server базы данных для [пула переднего сервера.](remove-the-sql-server-database-for-a-front-end-pool.md)
  
Используйте Windows PowerShell **Move-CsManagementServer** в оболочке управления Skype для бизнеса Server для перемещения базы данных из устаревшей базы данных SQL Server в базу данных SQL Server Skype для бизнеса Server 2019, а затем обновим SCP так, чтобы она была указать на расположение центрального сервера управления Skype для бизнеса Server 2019. 
  
Используйте процедуры в этом разделе для подготовки серверов переднего сервера Skype для бизнеса Server 2019 перед перемещением центрального сервера управления.
  
## <a name="to-prepare-an-enterprise-edition-front-end-pool"></a>Подготовка пула переднего конца Enterprise Edition

1. On the Skype for Business Server 2019 Enterprise Edition Front End pool where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group. Кроме того, SQL Server правами и разрешениями sysadmin базы данных, в которой необходимо установить центральное хранилище управления. 
    
2. Откройте оболочку управления Skype для бизнеса Server.
    
3. Чтобы создать новое центральное хранилище управления в базе данных SQL Server Skype для бизнеса Server 2019, введите в оболочке управления Skype для бизнеса Server 2019 2019:
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your SQL Server> -SQLInstanceName <name of instance>
   ```

4. Подтвердим, что состояние службы **переднего** сервера Skype для бизнеса Server **запущено.**
    
## <a name="to-prepare-a-standard-edition-front-end-server"></a>Подготовка сервера переднего сервера Standard Edition

1. On the Skype for Business Server 2019 Standard Edition Front End Server where you want to relocate the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group. 
    
2. Откройте мастер развертывания Skype для бизнеса Server.
    
3. В мастере развертывания Skype для бизнеса Server щелкните **"Подготовить первый сервер Standard Edition".**
    
4. На странице **"Выполнение** команд SQL Server Express устанавливается в качестве центрального сервера управления. Создаются необходимые правила брандмауэра. После завершения установки базы данных и предварительно устанавливаемого ПО нажмите кнопку **Готово**.
    
    > [!NOTE]
    > При первоначальной установке может пройти некоторое время, прежде чем на экране вывода результатов команд появятся какие-либо изменения. Это связано с установкой SQL Server Express. Если необходимо отслеживать установку базы данных, используйте для этого диспетчер задач. 
  
5. To create the new Central Management store on the Skype for Business Server 2019 Standard Edition Front End Server, in the Skype for Business Server Management Shell, type: 
    
   ```PowerShell
   Install-CsDatabase -CentralManagementDatabase -SQLServerFQDN <FQDN of your Standard Edition Server> -SQLInstanceName <name of instance - RTC by default>
   ```

6. Подтвердим, что состояние службы **переднего** сервера Skype для бизнеса Server **запущено.**
    
## <a name="to-move-the-legacy-installs-central-management-server-to-skype-for-business-server-2019"></a>Перемещение устаревшей системы установки центрального сервера управления в Skype для бизнеса Server 2019

1. On the Skype for Business Server 2019 server that will be the Central Management Server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group. Необходимо также иметь права и разрешения администратора базы данных SQL Server. 
    
2. Откройте Skype для бизнеса Server Management Shell (запуск от администратора).
    
3. In the Skype for Business Server Management Shell, type: 
    
   ```PowerShell
   Enable-CsTopology
   ```

    > [!CAUTION]
    > Если `Enable-CsTopology` это не удалось, уладим проблему, не мешая выполнению команды, прежде чем продолжить. Если **enable-CsTopology** не удается, перемещение не удастся и топология может оказаться в состоянии, когда центральное хранилище управления не существует. 
  
4. On the Skype for Business Server 2019 Front End Server or Front End pool, in the Skype for Business Server Management Shell, type: 
    
   ```PowerShell
   Move-CsManagementServer
   ```

5. В оболочке управления Skype для бизнеса Server отображаются серверы, хранилища файлов, хранилища баз данных и точки подключения служб текущего состояния и предложенного состояния. Внимательно просмотрите сведения об исходном и целевом состоянии и убедитесь, что они правильны. Введите **Y**, чтобы продолжить, или **N**, чтобы остановить перемещение. 
    
6. Проверьте все предупреждения и ошибки, сгенерированные командой **Move-CsManagementServer**, и устраните их. 
    
7. На сервере Skype для бизнеса Server 2019 откройте мастер развертывания Skype для бизнеса Server. 
    
8. In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click Step **2: Setup or Remove Skype for Business Server Components,** click **Next**, review the summary, and then click **Finish**. 
    
9. На сервере установки прежних версиях откройте мастер развертывания. 
    
10. In Skype for Business Server Deployment Wizard, click **Install or Update Skype for Business Server System**, click Step **2: Setup or Remove Skype for Business Server Components,** click **Next**, review the summary, and then click **Finish**. 
    
11. Перезагружает сервер Skype для бизнеса Server 2019. Это необходимо из-за изменения членства в группе для доступа к базе данных центрального сервера управления.
    
12. To confirm that replication with the new Central Management store is occurring, in the Skype for Business Server Management Shell, type: 
    
    ```PowerShell
    Get-CsManagementStoreReplicationStatus
    ```

    > [!NOTE]
    > Обновление всех текущих реплик может занять некоторое время. 
  
## <a name="to-remove-legacy-install-central-management-store-files-after-a-move"></a>Удаление устаревших файлов центрального банка управления после перемещения

1. On the legacy install server, log on to the computer where the Skype for Business Server Management Shell is installed as a member of the **RTCUniversalServerAdmins** group. Необходимо также иметь права и разрешения администратора базы данных SQL Server. 
    
2. Open Skype for Business Server Management Shell
    
    > [!CAUTION]
    > Не удаляйте файлы старой базы данных, пока репликация не завершится и не станет стабильной. Если удалить файлы до завершения репликации, процесс репликации будет прерван и новый центральный сервер управления останется в неизвестном состоянии. Используйте командлет **Get-CsManagementStoreReplicationStatus** для подтверждения состояния репликации. 
  
3. Чтобы удалить файлы базы данных центрального банка управления из устаревшей установки центрального сервера управления, введите:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn <FQDN of SQL Server> -SqlInstanceName <Name of source server>
   ```

    Пример:
    
   ```PowerShell
   Uninstall-CsDatabase -CentralManagementDatabase -SqlServerFqdn sql.contoso.net -SqlInstanceName rtc
   ```

    Где это либо устаревший сервер установки в развертывании Enterprise Edition, либо  _\<FQDN of SQL Server\>_ FQDN сервера Standard Edition. 
    

