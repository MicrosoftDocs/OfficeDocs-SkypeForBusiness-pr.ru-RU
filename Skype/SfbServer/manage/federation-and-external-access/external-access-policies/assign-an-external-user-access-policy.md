---
title: Назначение политики доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Если пользователь включен для Skype для бизнеса Server, вы можете настроить SIP-федерацию, удаленный доступ к пользователю и подключение к общедоступным мгновенным сообщениями (IM) в панели управления Skype для бизнеса Server, применяя соответствующие политики для определенных пользователей.
ms.openlocfilehash: 400c49dfc7d0c893af98a8da7bc53894a39d6a9a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843922"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Назначение внешней политики доступа к пользователю для Skype для бизнеса включенного пользователя

Если пользователь включен для Skype для бизнеса Server, вы можете настроить SIP-федерацию, удаленный доступ к пользователю и подключение к общедоступным мгновенным сообщениями (IM) в панели управления Skype для бизнеса Server, применяя соответствующие политики для определенных пользователей. Например, если вы создали политику поддержки удаленного доступа к пользователю, ее необходимо применить к пользователю, прежде чем пользователь сможет подключиться к Skype для бизнеса Server из удаленного расположения и сотрудничать с внутренними пользователями из удаленного расположения.


> [!NOTE]  
> Для поддержки внешних пользователей необходимо включить поддержку для каждого типа внешнего доступа, который вы хотите поддерживать, а также настроить соответствующие политики и другие параметры для управления использования этой технологии. Подробные сведения см. [в материале Managing federation and external access to Skype для бизнеса Server.](../managing-federation-and-external-access.md)


Используйте процедуру, описанную в этом разделе, для применения ранее созданной политики доступа внешних пользователей к одним или нескольким учетным записям пользователей.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Применение политики доступа внешних пользователей к учетной записи пользователя

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления. 

3.  В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.

4.  В таблице со списком результатов поиска щелкните учетную запись пользователя, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.

5.  В **статье Изменение Skype для бизнеса Server пользователя** в соответствии с **политикой внешнего** доступа выберите политику пользователя, которую необходимо применить.
     
> [!NOTE]  
> Параметры **\<Automatic>** применяют сервер по умолчанию или параметры глобальной политики.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Назначение Per-User внешних политик доступа с помощью Windows PowerShell cmdlets

Политика внешнего доступа для каждого пользователя может быть назначена с помощью Windows PowerShell и Grant-CsExternalAccessPolicy. Этот комлет можно запускать из Skype для бизнеса Server или удаленного сеанса Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Назначение политики внешнего доступа для каждого пользователя одному пользователю

  - Следующей командой пользователю Ken Myer назначается политика внешнего доступа RedmondExternalAccessPolicy на уровне пользователей.<br/><br/>Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Назначение политики внешнего доступа для каждого пользователя нескольким пользователям

  - Эта команда назначает политику внешнего доступа на уровне пользователя USAExternalAccessPolicy всем пользователям с учетными записями в подразделении UnitedStates в Active Directory. Дополнительные сведения о параметре OU, используемом в этой команде, см. в документации для [командлета Get-CsUser.](/powershell/module/skype/Get-CsUser)<br/><br/>Get-CsUser -OU "ou=United States,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Чтобы отогнать политику внешнего доступа для каждого пользователя

  - Следующая команда отменяет назначение политики внешнего доступа, ранее назначенной для Ken Myer. После отмены назначения политики пользователь Ken Myer будет автоматически управляться глобальной политикой или, если такая существует, локальной политикой сайта. Политика сайта имеет более высокий приоритет, чем глобальная политика.<br/><br/>Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null


Дополнительные сведения см. в разделе Справка для [cmdlet Grant-CsExternalAccessPolicy.](/powershell/module/skype/Grant-CsExternalAccessPolicy)
