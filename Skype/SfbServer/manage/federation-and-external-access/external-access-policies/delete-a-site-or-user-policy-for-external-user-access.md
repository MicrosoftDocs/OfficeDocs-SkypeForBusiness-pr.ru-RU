---
title: Удаление сайта или пользовательской политики для доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
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
description: Вы можете удалить любой сайт или политику пользователя, указанную в панели управления Skype для бизнес-серверов на странице Политика внешнего доступа.
ms.openlocfilehash: 407e90af201055f371dc92485ab258bac851a258
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099025"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Удаление сайта или пользовательской политики для доступа внешних пользователей

Если были созданы или настроены политики внешнего доступа пользователей, которые больше не нужно использовать, выполните следующие действия.

  - Удалите любую созданную политику сайта или пользователя.

  - Сбросьте глобальную политику до значений по умолчанию. Параметры глобальной политики по умолчанию запрещают любой внешний доступ пользователей. Саму глобальную политику удалить невозможно.


Вы можете удалить любой сайт или политику пользователя, указанную в панели управления Skype для бизнес-серверов на странице **Политика внешнего** доступа. При удалении глобальной политики она на самом деле не удаляется, а восстанавливаются параметры по умолчанию, не включающие поддержку доступа внешних пользователей. Сведения об сбросе глобальной политики см. в материале [Reset the global policy for external user access.](reset-the-global-policy-for-external-user-access.md)


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Удаление политика узла или пользователя для доступа внешних пользователей

1.  С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов. 

3.  Щелкните **Доступ для внешних пользователей** и выберите **Политика внешнего доступа**.

4.  На вкладке **Политика внешнего доступа** щелкните политику узла или пользователя, которую нужно удалить, нажмите кнопку **Изменить** и затем нажмите **Удалить**.

5.  При отображении запроса на подтверждение нажмите кнопку **ОК**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Удаление политик ПИН-кода с помощью Windows PowerShell cmdlets

Политики внешнего доступа можно удалить с помощью Windows PowerShell и Remove-CsExternalAccessPolicy. Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Удаление определенной политики внешнего доступа

  - Эта команда удаляет политику внешнего доступа для узла Redmond:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Удаление всех политик внешнего доступа, применяемых к области каждого пользователя

  - Эта команда удаляет все политики внешнего доступа, настроенные на уровне пользователя:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Удаление всех политик внешнего доступа, в которых отключен внешний доступ пользователей

  - Эта команда удаляет все политики внешнего доступа, в который доступ внешних пользователей отключен:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Дополнительные сведения см. в разделе Справка для [cmdlet Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)