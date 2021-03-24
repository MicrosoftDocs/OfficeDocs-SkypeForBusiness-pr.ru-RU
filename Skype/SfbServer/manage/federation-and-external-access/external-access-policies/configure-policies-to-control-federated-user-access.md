---
title: Настройка политик для управления доступом федеративных пользователей
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
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
description: 'При настройке политик для поддержки связи с федеративными партнерами эти политики применяются к пользователям федеративных доменов. '
ms.openlocfilehash: 6107615767d0360180baf9f22d5fddc6a5f8e565
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099045"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Настройка политик для управления федерадным доступом пользователей в Skype для бизнеса Server

При настройке политик для поддержки связи с федеративными партнерами эти политики применяются к пользователям федеративных доменов. Вы можете настроить одну или несколько внешних политик доступа к пользователю, чтобы определить, могут ли пользователи федерадных доменов сотрудничать с пользователями Skype для бизнеса Server. Для управления доступом федеративных пользователей можно настроить политики на глобальном уровне, уровне сайта и уровне пользователей. Параметры политики Skype для бизнеса Server, применяемые на одном уровне политики, могут переопределять параметры, применяемые на другом уровне политики. Приоритет политик в Skype для бизнеса Server: политика пользователя (наибольшее влияние) переопределяет политику сайта, а политика сайта переопределяет глобальную политику (наименьшее влияние).  То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.


> [!NOTE]  
> Можно настроить политики для управления доступом федеративных пользователей, даже если федерация не была включена для данной организации. Однако настроенные политики вступают в силу только при включении федерации для организации. Сведения о включаемой федерации см. в материале [Включение или отключение удаленного доступа к пользователю.](../access-edge/enable-or-disable-remote-user-access.md)  Кроме того, если указать политику пользователя для управления федерадным доступом пользователей, эта политика применяется только к пользователям, которые включены для Skype для бизнес-сервера и настроены на использование политики.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Чтобы настроить политику для поддержку доступа пользователей федеративных доменов

1.  С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.

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

Чтобы включить доступ федеративных пользователей, необходимо также включить поддержку федераций в организации. Подробные сведения см. в материале [Enable or disable federation and public IM connectivity.](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

Если это политика пользователей, необходимо также применить эту политику к пользователям, которые должны работать совместно с федеративными пользователями. Дополнительные сведения см. в [материале Назначение внешней политики доступа к пользователю.](assign-an-external-user-access-policy.md)

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Настройка существующей политики с Windows PowerShell для поддержки доступа пользователей федератированных доменов

1.  С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Запустите оболочку управления серверами в Skype для Busines: нажмите кнопку Начните, щелкните Все **программы,** щелкните **Skype для** бизнес-сервера, а затем нажмите кнопку Skype для управления **бизнес-сервером.**

3.  Введите следующее в оболочке управления skype для бизнес-серверов:
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > Параметр EnablePublicCloudAudioVideoAccess не имеет соответствующего выбора в панели управления Skype для бизнес-серверов


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Создание новой политики с Windows PowerShell для поддержки доступа пользователей федератированных доменов

1.  С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните **Microsoft Skype для** бизнес-сервера, а затем нажмите кнопку Skype для управления бизнес-сервером. 

3.  Введите следующее в оболочке управления skype для бизнес-серверов:
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Пример создания новой политики сайта:
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Удаление или сброс политики с Windows PowerShell для поддержки доступа пользователей федератированных доменов

1.  С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Введите следующее в оболочке управления Skype для бизнес-серверов
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Пример сброса глобальной политики (из глобальной политики можно только убрать параметр. Саму политику удалить невозможно):
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Чтобы удалить политику сайта, введите следующее:
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Удаляет политику сайта Redmond. Чтобы удалить политику пользователей с именем UserEAPPolicy, введите следующую команду:
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>См. также


[Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Назначение политики доступа внешних пользователей](assign-an-external-user-access-policy.md)

[Управление федеративными доменами SIP для организации](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Управление федеративными поставщиками SIP в организации](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](/powershell/module/skype/Grant-CsExternalAccessPolicy)  
