---
title: 'Lync Server 2013: Настройка политик для управления доступом федеративных пользователей'
description: 'Lync Server 2013: Настройка политик для управления доступом федеративного пользователя.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d69f35baa16086b0c4e93a2a015474f87e08b736
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548745"
---
# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a>Настройка политик для управления доступом федеративных пользователей в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-02-05_

При настройке политик для поддержки связи с федеративными партнерами эти политики применяются к пользователям федеративных доменов. Можно настроить одну или несколько политик доступа внешних пользователей, чтобы управлять тем, могут ли пользователи федеративных доменов совместно работать с пользователями Lync Server 2013. Для управления доступом федеративных пользователей можно настроить политики на глобальном уровне, уровне сайта и уровне пользователей. Параметры политики Lync Server, применяемые на одном уровне политики, могут переопределять параметры, применяемые на другом уровне политики. Приоритет политики Lync Server: политика пользователя (наиболее влияние) переопределяет политику сайта, а затем политика сайта переопределяет глобальную политику (наименее влияние). То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.

<div>


> [!NOTE]  
> Можно настроить политики для управления доступом федеративных пользователей, даже если федерация не была включена для данной организации. Однако настроенные политики вступают в силу только при включении федерации для организации. Подробнее о включении Федерации можно узнать в статье <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Включение и отключение удаленного доступа пользователей в Lync Server 2013</A> в документации по развертыванию или документации по операциям. Кроме того, если указать политику пользователя для управления доступом федеративного пользователя, политика применяется только к пользователям, для которых включена поддержка Lync Server 2013 и настроено на использование политики.



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Чтобы настроить политику для поддержку доступа пользователей федеративных доменов

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

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

Чтобы включить доступ федеративных пользователей, необходимо также включить поддержку федераций в организации. Дополнительные сведения: [Включение и отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).

Если это политика пользователей, необходимо также применить эту политику к пользователям, которые должны работать совместно с федеративными пользователями. Подробнее: [Назначение политики доступа внешних пользователей пользователю, поддерживающему Lync, в Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Настройка существующей политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Введите в командной консоли Lync Server следующую команду:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Пример команды, которая задает глобальную политику для включения доступа федеративных пользователей, включения доступа из доменов XMPP, включения удаленного доступа пользователей, включения доступа из систем общедоступных поставщиков и предоставления возможности использовать аудио и видео при работе с поставщиками, обеспечивающими такую поддержку:
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > Параметр "Енаблепубликклаудаудиовидеоакцесс" не имеет соответствующего выбора в панели управления Lync Server

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Создание новой политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Введите в командной консоли Lync Server следующую команду:
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Пример создания новой политики сайта:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Удаление или сброс политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Введите следующую команду в командной консоли Lync Server.
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    Пример сброса глобальной политики (из глобальной политики можно только убрать параметр. Саму политику удалить невозможно):
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    Чтобы удалить политику сайта, введите следующее:
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    Удаляет политику сайта Redmond. Чтобы удалить политику пользователей с именем UserEAPPolicy, введите следующую команду:
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a>См. также


[Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[Назначение политики доступа внешних пользователей пользователю, поддерживающему Lync, в Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[Управление федеративными доменами SIP для Организации в Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Управление федеративными поставщиками SIP для Организации в Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[Set — CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New — CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove — CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Granting — CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

