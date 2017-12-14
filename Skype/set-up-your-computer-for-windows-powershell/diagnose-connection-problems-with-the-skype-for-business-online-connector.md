---
title: "Диагностика проблем подключения с помощью соединителя Skype для бизнеса Online"
ms.author: tonysmit
author: tonysmit
ms.date: 5/17/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
description: "Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors."
---

# Диагностика проблем подключения с помощью соединителя Skype для бизнеса Online

Этот раздел содержит сведения, которые помогут диагностировать и устранить проблемы, возникающие при попытке создать удаленный сеанс Microsoft PowerShell для подключения к Skype для бизнеса online. Ознакомьтесь со следующими разделами:
  
- [Ошибка Import-Module, вызванная политикой выполнения Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_PowerShellExecutionPolicy)
    
- [Ошибка Import-Module, вызванная неправильной версией Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_IncorrectVersion)
    
- [Не удалось подключиться к серверу Live ID](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_FailedConnect)
    
- [Не удалось загрузить модуль Live ID](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_FailedLoad)
    
- [Произошел сбой входа для пользователя](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_LogonFailed)
    
- [У пользователя нет разрешения на управление этим клиентом](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_UserPermission)
    
- [Возможность подключения к клиенту отключена в Skype для бизнеса Online](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_AbilityConnect)
    
- [Превышено максимальное число параллельных оболочек для этого пользователя в Skype для бизнеса Online ](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsUser)
    
- [Превышено максимальное число параллельных оболочек для этого клиента в Skype для бизнеса Online ](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## Ошибка Import-Module, вызванная политикой выполнения Windows PowerShell
<a name="BKMK_PowerShellExecutionPolicy"> </a>

Политика выполнения PowerShell помогает определить, какие файлы конфигурации можно загрузить в консоль PowerShell и какие сценарии пользователь может запустить из этой консоли. Как минимум Модуль соединителя Skype для бизнеса Online невозможно импортировать, если политика выполнения имеет значение RemoteSigned. Если это не так, вы получите следующее сообщение об ошибке при попытке импортировать модуль:
  
```
Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
```

Чтобы устранить эту проблему, запустите PowerShell от имени администратора, а затем выполните следующую команду:
  
```
Set-ExecutionPolicy RemoteSigned
```

Сведения о политике выполнения см. в разделе [Сведения о политиках выполнения](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## Ошибка Import-Module, вызванная неправильной версией Windows PowerShell
<a name="BKMK_IncorrectVersion"> </a>

Модуль соединителя Skype для бизнеса Online можно запускать только в Windows PowerShell 3.0. Если вы попытаетесь импортировать модуль в предыдущей версии PowerShell, произойдет сбой импорта с сообщением об ошибке, аналогичным следующему:
  
```
Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.
```

Единственный способ исправить эту проблему  установить Windows PowerShell 3.0, используя Центр загрузки Майкрософт по ссылке [http://www.microsoft.com/ru-ru/download/details.aspx?id=29939](http://www.microsoft.com/en-us/download/details.aspx?id=29939).
  
## Не удалось подключиться к серверу Live ID
<a name="BKMK_FailedConnect"> </a>

Обычно три причины могут вызвать сбой подключения со следующим сообщением об ошибке:
  
```
Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.
```

Часто эта ошибка значит, что Помощник по входу в Microsoft Online Services не работает. Вы можете проверить состояние этой службы, запустив следующую команду из командной строки PowerShell:
  
```
Get-Service "msoidsvc"
```

Если служба не запущена, запустите ее с помощью следующей команды:
  
```
Start-Service "msoidsvc"
```

Если служба запущена, возможно, возникли проблемы с сетевым подключением между компьютером и сервером проверки подлинности Microsoft Live ID. Чтобы проверить это, откройте Internet Explorer и перейдите по ссылке [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Попробуйте войти в Office 365 отсюда. Если это сделать не удастся, возможно, возникли проблемы с сетевым подключением.
  
В более редких случаях может быть задано неправильное значение URI подключения для сервера проверки подлинности Microsoft Live ID. Возможно, проблема в этом, если вы уже определили, что помощник по входу запущен, и у вас не возникают проблемы с сетевым подключением. В таком случае обратитесь в службу поддержки Office 365.
  
## Не удалось загрузить модуль Live ID
<a name="BKMK_FailedLoad"> </a>

Одно из необходимых требований, чтобы использовать PowerShell для управления Skype для бизнеса online,  установить Помощник по входу в Microsoft Online Services. Если помощник по входу не установлен, вы получите следующее сообщение об ошибке при попытке создать удаленный сеанс с Skype для бизнеса online:
  
```
Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.
```

Помощник по входу в Microsoft Online Services доступен в Центр загрузки Майкрософт по ссылке [Помощник по входу в службы Microsoft Online Services для ИТ-специалистов, RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177).
  
## Произошел сбой входа для пользователя
<a name="BKMK_LogonFailed"> </a>

При попытке установить удаленное подключение к Skype для бизнеса online нужно предоставить имя пользователя и пароль допустимой учетной записи пользователя Skype для бизнеса online. Если вы этого не сделаете, произойдет сбой при входе с сообщением об ошибке, аналогичным следующему:
  
```
Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.
```

Если вы считаете, что используете допустимую учетную запись пользователя и указали правильный пароль, попробуйте войти снова. При сбое используйте те же учетные данные и попробуйте войти на сайте [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Если там не удастся войти, обратитесь в службу поддержки Office 365.
  
## У пользователя нет разрешения на управление этим клиентом
<a name="BKMK_UserPermission"> </a>

Невозможно установить удаленное подключение PowerShell к Skype для бизнеса online, если вы не являетесь участником группы "Администраторы клиента", так как в этом случае произойдет сбой подключения и вы получите следующее сообщение об ошибке:
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the about_Remote_Troubleshooting Help topic.
```

Если вы считаете, что являетесь членом группы "Администраторы клиента" или должны быть в ней, обратитесь в службу поддержки Office 365.
  
## Возможность подключения к клиенту отключена в Skype для бизнеса Online
<a name="BKMK_AbilityConnect"> </a>

Чтобы использовать PowerShell для управления Skype для бизнеса online, для свойства EnableRemotePowerShellAccess политики клиента PowerShell нужно задать значение  `True`. Если оно не задано, произойдет сбой подключения и вы получите следующее сообщение об ошибке:
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

Если вы увидите это сообщение об ошибке, потребуется обратиться в службу поддержки Office 365 и включить удаленный доступ PowerShell.
  
## Превышено максимальное число параллельных оболочек для этого пользователя в Skype для бизнеса Online
<a name="BKMK_MaxNumberShellsUser"> </a>

Каждый администратор может установить максимум три удаленных подключения к Skype для бизнеса online одновременно. Если у вас установлено три удаленных подключения PowerShell, при попытке четвертого подключения произойдет сбой со следующим сообщением об ошибке:
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the about_Remote_Troubleshooting Help topic.
```

Единственный способ устранить эту проблему  закрыть одно или несколько из предыдущих подключений. По окончании работы с Skype для бизнеса online рекомендуется использовать командлет **Remove-PSSession**, чтобы завершить сеанс. Это поможет предотвратить проблему.
  
## Превышено максимальное число параллельных оболочек для этого клиента в Skype для бизнеса Online
<a name="BKMK_MaxNumberShellsTenant"> </a>

Хотя у каждого администратора может быть до трех одновременных подключений к клиенту Skype для бизнеса online, одному клиенту запрещено иметь больше девяти одновременных подключений. Например, три администратора могут открыть по три сеанса. Если четвертый администратор попытается установить подключение (10-е по счету), произойдет сбой со следующим сообщением об ошибке:
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

Единственный способ устранить эту проблему  закрыть одно или несколько из предыдущих подключений. По окончании работы с Skype для бизнеса online рекомендуется использовать командлет **Remove-PSSession**, чтобы завершить сеанс. Это поможет предотвратить проблему.
  

