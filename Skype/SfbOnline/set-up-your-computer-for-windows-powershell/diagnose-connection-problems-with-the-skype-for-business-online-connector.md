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
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors.
ms.openlocfilehash: b4f4bc41673ec91bbd408c5df950d9a1535b5963
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "44204970"
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

- [Превышено максимальное число параллельных оболочек для этого пользователя в Skype для бизнеса Online](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Превышено максимальное число параллельных оболочек для этого клиента в Skype для бизнеса Online](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Ошибка Import-Module, вызванная политикой выполнения Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

Политика выполнения PowerShell помогает определить, какие файлы конфигурации можно загрузить в консоль PowerShell и какие сценарии пользователь может запустить из этой консоли. Как минимум Модуль соединителя Skype для бизнеса Online невозможно импортировать, если политика выполнения имеет значение RemoteSigned. Если это не так, вы получите следующее сообщение об ошибке при попытке импортировать модуль:
  
- **Ошибка**: <em>Import-Module: файл C: \\ Program Files. \\ общие файлы \\ Microsoft Lync Server 2013 \\ modules \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup. PSM1 невозможно загрузить, так как в этой системе отключены запущенные сценарии. Дополнительные сведения можно найти в разделе about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170 .</em>

- **Решение**: чтобы устранить эту проблему, запустите PowerShell с правами администратора, а затем выполните следующую команду:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Сведения о политике выполнения см. в разделе [Сведения о политиках выполнения](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Ошибка Import-Module, вызванная неправильной версией Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Модуль соединителя Skype для бизнеса Online можно запускать только в Windows PowerShell 3.0. Если вы попытаетесь импортировать модуль в предыдущей версии PowerShell, произойдет сбой импорта с сообщением об ошибке, аналогичным следующему:
  
  - **Ошибка**: *Import-Module: версия загруженной оболочки PowerShell — "2,0". Модуль a: \\ файлы программы \\ Общие файлы \\ для Microsoft Lync Server 2013 \\ modules \\ LyncOnlineConnector \\ LyncOnlineConnector. PSD1 "требуется минимальная версия PowerShell" 3,0 "для выполнения. Убедитесь в том, что у вас установлена оболочка PowerShell, и повторите попытку.*

- **Разрешение**: единственный способ устранить эту проблему — установить Windows PowerShell 3,0, которая доступна в центре загрузки Майкрософт по адресу [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .
  
## <a name="failed-to-connect-to-live-id-server"></a>Не удалось подключиться к серверу Live ID
<a name="BKMKFailedConnect"> </a>

Обычно три причины могут вызвать сбой подключения со следующим сообщением об ошибке:

  - **Ошибка**: *Get-CsWebTicket: не удалось подключиться к серверам Live ID. Убедитесь, что прокси-сервер включен или компьютер имеет сетевое подключение к серверам Live ID.*

- **Решение**: часто эта ошибка означает, что помощник по входу в Microsoft Online Services не запущен. Вы можете проверить состояние этой службы, запустив следующую команду из командной строки PowerShell: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Если служба не запущена, запустите ее с помощью следующей команды:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Если служба запущена, возможно, возникли проблемы с сетевым подключением между компьютером и сервером проверки подлинности Microsoft Live ID. Чтобы проверить это, откройте Internet Explorer и перейдите по ссылке [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Попробуйте войти в Microsoft 365 или Office 365. Если это сделать не удастся, возможно, возникли проблемы с сетевым подключением.
  
    В более редких случаях может быть задано неправильное значение URI подключения для сервера проверки подлинности Microsoft Live ID. Возможно, проблема в этом, если вы уже определили, что помощник по входу запущен, и у вас не возникают проблемы с сетевым подключением. В этом случае обратитесь в службу поддержки Майкрософт.
  
## <a name="failed-to-load-live-id-module"></a>Не удалось загрузить модуль Live ID
<a name="BKMKFailedLoad"> </a>

Одно из необходимых требований, чтобы использовать PowerShell для управления Skype для бизнеса online,  установить Помощник по входу в Microsoft Online Services. Если помощник по входу не установлен, вы получите следующее сообщение об ошибке при попытке создать удаленный сеанс с Skype для бизнеса online:

- **Ошибка**: *Get-CsWebTicket: не удается загрузить модуль Live ID. Убедитесь, что у вас установлена правильная версия помощника по входу Live ID.*

- **Разрешение**: помощник по входу в Microsoft Online Services доступен в центре загрузки Майкрософт на [веб-сайте помощника по входу в Microsoft Online Services для специалистов по RTW](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Произошел сбой входа для пользователя
<a name="BKMKLogonFailed"> </a>

При попытке установить удаленное подключение к Skype для бизнеса online нужно предоставить имя пользователя и пароль допустимой учетной записи пользователя Skype для бизнеса online. Если вы этого не сделаете, произойдет сбой при входе с сообщением об ошибке, аналогичным следующему:

- **Ошибка**: *Get-CsWebTicket: не удалось выполнить вход для пользователя "kenmyer@litwareinc.com". Создайте новый объект PSCredential, убедившись в том, что вы использовали правильные имя пользователя и пароль.*

- **Решение**: Если вы считаете, что используете действующую учетную запись пользователя и используете правильный пароль, попробуйте войти в систему еще раз. При сбое используйте те же учетные данные и попробуйте войти на сайте [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Если вам не удается войти в систему, обратитесь в службу поддержки Майкрософт. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>У пользователя нет разрешения на управление этим клиентом
<a name="BKMKUserPermission"> </a>

Невозможно установить удаленное подключение PowerShell к Skype для бизнеса online, если вы не являетесь участником группы "Администраторы клиента", так как в этом случае произойдет сбой подключения и вы получите следующее сообщение об ошибке:

- **Ошибка**: *New-PSSession: [admin.vdomain.com] обработка данных с удаленного сервера admin.vdomain.com завершилась со следующим сообщением об ошибке: пользователь "User@foo.com" не имеет разрешения на управление этим клиентом. Разрешения можно предоставить, назначая пользователю соответствующую роль RBAC. Дополнительные сведения можно найти в разделе [Устранение неполадок удаленного](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)доступа.*

- **Разрешение**: Если вы считаете, что являетесь членом группы "Администраторы клиента" или обязаны быть участником, вам нужно обратиться в службу поддержки Майкрософт.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Возможность подключения к клиенту отключена в Skype для бизнеса Online
<a name="BKMKAbilityConnect"> </a>

Чтобы использовать PowerShell для управления Skype для бизнеса online, для свойства EnableRemotePowerShellAccess политики клиента PowerShell нужно задать значение  `True`. Если оно не задано, произойдет сбой подключения и вы получите следующее сообщение об ошибке:

- **Ошибка**: *New-PSSession: [admin.vdomain.com] обработка данных с удаленного сервера admin.vdomain.com завершилась со следующим сообщением об ошибке: возможность подключения к этому клиенту с помощью удаленного сеанса PowerShell отключена. Обратитесь к справке Lync, чтобы проверить политику клиента PowerShell для этого клиента. Дополнительные сведения можно найти в разделе [Устранение неполадок удаленного](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)доступа.*

- **Разрешение**: Если вы видите это сообщение об ошибке, вам нужно обратиться в службу поддержки Майкрософт и получить удаленный доступ к PowerShell.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Превышено максимальное число параллельных оболочек для этого пользователя в Skype для бизнеса Online
<a name="BKMKMaxNumberShellsUser"> </a>

Каждый администратор может установить максимум три удаленных подключения к Skype для бизнеса online одновременно. Если у вас установлено три удаленных подключения PowerShell, при попытке четвертого подключения произойдет сбой со следующим сообщением об ошибке:

- **Ошибка**: *New-PSSession: [admin.vdomain.com] подключение к удаленному серверу admin.vdomain.com завершилось сбоем со следующим сообщением об ошибке: службе WS-Management не удается обработать запрос. Превышено максимальное число параллельных оболочек для этого пользователя. Закройте существующие оболочки или увеличьте квоту для этого пользователя. Дополнительные сведения можно найти в разделе [удаленное решение проблем https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 ] (*

- **Разрешение**: единственный способ устранить эту проблему — закрыть одно или несколько из предыдущих подключений. По окончании работы с Skype для бизнеса online рекомендуется использовать командлет **Remove-PSSession**, чтобы завершить сеанс. Это поможет предотвратить проблему.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Превышено максимальное число параллельных оболочек для этого клиента в Skype для бизнеса Online
<a name="BKMKMaxNumberShellsTenant"> </a>

Несмотря на то, что у каждого администратора может быть несколько трех одновременных подключений к клиенту Skype для бизнеса Online, ни один клиент не может иметь более двадцати одновременных подключений. Например, у шести администраторов может быть три открытых сеанса. Если седьмой администратор пытается открыть более двух подключений (всего 21 одновременных подключений), эта попытка завершится сбоем, и появится следующее сообщение об ошибке:
  
- **Ошибка**: *New-PSSession: [admin.vdomain.com] подключение к удаленному серверу admin.vdomain.com завершилось сбоем со следующим сообщением об ошибке: службе WS-Management не удается обработать запрос. Превышено максимальное число параллельных оболочек для этого клиента. Закройте существующие оболочки или увеличьте квоту для этого клиента. Дополнительные сведения можно найти в разделе [удаленное решение проблем https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 ] (*

- **Разрешение**: единственный способ устранить эту проблему — закрыть одно или несколько из предыдущих подключений. По окончании работы с Skype для бизнеса online рекомендуется использовать командлет **Remove-PSSession**, чтобы завершить сеанс. Это поможет предотвратить проблему.  
 
## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для управления Skype для бизнеса Online с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
