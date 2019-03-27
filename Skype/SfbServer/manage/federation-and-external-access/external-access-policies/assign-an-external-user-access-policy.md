---
title: Назначение политики доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Если пользователь включен для Скайп для сервера, можно настроить федерацию SIP, удаленного доступа пользователей и общедоступных служб обмена мгновенными сообщениями (IM) в Скайп для панели управления Business Server путем применения соответствующих политик к определенным пользователям.
ms.openlocfilehash: f07a407fee6f32f4cd4207c93ca19341e409ea78
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881502"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Назначьте политику доступа внешних пользователей Скайп для пользователя с поддержкой бизнеса

Если пользователь включен для Скайп для сервера, можно настроить федерацию SIP, удаленного доступа пользователей и общедоступных служб обмена мгновенными сообщениями (IM) в Скайп для панели управления Business Server путем применения соответствующих политик к определенным пользователям. Например при создании политики для поддержки доступа удаленных пользователей, необходимо применить его для пользователя перед пользователь может подключаться к Скайп для Business Server на удаленном компьютере и совместно работать с внутренними пользователями из удаленного местоположения.


> [!NOTE]  
> Для поддержки доступа внешних пользователей, необходимо включить поддержку для каждого типа доступа внешних пользователей, которые вы хотите обеспечить поддержку и настройки соответствующих политик и других параметров для управления его использования. Дополнительные сведения см [Управление Федерация и внешний доступ к Скайп для Business Server](../managing-federation-and-external-access.md).


Используйте описанную в этом разделе для применения политики доступа ранее созданной внешних пользователей для одного или нескольких учетных записей пользователей.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Для применения политики доступа внешних пользователей к учетной записи пользователя

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server. 

3.  В левой панели навигации нажмите **Пользователи** и выполните поиск учетной записи, которую вы хотите настроить.

4.  В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.

5.  В **Скайп изменение для пользователя Business Server** в разделе **Политика внешнего доступа**выберите пользовательскую политику, которую нужно применить.
     
> [!NOTE]  
> ** \<Automatic>** применяются параметры сервера по умолчанию или параметров глобальной политики.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Назначение политик внешнего доступа на уровне пользователя с помощью командлетов Windows PowerShell

Может быть назначен политик внешнего доступа на уровне пользователя с помощью командлета Grant-CsExternalAccessPolicy и Windows PowerShell. Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Назначение политики внешнего доступа пользователя к отдельному пользователю

  - Эта команда назначает индивидуальную пользовательскую политику внешнего доступа RedmondExternalAccessPolicy пользователю Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Назначение политики внешнего доступа пользователя к нескольким пользователям

  - Эта команда назначает политику внешнего доступа пользователя USAExternalAccessPolicy для всех пользователей, имеющих учетные записи в Соединенных Штатах Америки Подразделения в Active Directory. Дополнительные сведения о Подразделении параметр, используемый в этой команде командлет [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) см.
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Отмена назначения индивидуальной политики внешнего доступа

  - Эта команда unassigns все политики внешнего доступа пользователя, ранее назначенную пользователю Ken Myer. После отмены назначения для Кена Майера будет автоматически действовать глобальная политика или локальная политика сайта, если такая существует. Политика сайта имеет приоритет над глобальной политикой.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Для получения дополнительных сведений см раздел справки для командлета [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .


