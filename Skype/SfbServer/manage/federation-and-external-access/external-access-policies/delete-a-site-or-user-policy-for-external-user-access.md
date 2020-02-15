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
description: Вы можете удалить любую политику сайта или пользователя, указанную на панели управления Skype для бизнеса Server на странице Политика внешнего доступа.
ms.openlocfilehash: ae0a0499e7497c4d62884860a2730960e5070ac8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041238"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Удаление сайта или пользовательской политики для доступа внешних пользователей

Если были созданы или настроены политики внешнего доступа пользователей, которые больше не нужно использовать, выполните следующие действия.

  - Удалите любую созданную политику сайта или пользователя.

  - Сбросьте глобальную политику до значений по умолчанию. Параметры глобальной политики по умолчанию запрещают любой внешний доступ пользователей. Саму глобальную политику удалить невозможно.


Вы можете удалить любую политику сайта или пользователя, указанную на панели управления Skype для бизнеса Server на странице **Политика внешнего доступа** . При удалении глобальной политики она на самом деле не удаляется, а восстанавливаются параметры по умолчанию, не включающие поддержку доступа внешних пользователей. Дополнительные сведения о сбросе глобальной политики приведены в разделе [Сброс глобальной политики для доступа внешних пользователей](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Удаление политика узла или пользователя для доступа внешних пользователей

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Skype для бизнеса Server. 

3.  Щелкните **Доступ для внешних пользователей** и выберите **Политика внешнего доступа**.

4.  На вкладке **Политика внешнего доступа** щелкните политику узла или пользователя, которую нужно удалить, нажмите кнопку **Изменить** и затем нажмите **Удалить**.

5.  При отображении запроса на подтверждение нажмите кнопку **ОК**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Удаление политик ПИН-кодов с помощью командлетов Windows PowerShell

Политики внешнего доступа можно удалить с помощью Windows PowerShell и командлета Remove – CsExternalAccessPolicy. Этот командлет можно запустить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Удаление определенной политики внешнего доступа

  - Эта команда удаляет политику внешнего доступа для узла Redmond:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Удаление всех политик внешнего доступа, примененных к области "на пользователя"

  - Эта команда удаляет все политики внешнего доступа, настроенные на уровне пользователя:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Удаление всех политик внешнего доступа, для которых отключен доступ извне пользователя

  - Эта команда удаляет все политики внешнего доступа, в который доступ внешних пользователей отключен:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Remove – CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .
