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
ms.openlocfilehash: 9157c556eaa2952adf2b67a514eebfb1a9d3abff
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617095"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Диагностика проблем подключения с помощью соединителя Skype для бизнеса Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[] Этот раздел содержит сведения, которые помогут диагностировать и устранить проблемы, возникающие при попытке создать удаленный сеанс Microsoft PowerShell для подключения к Skype для бизнеса online. Ознакомьтесь со следующими разделами:
  
- [Ошибка Import-Module, вызванная политикой выполнения Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Ошибка Import-Module, вызванная неправильной версией Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Сбой современной проверки подлинности при отключенной проверке подлинности WinRM Basic](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Не удалось подключиться к серверу Live ID](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Не удалось загрузить модуль Live ID](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Не удалось войти для пользователя](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [У пользователя нет разрешения на управление этим клиентом](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Возможность подключения к клиенту отключена в Skype для бизнеса Online](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Превышено максимальное количество одновременной оболочки для этого пользователя в Skype для бизнеса Online](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Превышено максимальное количество одновременной оболочки для этого клиента в Skype для бизнеса Online](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> По умолчанию сеансы PowerShell отстают через 60 минут. Чтобы повторно подключиться, необходимо закрыть сеанс и запустить новый сеанс PowerShell. Недавно была выпущена новая версия [Skype для бизнеса Online , модуль Windows PowerShell (2046.123 — опубликовано 02.01.2019),](https://www.microsoft.com/download/details.aspx?id=39366)который включает новый командлет **Enable-CsOnlineSessionForReconnection,** который устраняет проблему с 60-минутным временем.
> Сеанс PowerShell повторно подключит и пройдет проверку подлинности, что позволит использовать его повторно, не запуская новый экземпляр для повторного подключения.



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Ошибка Import-Module, вызванная политикой выполнения Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

Политика выполнения PowerShell помогает определить, какие файлы конфигурации можно загрузить в консоль PowerShell и какие сценарии пользователь может запустить из этой консоли. Как минимум Модуль соединителя Skype для бизнеса Online невозможно импортировать, если политика выполнения имеет значение RemoteSigned. Если это не так, вы получите следующее сообщение об ошибке при попытке импортировать модуль:
  
- Ошибка **:** Импорт-модуль : файл C. Программные файлы Общие файлы Модули Microsoft <em> \\ \\ \\ Lync Server 2013 \\ \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 не загружаются, так как запуск сценариев отключен в этой системе. Дополнительные сведения см. в about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170 .</em>

- **Разрешение** Чтобы устранить эту проблему, запустите PowerShell с права администратора и запустите следующую команду:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Сведения о политике выполнения см. в разделе [Сведения о политиках выполнения](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Ошибка Import-Module, вызванная неправильной версией Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Модуль соединителя Skype для бизнеса Online можно запускать только в Windows PowerShell 3.0. При попытке импортировать модуль в предыдущей версии PowerShell процесс импорта будет сбой с сообщением об ошибке, аналогичным этому сообщению:
  
  - **Ошибка**: *Import-Module : версия загружаемой PowerShell — "2.0". Модуль 'D: Program \\ Files Common Files Microsoft \\ \\ Lync Server 2013 \\ Modules \\ LyncOnlineConnectorLyncOnlineConnector.psd1' требуется минимальная версия \\ PowerShell 3.0 для выполнения. Проверьте установку PowerShell и попробуйте еще раз.*

- **Решение.** Единственный способ устранить эту проблему — установить Windows PowerShell 3.0, которая доступна в Центре загрузки Майкрософт по ссылке [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>Сбой современной проверки подлинности при отключенной проверке подлинности WinRM Basic
<a name="BKMKWinRMBasicAuth"> </a>

В последней версии модуля Skype для бизнеса Online Connector используется современная проверка подлинности, но для клиента удаленного управления Windows (WinRM) необходимо разрешить базовую проверку подлинности.  При современной проверке подлинности используются маркеры сноски, которые обычно передаются в заглавной области *Авторизация: Bearer.* Windows PowerShell, на основе Skype для бизнеса PowerShell, не разрешается использовать этот заглавный заглавный.  Вместо этого Skype для бизнеса PowerShell передает маркер сноски с помощью заглавного заглавного слова *Authorization: Basic.*

Инструкции [о том,](./download-and-install-windows-powershell-5-1.md) как включить проверку подлинности WinRM для Basic, см. в Windows PowerShell и установить Windows PowerShell.

## <a name="failed-to-connect-to-live-id-server"></a>Не удалось подключиться к серверу Live ID
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> Проверка подлинности live ID для соединителя Skype для бизнеса не является. Используйте модуль Teams PowerShell для управления сетевым клиентом. При управлении гибридными средами обновляются до последнего накопительного обновления или используется проверка подлинности oAuth.

Обычно три причины могут вызвать сбой подключения со следующим сообщением об ошибке:

  - **Ошибка**: *Get-CsWebTicket : Failed to connect live id servers. Убедитесь, что прокси-сервер включен или на компьютере есть сетевое подключение к серверам live ID.*

- **Решение.** Часто эта ошибка означает, что помощник по входу в Microsoft Online Services не запущен. Вы можете проверить состояние этой службы, запустив следующую команду из командной строки PowerShell: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Если служба не запущена, запустите ее с помощью следующей команды:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Если служба запущена, возможно, возникли проблемы с сетевым подключением между компьютером и сервером проверки подлинности Microsoft Live ID. Чтобы проверить это, откройте Internet Explorer и перейдите по ссылке [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Попробуйте войти, чтобы Microsoft 365 или Office 365 из нее. Если это сделать не удастся, возможно, возникли проблемы с сетевым подключением.
  
    В более редких случаях может быть задано неправильное значение URI подключения для сервера проверки подлинности Microsoft Live ID. Возможно, проблема в этом, если вы уже определили, что помощник по входу запущен, и у вас не возникают проблемы с сетевым подключением. В этом случае обратитесь в службу поддержки Майкрософт.
  
## <a name="failed-to-load-live-id-module"></a>Не удалось загрузить модуль Live ID
<a name="BKMKFailedLoad"> </a>

Одно из необходимых требований, чтобы использовать PowerShell для управления Skype для бизнеса online,  установить Помощник по входу в Microsoft Online Services. Если помощник по входу не установлен, вы получите следующее сообщение об ошибке при попытке создать удаленный сеанс с Skype для бизнеса online:

- **Ошибка:** *Get-CsWebTicket : Не может загрузить модуль Live ID. Убедитесь, что установлена* правильная версия помощника по входу в Live Id.

- **Разрешение:** помощник по входу в Microsoft Online Services доступен в Центре загрузки Майкрософт на сайте Microsoft Online Services Sign-In для ИТ-специалистов [RTW](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Произошел сбой входа для пользователя
<a name="BKMKLogonFailed"> </a>

При попытке установить удаленное подключение к Skype для бизнеса online нужно предоставить имя пользователя и пароль допустимой учетной записи пользователя Skype для бизнеса online. Если этого не сделать, при ошибке будет отобрано сообщение об ошибке, аналогичное этому сообщению:

- **Ошибка:** *Get-CsWebTicket : Ошибка при kenmyer@litwareinc.com пользователя. Создайте новый объект PSCredential, убедившись,* что вы использовали правильное имя пользователя и пароль.

- **Разрешение:** если вы считаете, что используете действительную учетную запись пользователя и у вас правильный пароль, попробуйте войти еще раз. Если это не удается, используйте те же учетные данные и попробуйте войти в [https://login.microsoftonline.com/](https://login.microsoftonline.com/) . Если вам не удается войти в нее, обратитесь в службу поддержки Майкрософт. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>У пользователя нет разрешения на управление этим клиентом
<a name="BKMKUserPermission"> </a>

Невозможно установить удаленное подключение PowerShell к Skype для бизнеса online, если вы не являетесь участником группы "Администраторы клиента", так как в этом случае произойдет сбой подключения и вы получите следующее сообщение об ошибке:

- Ошибка **:** New-PSSession : [admin.vdomain.com] Сбой обработки данных с удаленного сервера admin.vdomain.com со следующим сообщением об ошибке: у пользователя "user@foo.com" нет разрешения на управление этим *клиентом. Разрешения можно предоставить, назначив пользователю соответствующую роль RBAC. Дополнительные сведения см. в [удалении устранения неполадок.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )*

- **Решение:** если вы считаете, что вы входите в группу "Администраторы клиента", обратитесь в службу поддержки Майкрософт.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Возможность подключения к клиенту отключена в Skype для бизнеса Online
<a name="BKMKAbilityConnect"> </a>

Чтобы использовать PowerShell для управления Skype для бизнеса online, для свойства EnableRemotePowerShellAccess политики клиента PowerShell нужно задать значение  `True`. Если оно не задано, произойдет сбой подключения и вы получите следующее сообщение об ошибке:

- Ошибка **:** New-PSSession : [admin.vdomain.com] Сбой обработки данных с удаленного сервера admin.vdomain.com со следующим сообщением об ошибке: Возможность подключения к этому клиенту с помощью удаленного сеанса *PowerShell отключена. Обратитесь в справку Lync, чтобы проверить политику tenant Powershell для этого клиента. Дополнительные сведения см. в [удалении устранения неполадок.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )*

- **Решение.** Если вы видите это сообщение об ошибке, обратитесь в службу поддержки Майкрософт и включим удаленный доступ PowerShell.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Превышено максимальное число параллельных оболочек для этого пользователя в Skype для бизнеса Online
<a name="BKMKMaxNumberShellsUser"> </a>

Каждый администратор может установить максимум три удаленных подключения к Skype для бизнеса online одновременно. Если у вас установлено три удаленных подключения PowerShell, при попытке четвертого подключения произойдет сбой со следующим сообщением об ошибке: 

- **Ошибка**: *New-PSSession : [admin.vdomain.com] Не удалось подключиться к удаленному серверу admin.vdomain.com со следующим сообщением об ошибке: служба WS-Management не может обработать запрос. Превышено максимальное количество одновременной оболочки для этого пользователя. Закроем существующие оболочки или поднимем квоту для этого пользователя. Дополнительные сведения см. в [удалении устранения неполадок.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )*

- **Решение.** Единственный способ устранить эту проблему — закрыть одно или несколько из предыдущих подключений. По окончании работы с Skype для бизнеса online рекомендуется использовать командлет **Remove-PSSession**, чтобы завершить сеанс. Это поможет предотвратить проблему.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Превышено максимальное число параллельных оболочек для этого клиента в Skype для бизнеса Online
<a name="BKMKMaxNumberShellsTenant"> </a>

Хотя у каждого администратора может быть до трех одновременных подключений к Skype для бизнеса Online, ни одному клиенту не разрешено иметь более 20 одновременных подключений. Например, у шести администраторов может быть три открытых сеанса. Если четвертый администратор попытается создать более двух подключений (в результате будет одновременно 21 подключение), попытка будет со следующей ошибкой:
  
- **Ошибка**: *New-PSSession : [admin.vdomain.com] Не удалось подключиться к удаленному серверу admin.vdomain.com со следующим сообщением об ошибке: служба WS-Management не может обработать запрос. Превышено максимальное количество одновременной оболочки для этого клиента. Закроем существующие оболочки или поднимем квоту для этого клиента. Дополнительные сведения см. в [удалении устранения неполадок.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )*

- **Решение.** Единственный способ устранить эту проблему — закрыть одно или несколько из предыдущих подключений. По окончании работы с Skype для бизнеса online рекомендуется использовать командлет **Remove-PSSession**, чтобы завершить сеанс. Это поможет предотвратить проблему.  
 
## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для управления Skype для бизнеса с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
