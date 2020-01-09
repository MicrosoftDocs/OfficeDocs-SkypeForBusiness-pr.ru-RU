---
title: Командная консоль Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Командная консоль управления Skype для бизнеса Server предоставляет интерфейс командной строки для администрирования и управления сервером. Она создана на основе Windows PowerShell и содержит полный набор командлетов управления и администрирования, которые относятся к Skype и старым серверным продуктам Lync.
ms.openlocfilehash: 4890194824caaea771d31e008d4546d871d0da8a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991594"
---
# <a name="skype-for-business-server-management-shell"></a>Командная консоль Skype для бизнеса Server
 
Командная консоль управления Skype для бизнеса Server предоставляет интерфейс командной строки для администрирования и управления сервером. Она создана на основе Windows PowerShell и содержит полный набор командлетов управления и администрирования, которые относятся к Skype и старым серверным продуктам Lync.
  
Windows PowerShell позволяет управлять приложениями Майкрософт из командной строки. Она включает среду командной строки, команды для определенного продукта и полный язык сценариев. Windows PowerShell впервые была представлена в качестве загружаемого выпуска для операционной системы Windows с опозданием в 2006 и была включена в интерфейс командной строки для управляемости сервера Microsoft Exchange Server 2007. Она была включена в большинство серверных продуктов Microsoft, включая Lync и серверы Skype, начиная с Lync Server 2010. В командной консоли Skype для бизнеса Server есть более 700 отдельных командлетов Lync и Skype.
  
> [!NOTE]
> Справочник по командлетам Skype для бизнеса перенесен на веб-сайт docs.microsoft.com. По представленным ниже ссылкам вы можете перейти на новую страницу портала docs.microsoft.com. Теперь весь контент предлагается с открытым исходным кодом и доступен в сообществе GitHub. Хотите принять участие в работе с ним? Ознакомьтесь с ФАЙЛОМ README в репозитории здесь:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
В Skype для бизнеса Server входит более 700 командлетов, позволяющих администраторам управлять Skype для бизнеса Server с помощью командной консоли Skype для бизнеса Server. Вы можете получить справку по командлету непосредственно в командной строке, введя следующую команду:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

Предыдущая команда получает полную справку, доступную для командлета **New-CsVoicePolicy**. Чтобы просмотреть справку для другого командлета, замените **New-CsVoicePolicy** на имя нужного командлета.
  
Чтобы получить полный список доступных командлетов для управления Skype для бизнеса Server, введите в командной строке оболочки следующую команду.  
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Что нужно знать о Windows PowerShell в Skype для бизнеса Server:
  
- Чтобы запустить командлеты Skype для бизнеса Server, откройте командную консоль управления "Skype для бизнеса".
    
    > [!CAUTION]
    > Если вы открыли окно Windows PowerShell вместо командной консоли Skype для бизнеса Server, по умолчанию вы не сможете запускать командлеты Skype. Чтобы запустить командлеты Skype для бизнеса Server в Windows PowerShell, сначала введите в командной строке Windows PowerShell следующее: >`Import-Module SkypeforBusiness`
  
- Консоль управления Skype для бизнеса Server автоматически устанавливается на каждый сервер переднего плана Skype для бизнеса Server Enterprise Edition или Standard Edition Server.
    
- Вы можете обновить содержимое справки командной консоли Skype для бизнеса Server, запустив командлет [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) . С помощью командлета Update-Help загружаются и устанавливаются самые новые файлы справки для всех модулей, установленных на компьютере, в том числе обновления командлетов Skype для бизнеса.
    
    По умолчанию командлет **Update-Help** обновит все модули, установленные на сервере Skype для бизнеса. Если требуется обновить лишь определенные модули, с помощью параметра _Module_ можно ограничить область применения данного командлета. В следующем примере обновляется только модуль Skype для бизнеса.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Если вам нужно обновить справку на серверах, не подключенных к Интернету, вы можете воспользоваться командлетом [Save-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) , чтобы получить последнюю версию справки и сохранить ее в указанном месте. Затем вы можете использовать командлет **Update-Help** с параметром _-SourcePath_ на серверах, не подключенных к Интернету, чтобы получить обновленную справку из выбранного местоположения. В следующем примере показано, как сохранить файлы справки в общем сетевом файле, а затем обновить справку для модуля Skype для бизнеса в общей папке.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Более подробную информацию можно найти в разделе [об обновляемой справке](https://technet.microsoft.com/library/hh847735.aspx).
    
    > [!NOTE]
    > Если вы используете PowerShell удаленно, вам может потребоваться разрешить связь через брандмауэр. Чтобы узнать больше о портах оболочки PowerShell, используемых удаленным взаимодействием, посмотрите, [какой порт используется в PowerShell](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    

