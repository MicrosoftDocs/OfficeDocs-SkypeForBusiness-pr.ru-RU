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

- [Превышено максимальное количество одновременной оболочки для этого пользователя в Skype для бизнеса Online](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Превышено максимальное количество одновременной оболочки для этого клиента в Skype для бизнеса Online](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Ошибка Import-Module, вызванная политикой выполнения Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

Политика выполнения PowerShell помогает определить, какие файлы конфигурации можно загрузить в консоль PowerShell и какие сценарии пользователь может запустить из этой консоли. Как минимум Модуль соединителя Skype для бизнеса Online невозможно импортировать, если политика выполнения имеет значение RemoteSigned. Если это не так, вы получите следующее сообщение об ошибке при попытке импортировать модуль:
  
- Ошибка **:** <em>Import-Module : File C: \\ Program Files Common Files Microsoft \\ \\ Lync Server 2013 \\ Modules \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 не загружается, так как запуск сценариев отключен в этой системе. Дополнительные сведения см. в about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170 .</em>

- **Решение:** Чтобы устранить эту проблему, запустите PowerShell с права администратора, а затем запустите следующую команду:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Сведения о политике выполнения см. в разделе [Сведения о политиках выполнения](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Ошибка Import-Module, вызванная неправильной версией Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Модуль соединителя Skype для бизнеса Online можно запускать только в Windows PowerShell 3.0. Если вы попытаетесь импортировать модуль в предыдущей версии PowerShell, произойдет сбой импорта с сообщением об ошибке, аналогичным следующему:
  
  - **Ошибка**: *Import-Module : версия загруженного PowerShell —2.0. Модуль D: \\ Program Files \\ Common Files Microsoft \\ Lync Server 2013 \\ Modules \\ LyncOnlineConnectorLyncOnlineConnector.psd1' требует выполнения минимальной версии \\ PowerShell 3.0. Проверьте установку PowerShell и попробуйте еще раз.*

- **Решение:** единственный способ устранить эту проблему — установить Windows PowerShell 3.0, которая доступна в Центре загрузки Майкрософт по [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) ссылке.
  
## <a name="failed-to-connect-to-live-id-server"></a>Не удалось подключиться к серверу Live ID
<a name="BKMKFailedConnect"> </a>

Обычно три причины могут вызвать сбой подключения со следующим сообщением об ошибке:

  - **Ошибка:** *Get-CsWebTicket : Failed to connect live id servers. Убедитесь, что прокси-сервер* включен или компьютер подключен к серверам live id.

- **Решение.** Часто эта ошибка означает, Microsoft Online Services помощник по входу не запущен. Вы можете проверить состояние этой службы, запустив следующую команду из командной строки PowerShell: 
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

- **Ошибка:** *Get-CsWebTicket : Не может загрузить модуль Live ID. Убедитесь, что установлена* правильная версия помощника по входу в Live Id.

- **Решение:** помощник Microsoft Online Services по входу доступен в Центре загрузки Майкрософт на сайте Microsoft Online Services Sign-In для [ИТ-специалистов, RTW](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Произошел сбой входа для пользователя
<a name="BKMKLogonFailed"> </a>

При попытке установить удаленное подключение к Skype для бизнеса online нужно предоставить имя пользователя и пароль допустимой учетной записи пользователя Skype для бизнеса online. Если вы этого не сделаете, произойдет сбой при входе с сообщением об ошибке, аналогичным следующему:

- **Ошибка:** *Get-CsWebTicket : Ошибка при логотипе пользователя "kenmyer@litwareinc.com". Создайте новый объект PSCredential, убедившись,* что вы использовали правильное имя пользователя и пароль.

- **Решение:** если вы считаете, что используете допустимую учетную запись пользователя и у вас правильный пароль, попробуйте войти еще раз. При сбое используйте те же учетные данные и попробуйте войти на сайте [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Если вам не удается войти в систему, обратитесь в службу поддержки Майкрософт. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>У пользователя нет разрешения на управление этим клиентом
<a name="BKMKUserPermission"> </a>

Невозможно установить удаленное подключение PowerShell к Skype для бизнеса online, если вы не являетесь участником группы "Администраторы клиента", так как в этом случае произойдет сбой подключения и вы получите следующее сообщение об ошибке:

- Ошибка **:** New-PSSession : [admin.vdomain.com] Обработка данных с удаленного сервера admin.vdomain.com со следующим сообщением об ошибке: у пользователя "user@foo.com" нет разрешения на управление этим *клиентом. Разрешения можно получить, назначив пользователю соответствующую роль RBAC. Дополнительные сведения см. в [удаленном устранении неполадок.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*

- **Решение.** Если вы считаете, что вы входите в группу "Администраторы клиента" или должны быть в этой группе, обратитесь в службу поддержки Майкрософт.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Возможность подключения к клиенту отключена в Skype для бизнеса Online
<a name="BKMKAbilityConnect"> </a>

Чтобы использовать PowerShell для управления Skype для бизнеса online, для свойства EnableRemotePowerShellAccess политики клиента PowerShell нужно задать значение  `True`. Если оно не задано, произойдет сбой подключения и вы получите следующее сообщение об ошибке:

- Ошибка **:** New-PSSession : [admin.vdomain.com] Обработка данных с удаленного сервера admin.vdomain.com со следующим сообщением об ошибке: Возможность подключения к этому клиенту с помощью удаленного сеанса *PowerShell отключена. Обратитесь в справку Lync, чтобы проверить политику клиента Powershell для этого клиента. Дополнительные сведения см. в [удаленном устранении неполадок.](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1)*

- **Решение.** Если вы видите это сообщение об ошибке, вам потребуется обратиться в службу поддержки Майкрософт и включить удаленный доступ PowerShell.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Превышено максимальное число параллельных оболочек для этого пользователя в Skype для бизнеса Online
<a name="BKMKMaxNumberShellsUser"> </a>

Каждый администратор может установить максимум три удаленных подключения к Skype для бизнеса online одновременно. Если у вас установлено три удаленных подключения PowerShell, при попытке четвертого подключения произойдет сбой со следующим сообщением об ошибке:

- **Ошибка**: New-PSSession : [admin.vdomain.com] Не удалось подключиться к удаленному серверу admin.vdomain.com со следующим сообщением об ошибке: WS-Management служба не может *обработать запрос. Превышено максимальное количество одновременной оболочки для этого пользователя. Закроем существующие оболочки или поднимем квоту для этого пользователя. Дополнительные сведения см. в [удаленном https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 устранении неполадок](*

- **Решение:** единственный способ устранить эту проблему — закрыть одно или несколько из предыдущих подключений. По окончании работы с Skype для бизнеса online рекомендуется использовать командлет **Remove-PSSession**, чтобы завершить сеанс. Это поможет предотвратить проблему.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Превышено максимальное число параллельных оболочек для этого клиента в Skype для бизнеса Online
<a name="BKMKMaxNumberShellsTenant"> </a>

Хотя у каждого администратора может быть до трех одновременных подключений к клиенту Skype для бизнеса Online, одному клиенту запрещено иметь более двадцати одновременных подключений. Например, шесть администраторов могут в каждом из трех открытых сеансов. Если седьмой администратор попытается открыть более двух подключений (21 одновременный), попытка будет со следующей ошибкой:
  
- **Ошибка**: New-PSSession : [admin.vdomain.com] Не удалось подключиться к удаленному серверу admin.vdomain.com со следующим сообщением об ошибке: WS-Management служба не может *обработать запрос. Превышено максимальное количество одновременной оболочки для этого клиента. Закроем существующие оболочки или поднимем квоту для этого клиента. Дополнительные сведения см. в [удаленном https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 устранении неполадок](*

- **Решение:** единственный способ устранить эту проблему — закрыть одно или несколько из предыдущих подключений. По окончании работы с Skype для бизнеса online рекомендуется использовать командлет **Remove-PSSession**, чтобы завершить сеанс. Это поможет предотвратить проблему.  
 
## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для управления skype для бизнеса с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
