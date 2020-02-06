---
title: Удаление сайта или пользовательской политики для доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Вы можете удалить любые сайты и политики пользователей, указанные на панели управления "Skype для бизнеса" на сервере, на странице политики внешней доступа.
ms.openlocfilehash: 2472058009622834e20a1657167c7061b9706579
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818290"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Удаление сайта или пользовательской политики для доступа внешних пользователей

Если вы создали или настроили политики доступа внешних пользователей, которые вы больше не хотите использовать, вы можете сделать следующее:

  - Удалите все созданные вами сайты и политики пользователей.

  - Восстановление параметров глобальной политики по умолчанию. Параметры глобальной политики по умолчанию запрещают доступ к внешним пользователям. Невозможно удалить глобальную политику.


Вы можете удалить любые сайты и политики пользователей, указанные на панели управления "Skype для бизнеса" на сервере, на странице **политики внешней доступа** . При удалении глобальной политики фактически она не удаляется, но только восстанавливает параметры, заданные по умолчанию, которые не включают поддержку каких – либо параметров доступа внешних пользователей. Дополнительные сведения о сбросе глобальной политики см. [в разделе Восстановление глобальной политики для внешнего доступа пользователей](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Удаление политики сайта или пользователя для доступа внешних пользователей

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server. 

3.  Выберите **внешний доступ пользователей**и нажмите кнопку **Политика внешних доступа**.

4.  На вкладке **внешняя политика доступа** выберите сайт или политику пользователей, которые вы хотите удалить, и нажмите кнопку **изменить**, а затем — **Удалить**.

5.  Когда появится запрос на подтверждение удаления, нажмите кнопку **ОК**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Удаление политик закрепления с помощью командлетов Windows PowerShell

Внешние политики доступа можно удалить с помощью Windows PowerShell и командлета Remove-Ксекстерналакцессполици. Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Удаление особой политики внешнего доступа

  - Эта команда удаляет политику внешней политики доступа, примененную к сайту Redmond.
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Чтобы удалить все внешние политики доступа, примененные к области "на пользователя"

  - Эта команда удаляет все политики внешней доступа, настроенные для области "на пользователя".
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Удаление всех внешних политик доступа, для которых отключен доступ за пределами пользователей

  - Эта команда удаляет все внешние политики доступа, в которых отключен доступ за пределы пользователей.
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Дополнительные сведения можно найти в разделе справки по командлету [Remove-ксекстерналакцессполици](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .
