---
title: Настройка политик управления доступом федеративных пользователей
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'При настройке политик для поддержки обмена данными с федеративным партнерам политики применяются для пользователей из федеративных доменов. '
ms.openlocfilehash: fcb4b0651c81316e06ab659430c3b0e9e5664e64
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222991"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Настройка политик для управления доступом федеративных пользователей в Скайп для Business Server

При настройке политик для поддержки обмена данными с федеративным партнерам политики применяются для пользователей из федеративных доменов. Можно настроить один или несколько политик доступа внешних пользователей для управления ли пользователей из федеративных доменов можно совместно работать с вашей Скайп для пользователей Business Server. Для управления доступом федеративных пользователей, можно настроить политики на глобальном, сайта и на уровне пользователя. Скайп Business Server параметры политики, применяемые на одном уровне политики можно переопределить параметры, которые применяются на уровне другой политики. — Это Скайп для определения приоритета Business Server: политика пользователя (большинство влияют на то) переопределяет политики сайта, а затем политика сайта переопределяет глобальную политику (как минимум влияют на то). То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.


> [!NOTE]  
> Можно настроить политики для управления доступом федеративных пользователей, даже в том случае, если вы не включили федерации для вашей организации. Тем не менее политики, с помощью которых действуют только в том случае, если у вас есть федерации для вашей организации. Для получения дополнительных сведений о включении федерации видеть [включения или отключения удаленного доступа пользователей](../access-edge/enable-or-disable-remote-user-access.md).  Кроме того при указании политики пользователя для управления доступом федеративных пользователей, политика применяется только к пользователям, которые включены для Скайп для Business Server и настроен для использования политики.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Чтобы настроить политику для поддержки доступа пользователей федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.

3.  В левой панели навигации щелкните **Доступ для внешних пользователей**и нажмите кнопку **Политика внешнего доступа**.

4.  На странице **Политика внешнего доступа** выполните одно из следующих действий.
    
      - Чтобы настроить глобальную политику для поддержки доступа федеративных пользователей, щелкните глобальную политику, нажмите кнопку **Изменить**и нажмите кнопку **Показать подробности**.
    
      - Чтобы создать новую политику сайта, нажмите кнопку **Создать**и выберите **Политика сайта**. В **разделе Выбор сайта**выберите требуемый сайт в списке и нажмите кнопку **ОК**.
    
      - Чтобы создать новую политику пользователя, нажмите кнопку **Создать**и выберите **Политика пользователя**. В **Новую внешнюю политику доступа**создайте уникальное имя в поле **имя** , которое указывает, какой пользователь политики освещает вопросы (например, **EnableFederatedUsers** для политики пользователя, которая разрешается связь для пользователей федеративного домена).
    
      - Чтобы изменить существующую политику, щелкните соответствующую политику, перечисленных в таблице, нажмите кнопку **Изменить**и нажмите кнопку **Показать подробности**.

5.  (Необязательно) Если вы хотите добавить или изменить описание, укажите информацию о политике в **поле Описание**.

6.  Выполните одно из указанных ниже действий.
    
      - Чтобы включить доступ федеративных пользователей к политике, установите флажок **Разрешить взаимодействие с федеративными пользователями** .
    
      - Чтобы отключить доступ федеративных пользователей к политике, снимите флажок **Разрешить взаимодействие с федеративными пользователями** .

7.  Нажмите **Исполнить**.

Чтобы включить доступ федеративных пользователей, необходимо также включить поддержку федерации в вашей организации. Дополнительные сведения см [Включить или отключить федерацию и общедоступные службы обмена Мгновенными сообщениями](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Если это политику уровня пользователя, также необходимо применить политику для пользователей, которые необходимо иметь возможность совместной работы с федеративными пользователями. Дополнительные сведения см в [назначении политики доступа внешних пользователей](assign-an-external-user-access-policy.md).

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Чтобы настроить существующую политику с помощью Windows PowerShell для поддержки доступа пользователей из федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Запустите Скайп для консоли Server бизнес: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп для Business Server**и нажмите кнопку **Скайп для консоли Business Server**.

3.  Введите следующие команды в Скайп для консоли Business Server.
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > Параметр «EnablePublicCloudAudioVideoAccess» не имеет соответствующего выбора в Скайп панели управления Business Server


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Чтобы создать новую политику с помощью Windows PowerShell для поддержки доступа пользователей из федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Запустите Скайп для консоли Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп Microsoft для Business Server**и нажмите кнопку **Скайп для консоли Business Server**.

3.  Введите следующие команды в Скайп для консоли Business Server.
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Пример создания новой политики сайта:
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Чтобы удалить или сбросить политику с помощью Windows PowerShell для поддержки доступа пользователей из федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Введите следующую команду в Скайп для консоли Business Server
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Пример Сброс глобальной политики (глобальной политики может иметь только его параметру удаленным. Политика не может быть удалена):
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Чтобы удалить политику сайта, введите следующую команду:
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Удаление политики сайта Redmond. Чтобы удалить политику уровня пользователя с именем UserEAPPolicy, введите следующую команду:
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>См. также


[Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Назначьте политику доступа внешних пользователей](assign-an-external-user-access-policy.md)

[Управление федеративными доменами SIP для организации](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Управление федеративными поставщиками SIP в организации](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[Новый CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

