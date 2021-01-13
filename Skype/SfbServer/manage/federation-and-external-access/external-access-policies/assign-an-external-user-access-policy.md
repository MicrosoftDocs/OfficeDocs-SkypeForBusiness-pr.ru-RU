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
description: Если для пользователя включена служба Skype для бизнеса Server, можно настроить федерацию SIP, удаленный доступ пользователей и подключение к общедоступным службам обмена мгновенными сообщениями в панели управления Skype для бизнеса Server, применив соответствующие политики к определенным пользователям.
ms.openlocfilehash: 25e9a63363dc4f982e142defd2164c2423471961
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826629"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Назначение политики доступа внешних пользователей пользователю, включенного в Skype для бизнеса

Если для пользователя включена служба Skype для бизнеса Server, можно настроить федерацию SIP, удаленный доступ пользователей и подключение к общедоступным службам обмена мгновенными сообщениями в панели управления Skype для бизнеса Server, применив соответствующие политики к определенным пользователям. Например, если вы создали политику для поддержки удаленного доступа пользователей, необходимо применить ее к пользователю, прежде чем пользователь сможет подключаться к Skype для бизнеса Server из удаленного расположения и взаимодействовать с внутренними пользователями из удаленного расположения.


> [!NOTE]  
> Для поддержки внешних пользователей необходимо включить поддержку для каждого типа внешнего доступа, который вы хотите поддерживать, а также настроить соответствующие политики и другие параметры для управления использования этой технологии. Подробные сведения см. в [управлении федерацией и внешним доступом к Skype для бизнеса Server.](../managing-federation-and-external-access.md)


Используйте процедуру, описанную в этом разделе, для применения ранее созданной политики доступа внешних пользователей к одним или нескольким учетным записям пользователей.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Применение политики доступа внешних пользователей к учетной записи пользователя

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 

3.  В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.

4.  В таблице со списком результатов поиска щелкните учетную запись пользователя, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.

5.  In **Edit Skype for Business Server User** under External access **policy,** select the user policy that you want to apply.
     
> [!NOTE]  
> Параметры **\<Automatic>** применяют сервер по умолчанию или параметры глобальной политики.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Назначение политик Per-User внешнего доступа с помощью Windows PowerShell

Политики внешнего доступа для каждого пользователя можно начертать с помощью Windows PowerShell и Grant-CsExternalAccessPolicy управления. Этот cmdlet можно запустить в оболочке управления Skype для бизнеса Server или в удаленном сеансе Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Назначение политики внешнего доступа для отдельного пользователя одному пользователю

  - Следующей командой пользователю Ken Myer назначается политика внешнего доступа RedmondExternalAccessPolicy на уровне пользователей.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Назначение политики внешнего доступа на пользователя нескольким пользователям

  - Эта команда назначает политику внешнего доступа на уровне пользователя USAExternalAccessPolicy всем пользователям с учетными записями в подразделении UnitedStates в Active Directory. Дополнительные сведения о параметре OU, используемом в этой команде, см. в документации по командлету [Get-CsUser.](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Чтобы отоименовать политику внешнего доступа на пользователя

  - Следующая команда отменяет назначение политики внешнего доступа, ранее назначенной для Ken Myer. После отмены назначения политики пользователь Ken Myer будет автоматически управляться глобальной политикой или, если такая существует, локальной политикой сайта. Политика сайта имеет более высокий приоритет, чем глобальная политика.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Дополнительные сведения см. в разделе справки по [cmdlet Grant-CsExternalAccessPolicy.](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)


