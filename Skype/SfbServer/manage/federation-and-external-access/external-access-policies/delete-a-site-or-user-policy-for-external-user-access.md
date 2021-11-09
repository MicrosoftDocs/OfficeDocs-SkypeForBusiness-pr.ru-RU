---
title: Удаление сайта или пользовательской политики для доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
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
description: Вы можете удалить любой сайт или политику пользователя, указанную в панели управления Skype для бизнеса Server на странице Политика внешнего доступа.
ms.openlocfilehash: 136b7f612dc2dcc0625e7f844ecf6ad38aba0c37
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834227"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Удаление сайта или пользовательской политики для доступа внешних пользователей

Если вы создали или настроили внешние политики доступа к пользователям, которые больше не нужно использовать, вы можете сделать следующий метод:

  - Удалите любую созданную политику сайта или пользователя.

  - Сбросьте глобальную политику до значений по умолчанию. Параметры глобальной политики по умолчанию запрещают любой внешний доступ пользователей. Саму глобальную политику удалить невозможно.


Вы можете удалить любой сайт или политику пользователя, которая указана в панели управления Skype для бизнеса Server на странице **Политика внешнего** доступа. Удаление глобальной политики фактически не удаляет ее, а только сбрасывает ее в параметры по умолчанию, которые не включают поддержку любых внешних параметров доступа пользователей. Сведения об сбросе глобальной политики см. в материале [Reset the global policy for external user access.](reset-the-global-policy-for-external-user-access.md)


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Удаление политика узла или пользователя для доступа внешних пользователей

1.  С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления. 

3.  Щелкните **Доступ для внешних пользователей** и выберите **Политика внешнего доступа**.

4.  На вкладке **Политика внешнего доступа** щелкните политику узла или пользователя, которую нужно удалить, нажмите кнопку **Изменить** и затем нажмите **Удалить**.

5.  При отображении запроса на подтверждение нажмите кнопку **ОК**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Удаление политик ПИН-кода с помощью Windows PowerShell cmdlets

Политики внешнего доступа можно удалить с помощью Windows PowerShell и Remove-CsExternalAccessPolicy. Этот комлет можно запускать из Skype для бизнеса Server или удаленного сеанса Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Удаление определенной политики внешнего доступа

  - Эта команда удаляет политику внешнего доступа для узла Redmond:<br/><br/>Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Удаление всех политик внешнего доступа, применяемых к области каждого пользователя

  - Эта команда удаляет все политики внешнего доступа, настроенные на уровне пользователя:<br/><br/>Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Удаление всех политик внешнего доступа, в которых отключен внешний доступ пользователей

  - Эта команда удаляет все политики внешнего доступа, в который доступ внешних пользователей отключен:<br/><br/>Get-CsExternalAccessPolicy | Where-Object {$_. EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Дополнительные сведения см. в разделе Справка для [cmdlet Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)
