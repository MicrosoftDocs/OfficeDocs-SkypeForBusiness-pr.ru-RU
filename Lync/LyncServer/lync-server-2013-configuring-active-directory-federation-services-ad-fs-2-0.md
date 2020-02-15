---
title: 'Lync Server 2013: Настройка служб федерации Active Directory (AD FS 2,0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba3a74f59bc996defcd9baee9162d034ab2178eb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029720"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>Настройка служб федерации Active Directory (AD FS 2,0) для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-07-03_

В следующем разделе описано, как настроить службы федерации Active Directory (AD FS 2,0) для поддержки многофакторной проверки подлинности. Сведения о том, как установить AD FS 2,0, можно найти в статье AD FS 2,0 пошаговые инструкции и руководства по [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).

<div class="">


> [!NOTE]  
> При установке служб федерации Active Directory 2,0 не используйте Диспетчер Windows Server для добавления роли служб федерации Active Directory. Вместо этого скачайте и установите пакет RTW 2,0 служб федерации Active Directory на сайте <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>.



</div>

<div>


**Настройка AD FS для двухфакторной проверки подлинности**

1.  Выполните вход на компьютер с AD FS 2,0 с помощью учетной записи администратора домена.

2.  Запуск Windows PowerShell.

3.  В командной строке Windows PowerShell выполните следующую команду:
    ```powershell
    add-pssnapin Microsoft.Adfs.PowerShell
    ```
4.  Установите связь с каждым сервером Lync Server 2013 с накопительными пакетами обновления для Lync Server 2013: Июль 2013 директор, корпоративный пул и сервер Standard Edition, для которых будет включена пассивная проверка подлинности, выполнив следующую команду, заменив имя сервера, относящееся к конкретному развертыванию:
    ```powershell
    Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
     ```
5.  В меню Администрирование откройте консоль управления AD FS 2,0.

6.  Разверните узел **отношения** \> доверия отношения **доверия с проверяющей стороной**.

7.  Убедитесь, что для Lync Server 2013 с накопительными пакетами обновления для Lync Server 2013 создано новое отношение доверия: Июль 2013 Корпоративный пул или сервер Standard Edition.

8.  Создайте и назначьте правило авторизации выдачи для отношения доверия с проверяющей стороной с помощью Windows PowerShell, выполнив следующие команды:
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  Создайте и назначьте правило преобразования выдачи для отношения доверия с проверяющей стороной с помощью Windows PowerShell, выполнив следующие команды:
    
       ```powershell
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. В консоли управления AD FS 2,0 щелкните правой кнопкой мыши отношение доверия с проверяющей стороной и выберите команду **изменить правила утверждений**.

11. Выберите вкладку **правила авторизации выдачи** и убедитесь, что новое правило авторизации было успешно создано.

12. Перейдите на вкладку **правила преобразования выдачи** и убедитесь, что новое правило преобразования успешно создано.

</div>

</div>

<span> </span>

</div>

</div>

</div>

