---
title: Командная консоль Skype для бизнеса Server
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
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Командная оболочка Skype для бизнеса Server предоставляет интерфейс командной строки для администрирования и управления сервером. Он построен на Windows PowerShell и включает полный набор средств управления и администрирования, которые относятся к Skype и устаревшим серверным продуктам Lync.
ms.openlocfilehash: 0653faa542bc9bc579bd7617e40d3efed030569f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816539"
---
# <a name="skype-for-business-server-management-shell"></a>Командная консоль Skype для бизнеса Server
 
Командная оболочка Skype для бизнеса Server предоставляет интерфейс командной строки для администрирования и управления сервером. Он построен на Windows PowerShell и включает полный набор средств управления и администрирования, которые относятся к Skype и устаревшим серверным продуктам Lync.
  
Windows PowerShell позволяет управлять приложениями Майкрософт из командной строки. Оно предоставляет среду командной строки, команды для определенных продуктов и полноценный язык скриптов. Windows PowerShell впервые была представлена в качестве загружаемого выпуска для операционной системы Windows в конце 2006 г. и была включена в качестве интерфейса командной строки для управления Microsoft Exchange Server 2007. Она была включена в большинство продуктов Microsoft Server, включая серверы Lync и Skype, начиная с Lync Server 2010. В оболочке управления Skype для бизнеса Server доступно более 700 специальных cmdlets для Lync и Skype.
  
> [!NOTE]
> Справочник по cmdlet skype для бизнеса перемещен в docs.microsoft.com. Щелкнув ссылки ниже, вы перейдите на новую docs.microsoft.com страницу. Теперь содержимое доступно с открытым исходным кодом и доступно для сообщества с помощью GitHub. Заинтересованы в том, чтобы вносить свой вклад? Ознакомьтесь с readME в репо здесь: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype для бизнеса Server включает более 700 cmdlets, позволяющих администраторам управлять Skype для бизнеса Server с помощью оболочки управления Skype для бизнеса Server. Справку по командлету можно получить непосредственно из командной строки, введя команду, аналогичную следующей:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

В предыдущей команде извлекалась полная справка, доступная для командлета **New-CsVoicePolicy.** Чтобы просмотреть справку для другого cmdlet, замените **New-CsVoicePolicy** именем, для которого требуется получить справку.
  
Чтобы получить полный список командлетов, доступных для управления Skype для бизнеса Server, введите в командной области оболочки следующую команду: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Что нужно знать о Windows PowerShell в Skype для бизнеса Server:
  
- Чтобы запустить команды Skype для бизнеса Server, откройте оболочку управления Skype для бизнеса Server.
    
    > [!CAUTION]
    > If you open a Windows PowerShell rather than the Skype for Business Server Management Shell, by default you may not be able to run the Skype cmdlets. Чтобы запустить командлеты Skype для бизнеса Server из Windows PowerShell, введите в командной Windows PowerShell следующую команду: >  `Import-Module SkypeforBusiness`
  
- Skype для бизнеса Server Management Shell автоматически устанавливается на каждом сервере переднего сервера Skype для бизнеса Server Enterprise Edition или сервере Standard Edition.
    
- You can update the Skype for Business Server Management Shell help content by running the [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) cmdlet. Командлет Update-Help загружает и устанавливает самые новые файлы справки, доступные для всех модулей, установленных на компьютере, включая обновления командлетов Skype для бизнеса.
    
    По умолчанию **командлет Update-Help** обновляет все модули, установленные в Skype для бизнеса Server. Чтобы обновить только определенные модули, можно использовать параметр _Module,_ чтобы ограничить область действия командлета. В следующем примере обновляется только модуль Skype для бизнеса.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Если требуется обновить справку на серверах, не подключенных к [](https://technet.microsoft.com/library/hh849724.aspx) Интернету, вы можете использовать для получения последней версии справки и сохранения ее в задаемом расположении. Затем можно использовать  для получения обновленной справки из выбранного расположения с помощью параметра _-SourcePath_ на серверах, не подключенных к Интернету. В следующем примере показано, как сохранить файлы справки в сетевой папке, а затем обновить справку для модуля Skype для бизнеса из файловой папки.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Дополнительные сведения см. в [справке по updatable.](https://technet.microsoft.com/library/hh847735.aspx)
    
    > [!NOTE]
    > При удаленном использовании PowerShell может потребоваться разрешить взаимодействие через брандмауэр. Дополнительные информацию о портах, которые использует для ремотивирования PowerShell, см. в этой [теме.](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/)
    

