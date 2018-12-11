---
title: Удаление сайта или пользовательской политики для доступа внешних пользователей
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Можно удалить любой политику узла или пользователя, который указан в Скайп для панели управления Business Server на странице политика внешнего доступа.
ms.openlocfilehash: 53087985ee0723a6291582c3a584be0986119918
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222858"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Удаление сайта или пользовательской политики для доступа внешних пользователей

Если были созданы или настроены политики доступа внешних пользователей, которые больше не хотите использовать, можно сделать следующее:

  - Удалите политику узла или пользователя, который вы создали.

  - Сброс глобальной политики по умолчанию. Параметры глобальной политики по умолчанию запретить доступ внешних пользователей. Не удается удалить глобальную политику.


Можно удалить любой политику узла или пользователя, который указан в Скайп для панели управления Business Server на странице **Политика внешнего доступа** . Удаление глобальной политики не приводит к удалению фактически, но только сбрасывает параметры по умолчанию, которые не поддерживают функцию для параметров доступа внешних пользователей. Для получения дополнительных сведений о Сброс глобальной политики видеть [Сброс глобальной политики для доступа внешних пользователей](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Чтобы удалить политику сайта или пользователя для доступа внешних пользователей

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server. 

3.  **Доступ внешних пользователей**, щелкните **Политика внешнего доступа**.

4.  На вкладке **Политика внешнего доступа** щелкните в политике сайта или пользователя, которые необходимо удалить, нажмите кнопку **Изменить**и выберите команду **Удалить**.

5.  При появлении запроса на подтверждение нажмите **кнопку ОК**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Удаление политик ПИН-кода с помощью командлетов Windows PowerShell

Политики внешнего доступа можно удалить с помощью Windows PowerShell и командлет Remove-CsExternalAccessPolicy. Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Чтобы удалить политику внешнего доступа

  - Эта команда удаляет политику внешнего доступа, применяемых к сайту Redmond:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Удаление всех внешний доступ к политик, применяемых на уровне пользователя

  - Эта команда удаляет все политики внешнего доступа, настроенные на уровне пользователя:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Удаление всех политик внешнего доступа, где отключена доступа внешних пользователей

  - Эта команда удаляет все политики внешнего доступа, где внешних пользователей доступ был отключен:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Для получения дополнительных сведений см раздел справки для командлета [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .
