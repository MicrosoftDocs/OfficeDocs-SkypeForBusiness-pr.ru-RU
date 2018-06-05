---
title: Командная консоль Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: Скайп для консоли Business Server содержит интерфейс командной строки для администрирования и управления сервером. Создан на основе Windows PowerShell, а также полный набор командлетов управления и администрирования, относящиеся к Скайп и прежних версий продуктов Lync server.
ms.openlocfilehash: e1c954c75f03be7e7603866c4bb58d5927f2c3f8
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569374"
---
# <a name="skype-for-business-server-2015-management-shell"></a>Командная консоль Skype для бизнеса Server 2015
 
Скайп для консоли Business Server содержит интерфейс командной строки для администрирования и управления сервером. Создан на основе Windows PowerShell, а также полный набор командлетов управления и администрирования, относящиеся к Скайп и прежних версий продуктов Lync server.
  
Windows PowerShell позволяет управлять приложениями корпорации Майкрософт с помощью командной строки. Содержит среды командной строки, команды конкретного продукта и полный языка сценариев. Windows PowerShell была впервые введена как загружаемая версия для операционной системы Windows позднее в 2006 г. и был включены как интерфейс командной строки для управления Microsoft Exchange Server 2007. Он был включен в большинство серверных продуктов Майкрософт, включая Lync и Скайп серверы, Приступая к работе с Lync Server 2010. Около 700 определенные командлеты Lync и Скайп доступны в Скайп для консоли Business Server.
  
> [!NOTE]
> Справочник по командлетам Skype для бизнеса перенесен на веб-сайт docs.microsoft.com. По представленным ниже ссылкам вы можете перейти на новую страницу портала docs.microsoft.com. Теперь весь контент предлагается с открытым исходным кодом и доступен в сообществе GitHub. Хотите принять участие в работе с ним? Извлечение сведений в repo здесь:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Скайп для Business Server 2015 поставляется с более чем 700 командлетов, которые позволяют администраторам управлять Скайп для Business Server, с помощью Скайп для консоли Business Server. Вы можете получить справку по командлету непосредственно в командной строке, введя следующую команду:
  
```
Get-Help New-CsVoicePolicy -Full
```

Предыдущая команда извлекает всю справку, доступные для командлета **New-CsVoicePolicy** . Чтобы просмотреть справку для разных командлета, замените **New-CsVoicePolicy** с именем командлета, для которого требуется получить справку.
  
Чтобы получить полный список доступных командлетов для управления Skype для бизнеса Server, введите в командной строке оболочки следующую команду.  
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Что нужно знать о Windows PowerShell в Скайп для Business Server:
  
- Чтобы запустить Скайп по командлетам Business Server, откройте Скайп для консоли Business Server.
    
    > [!CAUTION]
    > При открытии окна Windows PowerShell, а не Скайп для консоли Business Server по умолчанию не можно для запуска командлетов Скайп. Чтобы запустить Скайп по командлетам Business Server из в Windows PowerShell, сначала введите следующее в командной строке Windows PowerShell: >`Import-Module SkypeforBusiness`
  
- Скайп для консоли Business Server автоматически устанавливается на каждом Скайп для Business Server Enterprise Edition сервера переднего плана или сервере Standard Edition.
    
- Скайп для содержимого справки консоли Business Server можно обновить с помощью командлета [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) . Командлет Update-Help загружает и устанавливает новые файлы справки доступны для всех модулей, установленный на компьютере, включая обновления Скайп для бизнеса командлетов.
    
    По умолчанию командлет **Update-Help** приведут к обновлению всех модулей, установленные на ваш Скайп для Business Server. Если вы хотите обновить только определенные модули, параметр _модуль_ можно использовать для ограничения области командлета. В следующем примере обновляются только Скайп для бизнес-модуля.
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    Если вам потребуется обновить справки на серверах, не подключенные к Интернету, командлет [Сохранить справки](https://technet.microsoft.com/en-us/library/hh849724.aspx) для получения последней версии справки и сохраните его в папку, в которой указан. Затем можно использовать командлет **Update-Help** с параметром _- SourcePath_ на серверах, не подключенных к Интернету для получения обновленной справки с выбранной папке. Следующем примере показано, как сохранить файлы справки в сетевую общую папку, а затем обновить справку по Скайп для бизнес-модуля из общей папки.
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Для получения дополнительных сведений см [о обновляемым](https://technet.microsoft.com/library/hh847735.aspx).
    

