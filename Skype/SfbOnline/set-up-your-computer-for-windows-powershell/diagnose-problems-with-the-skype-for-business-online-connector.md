---
title: Диагностика проблем подключения с помощью соединителя Skype для бизнеса Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
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
description: Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors.
ms.openlocfilehash: c2092da0324a147b182ce7715e757f1ed039aa65
ms.sourcegitcommit: 1ac37cc27d4ccb3e1dae20ca1929214e17be2075
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/07/2022
ms.locfileid: "65913397"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Диагностика проблем подключения с помощью соединителя Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[] Этот раздел содержит сведения, которые помогут диагностировать и устранить проблемы, возникающие при попытке создать удаленный сеанс Microsoft PowerShell для подключения к Skype для бизнеса online. Ознакомьтесь со следующими разделами:
  
- [Ошибка Import-Module, вызванная политикой выполнения Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Ошибка Import-Module, вызванная неправильной версией Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Современная проверка подлинности завершается сбоем, если проверка подлинности WinRM Basic отключена](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Не удалось подключиться к серверу Live ID](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
      
- [Сбой входа для пользователя](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [У пользователя нет разрешения на управление этим клиентом](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Возможность подключения к клиенту отключена в Skype для бизнеса Online](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Превышено максимальное количество одновременных оболочк для этого пользователя в Skype для бизнеса Online.](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Превышено максимальное количество одновременных оболочк для этого клиента в Skype для бизнеса Online.](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Ошибка Import-Module, вызванная политикой выполнения Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

Политика выполнения PowerShell помогает определить, какие файлы конфигурации можно загрузить в консоль PowerShell и какие сценарии пользователь может запустить из этой консоли. Как минимум Модуль соединителя Skype для бизнеса Online невозможно импортировать, если политика выполнения имеет значение RemoteSigned. Если это не так, вы получите следующее сообщение об ошибке при попытке импортировать модуль:
  
- Ошибка: <em>Import-Module: File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. Дополнительные сведения см. в about_Execution_Policies .https://go.microsoft.com/fwlink/?LinkID=135170</em>

- **Разрешение** Чтобы устранить эту проблему, запустите PowerShell от имени администратора и выполните следующую команду:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Сведения о политике выполнения см. в разделе [Сведения о политиках выполнения](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Ошибка Import-Module, вызванная неправильной версией Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Модуль соединителя Skype для бизнеса Online можно запускать только в Windows PowerShell 3.0. При попытке импортировать модуль в предыдущей версии PowerShell процесс импорта завершится ошибкой с сообщением об ошибке следующего типа:
  
  - **Ошибка**: *Import-Module: версия загруженного PowerShell — "2.0". Для выполнения модуля "Общие файлы D:\\Program Files\\\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1" требуется минимальная версия PowerShell 3.0. Проверьте установку PowerShell и повторите попытку.*

- **Решение**. Единственный способ устранить эту проблему — установить Windows PowerShell 3.0, доступную в Центре загрузки Майкрософт по [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595)адресу .
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>Современная проверка подлинности завершается сбоем, если проверка подлинности WinRM Basic отключена
<a name="BKMKWinRMBasicAuth"> </a>

Последняя версия модуля соединителя Skype для бизнеса Online использует современную проверку подлинности, но базовый клиент Удаленного управления Windows (WinRM) должен быть настроен для разрешения обычной проверки подлинности.  Современная проверка подлинности использует маркеры носителя, которые обычно передаются в *заголовке Authorization: Bearer* . Windows PowerShell, на основе которого создается Skype для бизнеса PowerShell, не позволяет манипулировать этим заголовком.  Вместо этого Skype для бизнеса PowerShell использует заголовок *Authorization: Basic* для передачи маркера носителя.

[Инструкции по включению](./download-and-install-windows-powershell-5-1.md) проверки подлинности WinRM для обычной проверки подлинности см. в статье "Загрузка и установка Windows PowerShell".

## <a name="failed-to-connect-to-live-id-server"></a>Не удалось подключиться к серверу Live ID
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> Аутентификация с динамическим идентификатором устарела для skype для бизнеса Online Connector. Используйте модуль Teams PowerShell для управления сетевым клиентом. При управлении гибридными средами выполните обновление до последнего накопительного пакета обновления или используйте проверку подлинности oAuth.

Обычно три причины могут вызвать сбой подключения со следующим сообщением об ошибке:

  - **Ошибка***: Get-CsWebTicket: не удалось подключить серверы динамических идентификаторов. Убедитесь, что прокси-сервер включен или компьютер подключен к серверам динамических идентификаторов.*

- **Решение**. Часто эта ошибка означает, что помощник по входу в Microsoft Online Services не запущен. Вы можете проверить состояние этой службы, запустив следующую команду из командной строки PowerShell: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Если служба не запущена, запустите ее с помощью следующей команды:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Если служба запущена, возможно, возникли проблемы с сетевым подключением между компьютером и сервером проверки подлинности Microsoft Live ID. Чтобы проверить это, откройте Internet Explorer и перейдите по ссылке [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Попробуйте войти в Microsoft 365 или Office 365. Если это сделать не удастся, возможно, возникли проблемы с сетевым подключением.
  
    В более редких случаях может быть задано неправильное значение URI подключения для сервера проверки подлинности Microsoft Live ID. Возможно, проблема в этом, если вы уже определили, что помощник по входу запущен, и у вас не возникают проблемы с сетевым подключением. В этом случае обратитесь в службу поддержки Майкрософт.
  
## <a name="logon-failed-for-the-user"></a>Произошел сбой входа для пользователя
<a name="BKMKLogonFailed"> </a>

При попытке установить удаленное подключение к Skype для бизнеса online нужно предоставить имя пользователя и пароль допустимой учетной записи пользователя Skype для бизнеса online. В противном случае вход завершится сбоем вместе с сообщением об ошибке, как показано в следующем сообщении:

- **Ошибка**: *Get-CsWebTicket: не удалось выполнить вход для пользователя "kenmyer@litwareinc.com". Создайте новый объект PSCredential,* чтобы убедиться, что вы использовали правильное имя пользователя и пароль.

- **Решение**. Если вы считаете, что используете допустимую учетную запись пользователя и у вас правильный пароль, попробуйте снова войти в систему. Если это не удается, используйте те же учетные данные и попробуйте войти в систему [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Если вы не можете войти в систему, обратитесь в службу поддержки Майкрософт. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>У пользователя нет разрешения на управление этим клиентом
<a name="BKMKUserPermission"> </a>

Невозможно установить удаленное подключение PowerShell к Skype для бизнеса online, если вы не являетесь участником группы "Администраторы клиента", так как в этом случае произойдет сбой подключения и вы получите следующее сообщение об ошибке:

- Ошибка: *New-PSSession : [admin.vdomain.com] Сбой обработки данных с удаленного сервера admin.vdomain.com со следующим сообщением об ошибке: у пользователя user@foo.com нет разрешения на управление этим клиентом. Разрешения можно предоставить, назначив пользователю соответствующую роль RBAC. Дополнительные сведения см. в разделе "[Удаленное устранение неполадок"](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Решение**. Если вы считаете, что входите в группу "Администраторы клиента", обратитесь в службу поддержки Майкрософт.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Возможность подключения к клиенту отключена в Skype для бизнеса Online
<a name="BKMKAbilityConnect"> </a>

Чтобы использовать PowerShell для управления Skype для бизнеса online, для свойства EnableRemotePowerShellAccess политики клиента PowerShell нужно задать значение  `True`. Если оно не задано, произойдет сбой подключения и вы получите следующее сообщение об ошибке:

- Ошибка: *New-PSSession : [admin.vdomain.com] Обработка данных с удаленного сервера admin.vdomain.com со следующим сообщением об ошибке: возможность подключения к этому клиенту с помощью удаленного сеанса PowerShell отключена. Обратитесь в службу поддержки Lync, чтобы проверить политику PowerShell клиента этого клиента. Дополнительные сведения см. в разделе "[Удаленное устранение неполадок"](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Решение**. Если вы видите это сообщение об ошибке, необходимо обратиться в службу поддержки Майкрософт и включить удаленный доступ PowerShell.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Превышено максимальное число параллельных оболочек для этого пользователя в Skype для бизнеса Online
<a name="BKMKMaxNumberShellsUser"> </a>

Каждый администратор может установить максимум три удаленных подключения к Skype для бизнеса online одновременно. Если у вас установлено три удаленных подключения PowerShell, при попытке четвертого подключения произойдет сбой со следующим сообщением об ошибке: 

- Ошибка: *New-PSSession : [admin.vdomain.com] Не удалось подключиться к удаленному серверу admin.vdomain.com со следующим сообщением об ошибке: служба WS-Management не может обработать запрос. Превышено максимальное количество одновременных оболочк для этого пользователя. Закройте существующие оболочки или создайте квоту для этого пользователя. Дополнительные сведения см. в разделе "[Удаленное устранение неполадок"](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Решение**. Единственный способ устранить эту проблему — закрыть одно или несколько предыдущих подключений. По окончании работы с Skype для бизнеса online рекомендуется использовать командлет **Remove-PSSession**, чтобы завершить сеанс. Это поможет предотвратить проблему.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Превышено максимальное число параллельных оболочек для этого клиента в Skype для бизнеса Online
<a name="BKMKMaxNumberShellsTenant"> </a>

Хотя каждому администратору разрешено иметь до трех одновременных подключений к клиенту Skype для бизнеса Online, ни одному клиенту не разрешено иметь более 20 одновременных подключений. Например, у шести администраторов может быть три открытых сеанса. Если четвертый администратор попытается установить более двух подключений (что приведет к 21 одновременным подключениям), эта попытка завершится ошибкой со следующим сообщением об ошибке:
  
- **Ошибка**: New-PSSession : [admin.vdomain.com] Не удалось подключиться к удаленному серверу admin.vdomain.com со следующим сообщением об ошибке: служба WS-Management *не может обработать запрос. Превышено максимальное количество параллельных оболочк для этого клиента. Закройте существующие оболочки или создайте квоту для этого клиента. Дополнительные сведения см. в разделе " [Удаленное устранение неполадок"](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Решение**. Единственный способ устранить эту проблему — закрыть одно или несколько предыдущих подключений. По окончании работы с Skype для бизнеса online рекомендуется использовать командлет **Remove-PSSession**, чтобы завершить сеанс. Это поможет предотвратить проблему.  
 
## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для управления Skype для бизнеса online с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
