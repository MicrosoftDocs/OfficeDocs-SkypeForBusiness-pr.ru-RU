---
title: Сброс глобальной политики для доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Полностью удалить глобальную политику нельзя. Использование **параметра Delete** в глобальной политике только сбрасывает глобальную политику в параметры по умолчанию, которые не включают поддержку любых внешних параметров доступа пользователей.
ms.openlocfilehash: e65eb4f2a87789b22654b8de5e3681b1dda47d1a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416562"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Сброс глобальной политики для внешнего доступа к пользователям в Skype для бизнеса Server 

Если созданы или настроены внешние политики доступа пользователей, которые больше не нужно использовать, можно использовать следующие методы:

  - Удалите любую созданную политику сайта или пользователя.

  - Сбросьте глобальную политику до значений по умолчанию. Параметры глобальной политики по умолчанию запрещают любой внешний доступ пользователей. Глобальная политика не может быть удалена.

Полностью удалить глобальную политику нельзя. Параметр **Delete** в глобальной политике сбрасывает глобальную политику только в параметры по умолчанию, которые не включают поддержку любых внешних параметров доступа пользователей.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Восстановление параметров глобальной политики по умолчанию

1.  Учетная запись пользователя, которая входит в группу RTCUniversalServerAdmins или имеет эквивалентные права пользователя или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления.

3.  В левой панели навигации щелкните элемент **Доступ внешних пользователей**, а затем выберите **Политика внешнего доступа**.

4.  На вкладке **Политика внешнего доступа** щелкните глобальную политику, нажмите кнопку **Изменить** (Изменить) и затем нажмите **Удалить**.

5.  При отображении запроса на подтверждение нажмите кнопку **ОК**. В верхней части страницы появится сообщение о сбросе глобальной политики.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Сброс глобальной политики внешнего доступа с помощью Windows PowerShell cmdlets

Глобальную политику внешнего доступа можно сбросить с помощью Windows PowerShell и Remove-CsExternalAccessPolicy. Этот комлет можно выполнить либо из Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Сброс глобальной политики внешнего доступа

  - Следующая команда сбрасывает глобальную политику внешнего доступа:<br/><br/>Remove-CsExternalAccessPolicy -Identity "global"

Дополнительные сведения см. в разделе Справка для [cmdlet Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) .
