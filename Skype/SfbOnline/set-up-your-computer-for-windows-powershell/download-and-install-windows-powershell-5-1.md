---
title: Скачивание и установка Windows PowerShell 5.1
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
- LIL_Placement
description: Скачайте, установите и используйте Windows PowerShell 5.1, чтобы создать удаленный сеанс PowerShell, соединяющийся с приложением Skype для бизнеса Online.
ms.openlocfilehash: 2cbfa65f3170dd516e8bb46365ef663fd237d542
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612838"
---
# <a name="download-and-install-windows-powershell-51"></a>Скачивание и установка Windows PowerShell 5.1

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Если вы используете юбилейное обновление Windows 10 или Windows Server 2016, у вас уже должно быть приложение Windows PowerShell 5.1. Это обусловлено тем, что это приложение входит в состав этих операционных систем.
  
Чтобы узнать, какую версию Microsoft PowerShell вы используете, выполните следующие действия на компьютере под управлением ОС Windows 7, Windows Server 2008 R2 или Windows Server 2012:
  
1. В меню **Пуск** последовательно выберите пункты **Все программы**, **Стандартные**, **Windows PowerShell** и затем щелкните **Windows PowerShell**.
    
2. В консоли PowerShell введите следующую команду и нажмите клавишу ВВОД:
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. В окне консоли должны отобразиться примерно такие сведения:
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    Если возвращается номер версии 5.1, значит вы используете Windows PowerShell 5.1. В противном случае вам необходимо установить Windows PowerShell 5.1. Для этого можно скачать платформу Windows Management Framework 5.1, в состав которой входит среда Windows PowerShell 5.1, из [Центра загрузки Майкрософт](https://www.microsoft.com/download/details.aspx?id=54616).
  
Если вы убедились, что у вас установлена версия Windows PowerShell 5.1, необходимо проверить, настроена ли версия PowerShell для работы с удаленно исполняемыми сценариями. Для этого запустите приложение PowerShell от имени администратора. В ОС Windows 7, Windows Server 2008 R2, Windows Server 2012 или Windows Server 2012 R2 выполните следующие действия:
  
1. В меню **Пуск** последовательно выберите пункты **Все программы**, **Стандартные** и **Windows PowerShell**. Затем щелкните элемент **Windows PowerShell** правой кнопкой мыши и выберите **Запуск от имени администратора**.
    
2. Если появится диалоговое окно **Контроль учетных записей**, нажмите кнопку **Да**, чтобы разрешить запуск PowerShell с правами администратора.
    
В системе Windows 8 выполните указанные ниже действия.
  
1. Откройте панель чудо-кнопок и выберите **Поиск**, после чего щелкните правой кнопкой мыши элемент **Windows PowerShell**. Для быстрого доступа к панели чудо-кнопок на любом компьютере под управлением ОС Windows 8 (независимо от наличия сенсорного экрана) нажмите клавишу Windows и, не отпуская ее, клавишу C.
    
2. В панели инструментов внизу экрана выберите пункт **Запуск от имени администратора**.
    
3. Если появится диалоговое окно **Контроль учетных записей**, нажмите кнопку **Да**, чтобы разрешить запуск PowerShell с правами администратора.
    
После запуска PowerShell необходимо разрешить работу с удаленными сценариями в политике выполнения. Для этого в консоли PowerShell введите следующую команду и нажмите клавишу ВВОД:
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> При выполнении этой команды может появляться следующее сообщение об ошибке: > *Set-ExecutionPolicy: Доступ к разделу реестра "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell" запрещен.* Как правило, это сообщение выводится, если вы запустили PowerShell без прав администратора. Чтобы исправить эту ошибку, закройте сеанс PowerShell и запустите новый сеанс от имени администратора.
 
Чтобы проверить правильность настройки политики выполнения, в командной строке PowerShell введите следующую команду и нажмите клавишу ВВОД:
  
```PowerShell
Get-ExecutionPolicy
```

Если все настроено правильно, команда вернет следующее значение:
  
`RemoteSigned`

Если вы не используете Windows PowerShell 5.1, вам также необходимо скачать и установить платформу Windows Management Framework 5.1 из Центра загрузки Майкрософт. Этот пакет установки включает в себя Windows PowerShell 5.1 и Windows Remote Management (WinRM) 3.0. Его можно использовать, например, если вы работаете в ОС Windows 7 с пакетом обновления 1 (SP1) и еще не выполнили обновление до Windows PowerShell 5.1. В системах Windows Server 2016 и Windows 10 с юбилейным обновлением устанавливать приложение Windows PowerShell 5.1 обычно не требуется. Версия Windows PowerShell 5.1 входит в состав этих операционных систем.
  
Перед установкой Windows Management Framework 5.1 проверьте выполнение перечисленных ниже условий.
  
- Убедитесь, что вы скачали правильную версию пакета установки. Для 64-разрядной версии Windows 7 с пакетом обновления 1 (SP1) скачайте файл Win7AndW2K8R2-KB3191566-x64.ZIP. Для 32-разрядной версии Windows 7 необходимо скачать файл Win7-KB3191566-x86.ZIP.
    
- Для системы Windows 7 должен быть установлен пакет обновления 1.

Если вы не знаете свою версию Windows или не уверены, установлен ли у вас пакет обновления 1 для Windows 7, откройте меню **Пуск**, щелкните правой кнопкой мыши пункт **Компьютер** и выберите пункт **Свойства**. Нужная информация будет представлена в диалоговом окне "Система".
  
Чтобы установить Windows Management Framework 5.1, выполните процедуру из статьи [Установка и настройка WMF 5.1](/powershell/scripting/wmf/setup/install-configure).
  
После перезагрузки проверьте работоспособность Windows PowerShell и возможность запуска этого приложения от имени администратора. Для этого выполните следующие действия:
  
1. В меню **Пуск** последовательно выберите пункты **Все программы**, **Стандартные** и **Windows PowerShell**. Затем щелкните элемент **Windows PowerShell** правой кнопкой мыши и выберите **Запуск от имени администратора**.
    
2. Если появится диалоговое окно "Контроль учетных записей", нажмите кнопку **Да**, чтобы разрешить запуск PowerShell с правами администратора.
    
В появившейся консоли PowerShell необходимо убедиться, что служба WinRM запущена и правильно настроена. Для этого в командной строке PowerShell введите следующую команду и нажмите клавишу ВВОД:
  
```PowerShell
Get-Service winrm
```

На экране появятся сведения о службе WinRM:
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

Если в столбце состояния не указано, что служба WinRM запущена, запустите ее. Для этого введите следующую команду и нажмите клавишу ВВОД:
  
```PowerShell
Start-Service winrm
```

После запуска службы WinRM введите следующую команду, чтобы убедиться, что используется базовая проверка подлинности:
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

На экране появятся примерно следующие сведения:
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

Если настроена и применяется обычная проверка подлинности, вы можете использовать PowerShell для соединения с приложением Skype для бизнеса Online.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
