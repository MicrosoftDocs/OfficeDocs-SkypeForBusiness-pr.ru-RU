---
title: Настройка политик для управления доступом федеративных пользователей
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
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
description: 'При настройке политик для поддержки связи с федеративными партнерами эти политики применяются к пользователям федеративных доменов. '
ms.openlocfilehash: 447aad751ce6fc91bf2d6b80c8a14e92f9d4da82
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037409"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Настройка политик для управления доступом федеративных пользователей в Skype для бизнеса Server

При настройке политик для поддержки связи с федеративными партнерами эти политики применяются к пользователям федеративных доменов. Можно настроить одну или несколько политик доступа внешних пользователей, чтобы управлять тем, могут ли пользователи федеративных доменов совместно работать с пользователями Skype для бизнеса Server. Для управления доступом федеративных пользователей можно настроить политики на глобальном уровне, уровне сайта и уровне пользователей. Параметры политики Skype для бизнеса Server, применяемые на одном уровне политики, могут переопределять параметры, применяемые на другом уровне политики. Приоритет политик в Skype для бизнеса Server: политика пользователя (наибольшее влияние) — переопределяет политику сайта, а затем политика сайта переопределяет глобальную политику (наименее влияние). Это означает, что параметр политики ближе к объекту, на который влияет политика, чем больше влияет на объект.


> [!NOTE]  
> Можно настроить политики для управления доступом федеративных пользователей, даже если федерация не была включена для данной организации. Однако настроенные политики вступают в силу только при включении федерации для организации. Подробнее о включении Федерации можно узнать в статье [Включение и отключение удаленного доступа пользователей](../access-edge/enable-or-disable-remote-user-access.md).  Кроме того, если указать политику пользователя для управления доступом федеративного пользователя, политика применяется только к пользователям, для которых включена поддержка Skype для бизнеса Server и настроено на использование политики.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Чтобы настроить политику для поддержку доступа пользователей федеративных доменов

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Skype для бизнеса Server.

3.  На левой панели навигации щелкните **Внешний доступ пользователей**, затем щелкните **Политика внешнего доступа**.

4.  На странице **Политика внешнего доступа** выполните одно из следующих действий.
    
      - Чтобы настроить глобальную политику для поддержки доступа федеративных пользователей? щелкните глобальную политику, щелкните **Изменить**, затем щелкните **Подробнее**.
    
      - Чтобы создать новую политику сайта, щелкните **Создать**, затем щелкните **Политика сайта**. В разделе **Выбор сайта** щелкните подходящий сайт в списке и нажмите кнопку **ОК**.
    
      - Чтобы создать новую политику пользователей, щелкните **Создать**, затем щелкните **Политика сайта**. В разделе **Новая политика внешнего доступа** создайте уникальное имя в поле **Имя**, которое указывает, что охватывается политикой пользователей (например, **EnableFederatedUsers** для политики пользователей, которая разрешает связь с пользователями федеративных доменов).
    
      - Чтобы изменить существующую политику, щелкните ее в таблице, щелкните **Изменить**, затем **Показать сведения**.

5.  (Необязательно) Если необходимо добавить или изменить описание, укажите сведения для этой политики в пункте **Описание**.

6.  Выполните одно из следующих действий.
    
      - Чтобы включить доступ федеративных пользователей к политике, установите флажок **Разрешить взаимодействие с федеративными пользователями**.
    
      - Чтобы отключить доступ федеративных пользователей к политике, снимите флажок **Разрешить взаимодействие с федеративными пользователями**.

7.  Нажмите кнопку **Сохранить**.

Чтобы включить доступ федеративных пользователей, необходимо также включить поддержку федераций в организации. Дополнительные сведения см. в статье [Включение и отключение Федерации и общедоступной службы обмена мгновенными сообщениями](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Если это политика пользователей, необходимо также применить эту политику к пользователям, которые должны работать совместно с федеративными пользователями. Дополнительные сведения см. в разделе [Назначение политики доступа внешних пользователей](assign-an-external-user-access-policy.md).

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Настройка существующей политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Запустите консоль управления сервером Skype для Stress Server: нажмите кнопку **Пуск**, последовательно выберите пункты **все программы**, **Skype для бизнеса Server**и **консоль управления Skype для бизнеса Server**.

3.  Введите следующую команду в командной консоли Skype для бизнеса Server:
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > Параметр "Енаблепубликклаудаудиовидеоакцесс" не имеет соответствующего выбора в панели управления Skype для бизнеса Server


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Создание новой политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Запустите консоль управления Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, затем **Microsoft Skype для бизнеса Server**, а затем выберите пункт **Командная консоль Skype для бизнеса Server**.

3.  Введите следующую команду в командной консоли Skype для бизнеса Server:
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Пример создания новой политики сайта:
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Удаление или сброс политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Введите следующее в командной консоли Skype для бизнеса Server
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Пример сброса глобальной политики (из глобальной политики можно только убрать параметр. Саму политику удалить невозможно):
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Чтобы удалить политику сайта, введите следующее:
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Удаляет политику сайта Redmond. Чтобы удалить политику пользователей с именем UserEAPPolicy, введите следующую команду:
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>См. также


[Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Назначение политики доступа внешних пользователей](assign-an-external-user-access-policy.md)

[Управление федеративными доменами SIP для Организации](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Управление федеративными поставщиками SIP для Организации](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set — CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New — CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove — CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Granting — CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

