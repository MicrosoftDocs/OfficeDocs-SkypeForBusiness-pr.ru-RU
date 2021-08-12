---
title: Диагностика проблем с подключением с Skype для бизнеса Online Connector
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
description: Устранение неполадок при создании удаленного сеанса PowerShell для подключения к Skype для бизнеса Online, включая импорт-модуль, совмещаемую оболочку, live ID и проблемы с разрешениями.
ms.openlocfilehash: cb9268efc5e35ec5f25ed93314a77347b4a9363f038744c4de9a934528ae371f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295956"
---
# <a name="diagnose-connection-problems-using-skype-for-business-online-connector"></a>Диагностика проблем с подключением с Skype для бизнеса Online Connector

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

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

Политика выполнения PowerShell помогает определить, какие файлы конфигурации можно загрузить в консоль PowerShell и какие сценарии пользователь может запустить из этой консоли. Как минимум, вы не сможете импортировать модуль Skype для бизнеса Online Connector, если для политики выполнения не за установлено действие RemoteSigned. Если этого не происходит, при попытке импорта модуля вы получите следующее сообщение об ошибке:
  
- Ошибка **:** Импорт-модуль : файл C. Программные файлы Общие файлы Модули Microsoft <em> \\ \\ \\ Lync Server 2013 \\ \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 не загружаются, так как запуск сценариев отключен в этой системе. Дополнительные сведения см. в about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170 .</em>

- **Решение:** чтобы устранить эту проблему, запустите PowerShell от администратора и запустите следующую команду:
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Сведения о политике выполнения см. в разделе [Сведения о политиках выполнения](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Ошибка Import-Module, вызванная неправильной версией Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Модуль соединителя Skype для бизнеса Online можно запускать только в Windows PowerShell 3.0. При попытке импортировать модуль в предыдущей версии PowerShell процесс импорта будет сбой с сообщением об ошибке, аналогичным этому:
  
  - **Ошибка**: *Import-Module : версия загружаемой PowerShell — "2.0". Модуль 'D: Program \\ Files Common Files Microsoft \\ \\ Lync Server 2013 \\ Modules \\ LyncOnlineConnectorLyncOnlineConnector.psd1' требуется минимальная версия \\ PowerShell 3.0 для выполнения. Проверьте установку PowerShell и попробуйте еще раз.*

- **Решение.** Единственный способ устранить эту проблему — установить Windows PowerShell 3.0, которая доступна в Центре загрузки Майкрософт по ссылке [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .
  
## <a name="failed-to-connect-to-live-id-server"></a>Не удалось подключиться к серверу Live ID
<a name="BKMKFailedConnect"> </a>

Обычно три причины могут вызвать сбой подключения со следующим сообщением об ошибке:

  - **Ошибка**: *Get-CsWebTicket : Failed to connect live id servers. Убедитесь, что прокси-сервер включен или на компьютере есть сетевое подключение к серверам live id.*

- **Решение.** Часто эта ошибка означает, что помощник по входу в Microsoft Online Services не запущен. Вы можете проверить состояние этой службы, запустив следующую команду из командной строки PowerShell: 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Если служба не запущена, запустите ее с помощью этой команды:
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Если служба запущена, возможно, возникли проблемы с сетевым подключением между компьютером и сервером проверки подлинности Microsoft Live ID. Чтобы проверить это, откройте Internet Explorer и перейдите по ссылке [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Попробуйте войти, чтобы Microsoft 365 или Office 365 из нее. Если это не так, возможно, у вас возникли проблемы с сетевым подключением.
  
    В меньшей степени URI подключения для сервера проверки подлинности Microsoft Live ID настроено на неправильное значение. Если вы уже определили, что Sign-In работает и проблемы с сетью не возникли, возможно, проблема заключается в этой конфигурации. В этом случае обратитесь в службу поддержки Майкрософт.
  
## <a name="failed-to-load-live-id-module"></a>Не удалось загрузить модуль Live ID
<a name="BKMKFailedLoad"> </a>

Одно из необходимых требований, чтобы использовать PowerShell для управления Skype для бизнеса online,  установить Помощник по входу в Microsoft Online Services. Если помощник по входу не установлен, при попытке установить удаленный сеанс в Skype для бизнеса Online вы получите следующее сообщение об ошибке:

- **Ошибка:** *Get-CsWebTicket : Не может загрузить модуль Live Id. Убедитесь, что установлена* правильная версия помощника по входу в Live Id.

- **Разрешение:** помощник по входу в Microsoft Online Services доступен в Центре загрузки Майкрософт на сайте [Microsoft Online Services Sign-In помощника для ИТ-специалистов RTW](https://www.microsoft.com/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Произошел сбой входа для пользователя
<a name="BKMKLogonFailed"> </a>

При попытке установить удаленное подключение к Skype для бизнеса online нужно предоставить имя пользователя и пароль допустимой учетной записи пользователя Skype для бизнеса online. Если этого не сделать, при ошибке будет отобрано сообщение об ошибке, примерно такое:

- **Ошибка:** *Get-CsWebTicket : Ошибка при kenmyer@litwareinc.com пользователя. Создайте новый объект PSCredential, убедившись,* что вы использовали правильное имя пользователя и пароль.

- **Разрешение:** если вы считаете, что используете действительную учетную запись пользователя и у вас правильный пароль, попробуйте войти еще раз. При сбое используйте те же учетные данные и попробуйте войти на сайте [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Если вы не можете войти в систему, обратитесь в службу поддержки Майкрософт. 

  
## <a name="the-user-doesnt-have-permission-to-manage-this-tenant"></a>У пользователя нет разрешения на управление этим клиентом
<a name="BKMKUserPermission"> </a>

Удаленное подключение PowerShell кSkype для бизнеса Online невозможно, если вы не входите в группу "Администраторы клиента". В этом случае попытка подключения будет неудачной, и вы получите следующее сообщение об ошибке:

- Ошибка **:** New-PSSession : [admin.vdomain.com] При обработке данных с удаленного сервера admin.vdomain.com произошла ошибка со следующим сообщением об ошибке: у пользователя user@foo.com нет разрешения на управление этим *клиентом. Разрешения можно предоставить, назначив пользователю соответствующую роль RBAC. Дополнительные сведения см. в [удалении устранения неполадок.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting)*

- **Решение:** если вы считаете, что вы или должны быть участником группы "Администраторы клиента", обратитесь в службу поддержки Майкрософт.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Возможность подключения к клиенту отключена в Skype для бизнеса Online
<a name="BKMKAbilityConnect"> </a>

Чтобы использовать PowerShell для управления Skype для бизнеса online, для свойства EnableRemotePowerShellAccess политики клиента PowerShell нужно задать значение  `True`. Если это не так, подключение не будет работать, и вы получите следующее сообщение об ошибке:

- Ошибка **:** New-PSSession : [admin vdomain.com] Обработка данных от удаленного администратора сервера vdomain.com со следующим сообщением об ошибке: Возможность подключения к этому клиенту с помощью удаленного сеанса *\. \. PowerShell отключена. Обратитесь в справку Lync, чтобы проверить политику tenant Powershell для этого клиента. Дополнительные сведения см. в [удалении устранения неполадок.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting)*

- **Решение.** Если вы видите это сообщение об ошибке, обратитесь в службу поддержки Майкрософт и включим удаленный доступ PowerShell.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Превышено максимальное число параллельных оболочек для этого пользователя в Skype для бизнеса Online
<a name="BKMKMaxNumberShellsUser"> </a>

Каждый администратор может установить максимум три удаленных подключения к Skype для бизнеса online одновременно. Если у вас установлено три удаленных подключения PowerShell, при попытке четвертого подключения произойдет сбой со следующим сообщением об ошибке:

- **Ошибка**: *New-PSSession : [admin vdomain.com] Не удалось подключиться к удаленному администратору сервера vdomain.com со следующим сообщением об ошибке: служба WS-Management не может обработать \. \. запрос. Превышено максимальное количество одновременной оболочки для этого пользователя. Закроем существующие оболочки или поднимем квоту для этого пользователя. Дополнительные сведения [](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting) см. в*

- **Решение.** Единственный способ устранить эту проблему — закрыть одно или несколько из предыдущих подключений. Завершив сеанс Skype для бизнеса Online, рекомендуется использовать для завершения этого сеанса cmdlet **Remove-PSSession.** Это действие поможет вам предотвратить эту проблему.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Превышено максимальное число параллельных оболочек для этого клиента в Skype для бизнеса Online
<a name="BKMKMaxNumberShellsTenant"> </a>

Хотя у каждого администратора может быть до трех одновременных подключений к Skype для бизнеса Online, ни один клиент не может иметь более 20 одновременных подключений. Например, у шести администраторов может быть три открытых сеанса. Если администратор в седьмом классе попытается открыть более двух подключений (в результате будет одновременно открыто 21 подключение), попытка будет со следующей ошибкой:
  
- **Ошибка**: *New-PSSession : [admin.vdomain.com] Не удалось подключиться к удаленному серверу admin.vdomain.com со следующим сообщением об ошибке: служба WS-Management не может обработать запрос. Превышено максимальное количество одновременной оболочки для этого клиента. Закроем существующие оболочки или поднимем квоту для этого клиента. Дополнительные сведения см. в [Удаленное устранение неполадок](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1.*

- **Решение.** Единственный способ устранить эту проблему — закрыть одно или несколько из предыдущих подключений. Завершив сеанс Skype для бизнеса Online, рекомендуется использовать для завершения этого сеанса с помощью **Skype для бизнеса-PSSession.** Это поможет предотвратить эту проблему.  
 
## <a name="related-topics"></a>Статьи по теме
[Настройка компьютера для управления Skype для бизнеса online с помощью Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
