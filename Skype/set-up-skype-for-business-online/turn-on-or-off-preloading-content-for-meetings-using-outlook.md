---
title: "Включение и выключение разрешения предварительной загрузки содержимого для собраний с помощью Outlook"
ms.author: tonysmit
author: tonysmit
ms.date: 11/17/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: d217d422-f7e9-433d-ad24-bf41751f65ca
description: "See how to turn preloaded content on or off for Skype for Business meetings using files or attachments on an Outlook meeting invitation. "
---

# Включение и выключение разрешения предварительной загрузки содержимого для собраний с помощью Outlook

Пользователи могут заранее загружать содержимое, файлы или вложения из приглашения на собрание Outlook в Skype для бизнеса Online. Вы можете включить или отключить эту функцию. Эта функция включена для всех организацией, которые используют Skype для бизнеса Online. См. статью [Предварительная загрузка вложений для собрания Skype для бизнеса](https://support.office.com/article/fd3d9f9d-b448-4754-b813-02e49393f251).
  
> [!NOTE]
> В настоящее время в Skype для бизнеса Online нет командлетов, с помощью которых можно настроить или просматривать в сети значения для параметров  _MaxContentStorageMB_ и _MaxUploadFileMB_. Они доступны только для локальных развертываний. Важно помнить, что содержимое не будет отправлено в собрание, если размер вложения превышает  _MaxUploadFileSizeMB_ или если достигнуто пороговое значение для _MaxContentStorageMB_. > 
  
## Чтобы начать работу, можно сделать следующее

### 

 **Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**
  
1. Чтобы проверить, установлена ли у вас версия 3.0 или более поздняя, в меню **Пуск** выберите пункт **Windows PowerShell**.
    
2. Проверьте версию, введя в окне **Windows PowerShell** команду _Get-Host_.
    
3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.
    
4. Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.
    
Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
  
### 

 **Запуск сеанса Windows PowerShell**
  
1. В меню **Пуск** выберите пункт **Windows PowerShell**.
    
2. В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:
    
    > [!NOTE]
    > Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.
  
> 
  ```
  Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```

> 
  ```
  $credential = Get-Credential
  ```

> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```

> 
  ```
  Import-PSSession $session
  ```

Дополнительные сведения о запуске Windows PowerShell см. в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) или[Подключение к Skype для бизнеса с использованием Windows PowerShell](https://technet.microsoft.com/library/dn362795%28v=ocs.15%29.aspx).
  
## Включение и выключение функции

Возможность предварительно загружать вложение из приглашения Outlook на собрание Skype для бизнеса Online по умолчанию включена, но может потребоваться запретить пользователям из организации заранее загружать содержимое.
  
> [!IMPORTANT]
> Этот параметр можно включить или отключить только для всей организации, невозможно управлять им для отдельных пользователей. 
  
 **Чтобы отключить функцию, откройте Windows PowerShell и выполните следующие действия:**
  
```
Grant-CsGraphPolicy -PolicyName GraphDisabled 
```

 **Чтобы снова включить функцию, откройте Windows PowerShell и выполните следующие действия:**
  
```
Grant-CsGraphPolicy -PolicyName GraphEnabled 
```

## Хотите узнать больше о Windows PowerShell?

- Windows PowerShell, дает возможность управлять пользователями, предоставляя им права на определенные действия. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    

