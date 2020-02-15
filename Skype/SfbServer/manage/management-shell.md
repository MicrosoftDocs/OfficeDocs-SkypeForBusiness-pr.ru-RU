---
title: Командная консоль Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Консоль управления Skype для бизнеса Server предоставляет интерфейс командной строки для администрирования и управления сервером. Он создан на основе Windows PowerShell и содержит полный набор командлетов управления и администрирования, характерных для Skype и устаревших продуктов Lync Server.
ms.openlocfilehash: 085c8f4a8a454f97dc4fbc640a6f5c8a70baec31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044261"
---
# <a name="skype-for-business-server-management-shell"></a>Командная консоль Skype для бизнеса Server
 
Консоль управления Skype для бизнеса Server предоставляет интерфейс командной строки для администрирования и управления сервером. Он создан на основе Windows PowerShell и содержит полный набор командлетов управления и администрирования, характерных для Skype и устаревших продуктов Lync Server.
  
Windows PowerShell позволяет управлять приложениями Майкрософт из командной строки. Оно предоставляет среду командной строки, команды для определенных продуктов и полноценный язык скриптов. Windows PowerShell впервые появился в качестве загружаемого выпуска для операционной системы Windows с опозданием в 2006 и был включен в качестве интерфейса командной строки для управления Microsoft Exchange Server 2007. Она включена в большинство серверных продуктов Майкрософт, в том числе серверы Lync и Skype, начиная с Lync Server 2010. В командной консоли Skype для бизнеса Server есть более 700 доступных командлетов Lync и Skype.
  
> [!NOTE]
> Ссылка на командлет Skype для бизнеса перемещена в docs.microsoft.com. Перейдя по приведенным ниже ссылкам, вы перейдете на новую страницу docs.microsoft.com. Теперь контент открыт в исходном и доступном для участия в сообществах с помощью GitHub. Интересуетесь участниками? Ознакомьтесь со статьей README в репозитории здесь:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype для бизнеса Server поставляется с более чем 700 командлетами, которые позволяют администраторам управлять Skype для бизнеса Server с помощью командной консоли Skype для бизнеса Server. Чтобы получить справку по командлету непосредственно из командной строки, введите следующую команду:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

Предыдущая команда получает полную справку, доступную для командлета **New – CsVoicePolicy** . Для просмотра справки по другому командлету замените **New-CsVoicePolicy** на имя командлета, для которого требуется получить справку.
  
Чтобы получить полный список доступных командлетов для управления Skype для бизнеса Server, введите в командной строке командной консоли следующую команду: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Сведения о Windows PowerShell в Skype для бизнеса Server:
  
- Чтобы запустить командлеты Skype для бизнеса Server, откройте консоль управления Skype для бизнеса Server.
    
    > [!CAUTION]
    > Если открыть окно Windows PowerShell, а не командную консоль Skype для бизнеса Server, по умолчанию командлеты Skype могут оказаться недоступными. Чтобы запустить командлеты Skype для бизнеса Server в Windows PowerShell, сначала введите в командной строку Windows PowerShell следующую команду: >`Import-Module SkypeforBusiness`
  
- Консоль управления Skype для бизнеса Server автоматически устанавливается на каждом сервере переднего плана Skype для бизнеса Server Enterprise Edition или на сервере Standard Edition.
    
- Вы можете обновить контент справки по командной консоли Skype для бизнеса Server, выполнив командлет [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) . Командлет Update-Help загружает и устанавливает последние файлы справки, доступные для всех установленных на компьютере модулей, в том числе обновлений командлетов Skype для бизнеса.
    
    По умолчанию командлет **Update-Help** обновит все модули, установленные на сервере Skype для бизнеса. Если необходимо обновить только определенные модули, можно использовать параметр _module_ , чтобы ограничить область действия командлета. В следующем примере обновляется только модуль Skype для бизнеса.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Если вам нужно обновить справку на серверах, которые не подключены к Интернету, вы можете использовать командлет [Save — Help](https://technet.microsoft.com/library/hh849724.aspx) , чтобы получить последнюю версию справки и сохранить ее в указанном расположении. Затем можно использовать командлет **Update – Help** с параметром _– SourcePath_ на серверах, не подключенных к Интернету, чтобы получить обновленную справку из выбранного расположения. В приведенном ниже примере показано, как сохранить файлы справки в сетевую общую папку, а затем обновить справку для модуля Skype для бизнеса из общей папки.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Более подробную информацию можно узнать в статье [сведения об обновляемой справке](https://technet.microsoft.com/library/hh847735.aspx).
    
    > [!NOTE]
    > Если вы используете PowerShell удаленно, вам может потребоваться разрешить связь через брандмауэр. Чтобы узнать больше о портах PowerShell, используемых удаленным взаимодействием PowerShell, посмотрите, [какой порт использует удаленное взаимодействие PowerShell?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    

