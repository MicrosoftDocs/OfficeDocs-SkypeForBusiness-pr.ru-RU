---
title: Диагностика проблем подключения с помощью соединителя Skype для бизнеса Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors.
ms.openlocfilehash: d377d234ff4242ac99d751b1c14d3270e1776c6c
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838771"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Диагностика проблем подключения с помощью соединителя Skype для бизнеса Online

[] Этот раздел содержит сведения, которые помогут диагностировать и устранить проблемы, возникающие при попытке создать удаленный сеанс Microsoft PowerShell для подключения к Skype для бизнеса online. Ознакомьтесь со следующими разделами:
  
- [Ошибка Import-Module, вызванная политикой выполнения Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Ошибка Import-Module, вызванная неправильной версией Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Не удалось подключиться к серверу Live ID](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Не удалось загрузить модуль Live ID](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Произошел сбой входа для пользователя](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [У пользователя нет разрешения на управление этим клиентом](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Возможность подключения к клиенту отключена в Skype для бизнеса Online](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Превышено максимальное количество одновременных оболочек для этого пользователя в Скайп для бизнеса в Интернет](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKMaxNumberShellsUser)
    
- [Превышено максимальное количество одновременных оболочек для клиента в Скайп для бизнеса в Интернет](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Ошибка Import-Module, вызванная политикой выполнения Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

Политика выполнения PowerShell помогает определить, какие файлы конфигурации можно загрузить в консоль PowerShell и какие сценарии пользователь может запустить из этой консоли. Как минимум Модуль соединителя Skype для бизнеса Online невозможно импортировать, если политика выполнения имеет значение RemoteSigned. Если это не так, вы получите следующее сообщение об ошибке при попытке импортировать модуль:
  
- **Ошибка**: <em>Import-Module: файл C:\\Program Files\\общие файлы\\Microsoft Lync Server 2013\\модулей\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 не удается загрузить, поскольку выполняется сценарии отключено на этом компьютере. Для получения дополнительных сведений см about_Execution_Policies в https://go.microsoft.com/fwlink/?LinkID=135170.</em>

- **Решение**: Чтобы устранить эту проблему, запустите PowerShell от имени администратора и запустите следующую команду:
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    Сведения о политике выполнения см. в разделе [Сведения о политиках выполнения](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Ошибка Import-Module, вызванная неправильной версией Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Модуль соединителя Skype для бизнеса Online можно запускать только в Windows PowerShell 3.0. Если вы попытаетесь импортировать модуль в предыдущей версии PowerShell, произойдет сбой импорта с сообщением об ошибке, аналогичным следующему:
  
  - **Ошибка**: *Import-Module: версия загруженных PowerShell — «2.0". Модуль "D:\\Program Files\\общие файлы\\Microsoft Lync Server 2013\\модулей\\LyncOnlineConnector\\LyncOnlineConnector.psd1" требует Минимальная версия PowerShell «3.0"для выполнения. Проверьте установку PowerShell и повторите попытку.*

- **Решение**: Установка Windows PowerShell 3.0, который доступен в центре загрузки Майкрософт по является единственным способом для устранения этой проблемы [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
## <a name="failed-to-connect-to-live-id-server"></a>Не удалось подключиться к серверу Live ID
<a name="BKMKFailedConnect"> </a>

Обычно три причины могут вызвать сбой подключения со следующим сообщением об ошибке:

  - **Ошибка**: *Get-CsWebTicket: Сбой при подключении серверов Windows live id. Убедитесь, что включен прокси-сервера или компьютера имеет сетевое подключение к live id серверы.*

- **Решение**: часто эта ошибка означает, что не работает Microsoft Online Services помощник по входу. Вы можете проверить состояние этой службы, запустив следующую команду из командной строки PowerShell: 
    ```
    Get-Service "msoidsvc"
    ```
    Если служба не запущена, запустите ее с помощью следующей команды:
    ```
    Start-Service "msoidsvc"
    ```

    Если служба запущена, возможно, возникли проблемы с сетевым подключением между компьютером и сервером проверки подлинности Microsoft Live ID. Чтобы проверить это, откройте Internet Explorer и перейдите по ссылке [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Попробуйте войти в Office 365 отсюда. Если это сделать не удастся, возможно, возникли проблемы с сетевым подключением.
  
    В более редких случаях может быть задано неправильное значение URI подключения для сервера проверки подлинности Microsoft Live ID. Возможно, проблема в этом, если вы уже определили, что помощник по входу запущен, и у вас не возникают проблемы с сетевым подключением. В таком случае обратитесь в службу поддержки Office 365.
  
## <a name="failed-to-load-live-id-module"></a>Не удалось загрузить модуль Live ID
<a name="BKMKFailedLoad"> </a>

Одно из необходимых требований, чтобы использовать PowerShell для управления Skype для бизнеса online,  установить Помощник по входу в Microsoft Online Services. Если помощник по входу не установлен, вы получите следующее сообщение об ошибке при попытке создать удаленный сеанс с Skype для бизнеса online:

- **Ошибка**: *Get-CsWebTicket: не удалось загрузить модуль Live Id. Убедитесь, что правильные версии Live Id помощник по входу.*

- **Решение**: The Microsoft Online Services помощник по входу доступен в центре загрузки Майкрософт в [Microsoft Online Services помощника по входу для RTW специалистов ИТ](https://www.microsoft.com/en-us/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Произошел сбой входа для пользователя
<a name="BKMKLogonFailed"> </a>

При попытке установить удаленное подключение к Skype для бизнеса online нужно предоставить имя пользователя и пароль допустимой учетной записи пользователя Skype для бизнеса online. Если вы этого не сделаете, произойдет сбой при входе с сообщением об ошибке, аналогичным следующему:

- **Ошибка**: *Get-CsWebTicket: не удалось выполнить вход для пользователя 'kenmyer@litwareinc.com'. Создайте новый объект PSCredential, убедившись, что используется правильное имя пользователя и пароль.*

- **Решение**: Если вы думаете, что вы используете учетную запись пользователя и что у вас есть правильный пароль, попробуйте снова войти в систему. При сбое используйте те же учетные данные и попробуйте войти на сайте [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Если там не удастся войти, обратитесь в службу поддержки Office 365. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>У пользователя нет разрешения на управление этим клиентом
<a name="BKMKUserPermission"> </a>

Невозможно установить удаленное подключение PowerShell к Skype для бизнеса online, если вы не являетесь участником группы "Администраторы клиента", так как в этом случае произойдет сбой подключения и вы получите следующее сообщение об ошибке:

- **Ошибка**: *New-PSSession: [admin.vdomain.com] обработки данных из удаленного сервера admin.vdomain.com выведено следующее сообщение об ошибке: «user@foo.com» пользователь не имеет разрешения на управление клиента. Путем включения пользователя в соответствующие роль RBAC могут быть предоставлены разрешения. Для получения дополнительных сведений см [Удаленного устранения неполадок](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Решение**: Если вы думаете, или должны быть участником группы администраторов клиента необходимо обратиться в службу поддержки Office 365.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Возможность подключения к клиенту отключена в Skype для бизнеса Online
<a name="BKMKAbilityConnect"> </a>

Чтобы использовать PowerShell для управления Skype для бизнеса online, для свойства EnableRemotePowerShellAccess политики клиента PowerShell нужно задать значение  `True`. Если оно не задано, произойдет сбой подключения и вы получите следующее сообщение об ошибке:

- **Ошибка**: *New-PSSession: [admin.vdomain.com] обработки данных из удаленного сервера admin.vdomain.com выведено следующее сообщение об ошибке: возможность подключения клиента с помощью удаленного сеанса PowerShell отключена. Обратитесь в службу поддержки Lync, чтобы просмотреть политики Powershell клиента для клиента. Для получения дополнительных сведений см [Удаленного устранения неполадок](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Решение**: Если появится данное сообщение об ошибке, то необходимо обратиться в службу поддержки Office 365 и получать удаленный доступ к PowerShell включен.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Превышено максимальное число параллельных оболочек для этого пользователя в Skype для бизнеса Online
<a name="BKMKMaxNumberShellsUser"> </a>

Каждый администратор может установить максимум три удаленных подключения к Skype для бизнеса online одновременно. Если у вас установлено три удаленных подключения PowerShell, при попытке четвертого подключения произойдет сбой со следующим сообщением об ошибке:

- **Ошибка**: *New-PSSession: [admin.vdomain.com] подключение к удаленному серверу admin.vdomain.com выведено следующее сообщение об ошибке: служба WS-Management не удается обработать запрос. Превышено максимальное количество одновременных оболочек для этого пользователя. Закройте существующими оболочками или инициировать квоты для данного пользователя. Для получения дополнительных сведений см. [удаленного] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **Решение**: закрыть один или несколько предыдущих подключений является единственным способом для устранения этой проблемы. По окончании работы с Skype для бизнеса online рекомендуется использовать командлет **Remove-PSSession**, чтобы завершить сеанс. Это поможет предотвратить проблему.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Превышено максимальное число параллельных оболочек для этого клиента в Skype для бизнеса Online
<a name="BKMKMaxNumberShellsTenant"> </a>

Хотя у каждого администратора может быть до трех одновременных подключений к клиенту Skype для бизнеса online, одному клиенту запрещено иметь больше девяти одновременных подключений. Например, три администратора могут открыть по три сеанса. Если четвертый администратор попытается установить подключение (10-е по счету), произойдет сбой со следующим сообщением об ошибке:
  
- **Ошибка**: *New-PSSession: [admin.vdomain.com] подключение к удаленному серверу admin.vdomain.com выведено следующее сообщение об ошибке: служба WS-Management не удается обработать запрос. Превышено максимальное количество одновременных оболочек для клиента. Закройте существующими оболочками или инициировать квоты для клиента. Для получения дополнительных сведений см. [удаленного] (https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **Решение**: закрыть один или несколько предыдущих подключений является единственным способом для устранения этой проблемы. По окончании работы с Skype для бизнеса online рекомендуется использовать командлет **Remove-PSSession**, чтобы завершить сеанс. Это поможет предотвратить проблему.  
 
## <a name="related-topics"></a>Связанные разделы
[Настройка компьютера для Скайп online управления бизнес-процессов с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
