---
title: Командная консоль Skype для бизнеса Server
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
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Командная Skype для бизнеса Server Командная оболочка предоставляет интерфейс командной строки для администрирования и управления серверами. Он построен на Windows PowerShell и включает полный набор команды управления и администрирования, которые специфичен для Skype и устаревших продуктов сервера Lync.
ms.openlocfilehash: 3b9ea4658e7745bb1e6bd330c5dd865bf45a396a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857506"
---
# <a name="skype-for-business-server-management-shell"></a>Командная консоль Skype для бизнеса Server
 
Командная Skype для бизнеса Server Командная оболочка предоставляет интерфейс командной строки для администрирования и управления серверами. Он построен на Windows PowerShell и включает полный набор команды управления и администрирования, которые специфичен для Skype и устаревших продуктов сервера Lync.
  
Windows PowerShell позволяет управлять приложениями Майкрософт из командной строки. Оно предоставляет среду командной строки, команды для определенных продуктов и полноценный язык скриптов. Windows PowerShell был впервые представлен в качестве загружаемого выпуска для операционной системы Windows в конце 2006 г. и был включен в качестве интерфейса командной строки для управляемости Microsoft Exchange Server 2007 г. Она была включена в большинство продуктов Microsoft Server, включая Lync и Skype серверов, начиная с Lync Server 2010. В оболочке управления Skype Skype для бизнеса Server более 700 Skype Lync.
  
> [!NOTE]
> Skype для бизнеса ссылки на cmdlet перенесены в docs.microsoft.com. Щелкнув ссылки ниже, вы сможете найти новую страницу docs.microsoft.com. Теперь контент открыт и доступен для взносов сообщества через GitHub. Заинтересованы в содействии? Ознакомьтесь с README в репо здесь: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype для бизнеса Server с более чем 700 cmdlets, которые позволяют администраторам управлять Skype для бизнеса Server с помощью Skype для бизнеса Server оболочки управления. Вы можете получить справку для командлета непосредственно из командной строки, введя команду, аналогичную следующей:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

В предыдущей команде извлекается полная справка, доступная для **командлета New-CsVoicePolicy.** Чтобы просмотреть справку для другого cmdlet, замените **New-CsVoicePolicy** именем cmdlet, для которого требуется получить справку.
  
Чтобы получить полный список командлетов, доступных для управления Skype для бизнеса Server, введите следующее в командной подсказке оболочки: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Что нужно знать о Windows PowerShell в Skype для бизнеса Server:
  
- Чтобы запустить Skype для бизнеса Server, откройте Skype для бизнеса Server управленческой оболочки.
    
    > [!CAUTION]
    > Если вы откроете Windows PowerShell, а не Skype для бизнеса Server, по умолчанию вы не сможете запустить Skype. Чтобы запустить Skype для бизнеса Server командлеты из Windows PowerShell, сначала введите следующее в командной Windows PowerShell: >`Import-Module SkypeforBusiness`
  
- Skype для бизнеса Server Оболочка управления автоматически устанавливается на каждый сервер Skype для бизнеса Server выпуск Enterprise или выпуск Standard сервере.
    
- Вы можете обновить содержимое справки Skype для бизнеса Server с помощью команды [Update-Help.](/powershell/module/microsoft.powershell.core/update-help) Командлет Update-Help и устанавливает самые новые файлы справки, доступные для всех модулей, установленных на компьютере, включая обновления Skype для бизнеса командлетов.
    
    По умолчанию командлет **Update-Help** обновляет все модули, установленные на Skype для бизнеса Server. Если требуется обновить только определенные модули, можно использовать параметр _Module,_ чтобы ограничить область действия командлета. В следующем примере обновляется только Skype для бизнеса модуль.
    
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
