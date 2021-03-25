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
description: Командная оболочка Skype для бизнес-серверов предоставляет интерфейс командной строки для администрирования и управления серверами. Он построен на Windows PowerShell и включает полный набор команды управления и администрирования, которые специфичен для продуктов Skype и устаревших серверов Lync.
ms.openlocfilehash: 24da9ac341129239399ea17218be8547f3549d6f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118588"
---
# <a name="skype-for-business-server-management-shell"></a>Командная консоль Skype для бизнеса Server
 
Командная оболочка Skype для бизнес-серверов предоставляет интерфейс командной строки для администрирования и управления серверами. Он построен на Windows PowerShell и включает полный набор команды управления и администрирования, которые специфичен для продуктов Skype и устаревших серверов Lync.
  
Windows PowerShell позволяет управлять приложениями Майкрософт из командной строки. Оно предоставляет среду командной строки, команды для определенных продуктов и полноценный язык скриптов. Windows PowerShell была впервые представлена в качестве загружаемого выпуска для операционной системы Windows в конце 2006 г. и была включена в качестве интерфейса командной строки для управляемости Microsoft Exchange Server 2007 г. Он был включен в большинство продуктов Microsoft Server, включая серверы Lync и Skype, начиная с Lync Server 2010. В оболочке управления Skype для бизнеса серверов доступно более 700 lync и skype.
  
> [!NOTE]
> Ссылки на веб-кодлет Skype для бизнеса перенесены в docs.microsoft.com. Щелкнув ссылки ниже, вы сможете найти новую страницу docs.microsoft.com. Теперь контент открыт и доступен для взносов сообщества через GitHub. Заинтересованы в содействии? Ознакомьтесь с README в репо здесь: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype для бизнеса Server использует более 700 смдлетов, которые позволяют администраторам управлять Skype для бизнеса Server с помощью оболочки управления Skype для бизнес-серверов. Вы можете получить справку для командлета непосредственно из командной строки, введя команду, аналогичную следующей:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

В предыдущей команде извлекается полная справка, доступная для **командлета New-CsVoicePolicy.** Чтобы просмотреть справку для другого cmdlet, замените **New-CsVoicePolicy** именем cmdlet, для которого требуется получить справку.
  
Чтобы получить полный список командлетов, доступных для управления Skype для бизнеса Server, введите в командной подсказке оболочки следующее: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Что нужно знать о Windows PowerShell Skype для бизнеса Server:
  
- Чтобы запустить команды Skype для бизнеса Server, откройте оболочку управления Skype для бизнес-серверов.
    
    > [!CAUTION]
    > Если вы откроете Windows PowerShell, а не оболочку управления skype для бизнес-серверов, по умолчанию вы не сможете запустить команды Skype. Чтобы запустить командлеты Skype для бизнеса Server из Windows PowerShell, сначала введите следующее в командной Windows PowerShell: >  `Import-Module SkypeforBusiness`
  
- Оболочка управления Skype для бизнес-серверов автоматически устанавливается на каждом сервере skype для бизнеса Server Enterprise Edition front End Server или Standard Edition.
    
- Вы можете обновить содержимое справки по управлению Skype для бизнес-серверов с помощью команды [Update-Help.](/powershell/module/microsoft.powershell.core/update-help) Командлет Update-Help и устанавливает самые новые файлы справки, доступные для всех модулей, установленных на компьютере, включая обновления командлетов Skype для бизнеса.
    
    По умолчанию командлет **Update-Help** обновляет все модули, установленные на сервере Skype для бизнеса. Если требуется обновить только определенные модули, можно использовать параметр _Module,_ чтобы ограничить область действия командлета. В следующем примере обновляется только модуль Skype для бизнеса.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Если вам необходимо обновить справку на серверах, не подключенных к Интернету, вы можете использовать комлет [Save-Help,](/powershell/module/microsoft.powershell.core/save-help) чтобы получить последнюю версию справки и сохранить ее в нужном месте. Затем можно использовать комлет **Update-Help** с параметром _-SourcePath_ на серверах, не подключенных к Интернету, чтобы получить обновленную справку из выбранного вами расположения. В следующем примере показано, как сохранить файлы справки в сетевой файл, а затем обновить справку для модуля Skype для бизнеса из файла.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Дополнительные сведения см. в [справке "Updatable Help".](/powershell/module/microsoft.powershell.core/about/about_updatable_help)
    
    > [!NOTE]
    > Если вы используете PowerShell удаленно, возможно, потребуется разрешить связь через брандмауэр. Дополнительные данные об использовании повторного использования портов PowerShell см. в этой [ссылке.](/archive/blogs/christwe/what-port-does-powershell-remoting-use)
