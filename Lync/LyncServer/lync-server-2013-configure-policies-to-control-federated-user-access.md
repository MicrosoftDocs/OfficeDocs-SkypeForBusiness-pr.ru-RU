---
title: 'Lync Server 2013: настройка политик управления доступом федеративных пользователей'
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
ms.openlocfilehash: e1aeb1b29637fd3f4a8add770470069e8b4a6eb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a>Настройка политик управления доступом федеративных пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-02-05_

Если вы настраиваете политики для поддержки взаимодействия с федеративными партнерами, политики применяются к пользователям федеративных доменов. Вы можете настроить одну или несколько политик доступа внешних пользователей, чтобы указать, могут ли пользователи федеративных доменов работать совместно с пользователями Lync Server 2013. Чтобы управлять федеративным доступом пользователей, вы можете настроить политики на уровне Global, site и User. Параметры политики сервера Lync Server, примененные на одном уровне политики, могут переопределять параметры, примененные на другом уровне политики. Приоритет политики Lync Server: политика пользователей (наибольшее влияние) переопределяет политику сайта, а затем политика сайта переопределяет глобальную политику (наименее влияние). То есть, чем ближе параметр политики к объекту, на который она влияет, тем больше влияния она оказывает на объект.

<div>


> [!NOTE]  
> Вы можете настроить политики для управления доступом к федеративным пользователям, даже если вы не включили Федерацию для своей организации. Тем не менее, настроенные политики действуют только в том случае, если включена Федерация для вашей организации. Дополнительные сведения о включении Федерации можно найти <A href="lync-server-2013-enable-or-disable-remote-user-access.md">в разделе Включение и отключение удаленного доступа пользователей в Lync Server 2013</A> в документации по развертыванию или документации по эксплуатации. Кроме того, если вы укажете политику пользователей для управления доступом пользователей Федерации, политика применяется только для пользователей, которые включены в Lync Server 2013 и настроены на использование политики.



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Настройка политики для поддержки доступа пользователей федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

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

Для включения федеративного доступа пользователей необходимо также включить поддержку Федерации в Организации. Дополнительные сведения можно найти [в разделе Включение и отключение службы подключения к службам федерации и общедоступных сообщений в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).

Если это политика пользователя, необходимо также применить политику для пользователей, которые должны быть доступны для совместной работы с федеративными пользователями. Подробности можно найти в разделе [назначение внешней политики доступа пользователю Lync в Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Настройка существующей политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  В командной консоли Lync Server введите следующую команду:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Пример команды, которая позволяет настроить глобальную политику для доступа федеративных пользователей на разрешенные, КСМПП доступ к домену для включения, доступа к общедоступным поставщикам для включения и предоставления возможности использования звуковых и видеофайлов для общедоступных поставщиков, поддерживающих этот интерфейс.
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > Параметр "Енаблепубликклаудаудиовидеоакцесс" не имеет соответствующего выделения на панели управления Lync Server.

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Создание новой политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  В командной консоли Lync Server введите следующую команду:
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Ниже приведен пример создания новой политики сайта.
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Удаление или сброс политики с помощью Windows PowerShell для поддержки доступа пользователей федеративных доменов

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Введите следующую команду в командной консоли Lync Server Management Shell
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    Пример сброса глобальной политики (Глобальная политика может быть удалена только из нее. Не удается удалить политику.
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    Чтобы удалить политику сайта, введите:
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    Удаление политики сайта Redmond. Чтобы удалить политику пользователя с именем Усереапполици, введите:
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a>См. также


[Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[Назначение политики доступа внешних пользователей пользователю, разрешенному для Lync в Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[Управление федеративными доменами SIP для организации в Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Управление федеративными поставщиками SIP в организации в Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

