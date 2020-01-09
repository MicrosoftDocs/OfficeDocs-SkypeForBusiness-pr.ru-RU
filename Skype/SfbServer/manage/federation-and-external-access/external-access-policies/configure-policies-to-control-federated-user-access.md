---
title: Настройка политик управления доступом федеративных пользователей
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
localization_priority: Normal
description: 'Если вы настраиваете политики для поддержки взаимодействия с федеративными партнерами, политики применяются к пользователям федеративных доменов. '
ms.openlocfilehash: d9192589191590cd96f72323681ef4df6513e36d
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991764"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Настройка политик для управления доступом федеративных пользователей в Skype для бизнеса Server

Если вы настраиваете политики для поддержки взаимодействия с федеративными партнерами, политики применяются к пользователям федеративных доменов. Вы можете настроить одну или несколько политик доступа внешних пользователей, чтобы указать, могут ли пользователи федеративных доменов работать совместно с пользователями сервера Skype для бизнеса Server. Чтобы управлять федеративным доступом пользователей, вы можете настроить политики на уровне Global, site и User. Параметры политики Skype для бизнеса Server, примененные на одном уровне политики, могут переопределять параметры, примененные на другом уровне политики. Приоритет политики в Skype для бизнеса Server: политика пользователей (наибольшее влияние) переопределяет политику сайта, а затем политика сайта переопределяет глобальную политику (наименее влияние). То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.


> [!NOTE]  
> Вы можете настроить политики для управления доступом к федеративным пользователям, даже если вы не включили Федерацию для своей организации. Тем не менее, настроенные политики действуют только в том случае, если включена Федерация для вашей организации. Дополнительные сведения о включении Федерации можно найти в разделе [Включение и отключение удаленного доступа пользователей](../access-edge/enable-or-disable-remote-user-access.md).  Кроме того, если указать политику пользователей для управления доступом федеративного пользователя, политика применяется только для пользователей, которые включены в Skype для бизнеса Server и настроены на использование политики.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Настройка политики для поддержки доступа пользователей федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.

3.  На панели навигации слева выберите **внешний доступ для пользователей**и нажмите кнопку **Политика внешних доступа**.

4.  На странице " **политика внешней доступа** " выполните одно из указанных ниже действий.
    
      - Чтобы настроить глобальную политику для поддержки федеративного доступа пользователей, выберите глобальную политику, нажмите кнопку **изменить**, а затем выберите пункт **Показать подробности**.
    
      - Чтобы создать новую политику сайта, нажмите кнопку **создать**и выберите пункт **Политика сайта**. В разделе **выберите сайт**выберите нужный сайт из списка и нажмите кнопку **ОК**.
    
      - Чтобы создать политику пользователя, нажмите кнопку **создать**и выберите пункт **Политика пользователя**. В **новой политике внешнего доступа**Создайте уникальное имя в поле Name ( **имя** ), которое указывает политику пользователя (например, **енаблефедератедусерс** для политики пользователя, которая включает связь для пользователей федеративного домена).
    
      - Чтобы изменить существующую политику, выберите соответствующую политику, указанную в таблице, и нажмите кнопку **изменить**, а затем выберите команду **Показать подробности**.

5.  Необязательно Если вы хотите добавить или изменить описание, укажите сведения о политике в **описании**.

6.  Выполните одно из следующих действий:
    
      - Чтобы включить для политики федеративного доступа пользователей, установите флажок **включить связь с федеративными пользователями** .
    
      - Чтобы отключить федеративного доступа пользователей для политики, снимите флажок **включить связь с федеративными пользователями** .

7.  Нажмите **Исполнить**.

Для включения федеративного доступа пользователей необходимо также включить поддержку Федерации в Организации. Дополнительные сведения можно найти в разделе [Включение и отключение подключения к службам федерации и общедоступных мгновенных сообщений](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Если это политика пользователя, необходимо также применить политику для пользователей, которые должны быть доступны для совместной работы с федеративными пользователями. Подробности можно найти в разделе [назначение внешней политики доступа пользователей](assign-an-external-user-access-policy.md).

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Настройка существующей политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Запустите консоль управления сервером Skype для визитной: нажмите кнопку **Пуск**, выберите **все программы**, а затем — Skype для бизнеса **Server**, а затем — **Командная консоль управления Skype для бизнеса Server**.

3.  В командной консоли Skype для бизнеса Server введите следующую команду:
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > Параметр "Енаблепубликклаудаудиовидеоакцесс" не имеет соответствующего выделения на панели управления "Skype для бизнеса Server"


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Создание новой политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Запустите консоль управления в Skype для бизнеса Server: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Skype**для бизнеса Server, а затем — **Командная консоль управления Skype для бизнеса Server**.

3.  В командной консоли Skype для бизнеса Server введите следующую команду:
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Ниже приведен пример создания новой политики сайта.
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Удаление или сброс политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  В командной консоли Skype для бизнеса Server введите следующую команду:
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Пример сброса глобальной политики (Глобальная политика может быть удалена только из нее. Не удается удалить политику.
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Чтобы удалить политику сайта, введите:
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Удаление политики сайта Redmond. Чтобы удалить политику пользователя с именем Усереапполици, введите:
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>См. также


[Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Назначение политики доступа внешних пользователей](assign-an-external-user-access-policy.md)

[Управление федеративными доменами SIP для организации](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Управление федеративными поставщиками SIP в организации](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

