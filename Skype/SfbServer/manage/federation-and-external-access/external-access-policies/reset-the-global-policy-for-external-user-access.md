---
title: Сброс глобальной политики для доступа внешних пользователей
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: Вы не можете полностью удалить глобальную политику. При использовании команды **Удалить** для глобальной политики восстанавливаются параметры по умолчанию, не поддерживающие какие-либо параметры доступа внешних пользователей.
ms.openlocfilehash: 824d9f6c924a197a379f668263a23a6df89c27a980c82ea4d13abdd8621968da
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343433"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Сброс глобальной политики для внешнего доступа к пользователям в Skype для бизнеса Server 

Если были созданы или настроены политики внешнего доступа пользователей, которые больше не нужно использовать, выполните следующие действия.

  - Удалите любую созданную политику сайта или пользователя.

  - Сбросьте глобальную политику до значений по умолчанию. Параметры глобальной политики по умолчанию запрещают любой внешний доступ пользователей. Саму глобальную политику удалить невозможно.

Вы не можете полностью удалить глобальную политику. При использовании команды **Удалить** для глобальной политики восстанавливаются параметры по умолчанию, не поддерживающие какие-либо параметры доступа внешних пользователей.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Восстановление параметров глобальной политики по умолчанию

1.  С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления.

3.  В левой панели навигации щелкните элемент **Доступ внешних пользователей**, а затем выберите **Политика внешнего доступа**.

4.  На вкладке **Политика внешнего доступа** щелкните глобальную политику, нажмите кнопку **Изменить** (Изменить) и затем нажмите **Удалить**.

5.  При отображении запроса на подтверждение нажмите кнопку **ОК**. В верхней части страницы появится сообщение о сбросе глобальной политики.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Сброс глобальной политики внешнего доступа с помощью Windows PowerShell cmdlets

Глобальную политику внешнего доступа можно сбросить с помощью Windows PowerShell и Remove-CsExternalAccessPolicy. Этот комлет можно запускать из Skype для бизнеса Server или удаленного сеанса Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Сброс глобальной политики внешнего доступа

  - Следующая команда сбрасывает глобальную политику внешнего доступа:
    
        Remove-CsExternalAccessPolicy -Identity "global"

Дополнительные сведения см. в разделе Справка для [cmdlet Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)