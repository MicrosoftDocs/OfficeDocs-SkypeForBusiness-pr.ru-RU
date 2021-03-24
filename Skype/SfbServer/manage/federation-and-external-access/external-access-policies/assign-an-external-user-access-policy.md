---
title: Назначение политики доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Если пользователь включен для Skype для бизнес-сервера, вы можете настроить федерацию SIP, удаленный доступ к пользователю и подключение к общедоступным мгновенным сообщениями (IM) в панели управления Skype для бизнес-серверов, применяя соответствующие политики для определенных пользователей.
ms.openlocfilehash: 45e22a0d7951bfe4d58d90a1e5190aa242f7b29a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099055"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Назначение внешней политики доступа пользователей пользователю с включенной поддержкой Skype для бизнеса

Если пользователь включен для Skype для бизнес-сервера, вы можете настроить федерацию SIP, удаленный доступ к пользователю и подключение к общедоступным мгновенным сообщениями (IM) в панели управления Skype для бизнес-серверов, применяя соответствующие политики для определенных пользователей. Например, если вы создали политику поддержки удаленного доступа к пользователю, необходимо применить ее к пользователю, прежде чем пользователь сможет подключиться к Skype для бизнеса Server из удаленного расположения и сотрудничать с внутренними пользователями из удаленного расположения.


> [!NOTE]  
> Для поддержки внешних пользователей необходимо включить поддержку для каждого типа внешнего доступа, который вы хотите поддерживать, а также настроить соответствующие политики и другие параметры для управления использования этой технологии. Подробные сведения см. [в материале Managing federation and external access to Skype for Business Server.](../managing-federation-and-external-access.md)


Используйте процедуру, описанную в этом разделе, для применения ранее созданной политики доступа внешних пользователей к одним или нескольким учетным записям пользователей.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Применение политики доступа внешних пользователей к учетной записи пользователя

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов. 

3.  В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.

4.  В таблице со списком результатов поиска щелкните учетную запись пользователя, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.

5.  В **статье Изменить skype для пользователя бизнес-сервера** в соответствии с **политикой внешнего** доступа выберите политику пользователя, которую необходимо применить.
     
> [!NOTE]  
> Параметры **\<Automatic>** применяют сервер по умолчанию или параметры глобальной политики.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Назначение Per-User внешних политик доступа с помощью Windows PowerShell cmdlets

Политика внешнего доступа для каждого пользователя может быть назначена с помощью Windows PowerShell и Grant-CsExternalAccessPolicy. Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Назначение политики внешнего доступа для каждого пользователя одному пользователю

  - Следующей командой пользователю Ken Myer назначается политика внешнего доступа RedmondExternalAccessPolicy на уровне пользователей.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Назначение политики внешнего доступа для каждого пользователя нескольким пользователям

  - Эта команда назначает политику внешнего доступа на уровне пользователя USAExternalAccessPolicy всем пользователям с учетными записями в подразделении UnitedStates в Active Directory. Дополнительные сведения о параметре OU, используемом в этой команде, см. в документации для [командлета Get-CsUser.](/powershell/module/skype/Get-CsUser)
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Чтобы отогнать политику внешнего доступа для каждого пользователя

  - Следующая команда отменяет назначение политики внешнего доступа, ранее назначенной для Ken Myer. После отмены назначения политики пользователь Ken Myer будет автоматически управляться глобальной политикой или, если такая существует, локальной политикой сайта. Политика сайта имеет более высокий приоритет, чем глобальная политика.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Дополнительные сведения см. в разделе Справка для [cmdlet Grant-CsExternalAccessPolicy.](/powershell/module/skype/Grant-CsExternalAccessPolicy)