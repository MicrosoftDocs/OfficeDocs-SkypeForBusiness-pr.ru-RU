---
title: 'Lync Server 2013: Настройка служб федерации Active Directory (AD FS 2,0)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Active Directory Federation Services (AD FS 2.0)
ms:assetid: 0ba8657f-55b8-41b3-960c-fdc5eeee6978
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308561(v=OCS.15)
ms:contentKeyID: 54973682
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 924f9c1b6e7fe64186eeee6a34364417d497866b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-active-directory-federation-services-ad-fs-20-for-lync-server-2013"></a>Настройка служб федерации Active Directory (AD FS 2,0) для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-07-03_

В этом разделе рассматривается настройка служб федерации Active Directory (AD FS 2.0) для поддержки многофакторной проверки подлинности. Сведения о том, как установить AD FS 2,0, приведены пошаговые инструкции для AD FS 2,0 и инструкции по [http://go.microsoft.com/fwlink/p/?LinkId=313374](http://go.microsoft.com/fwlink/p/?linkid=313374).

<div class="">


> [!NOTE]  
> При установке AD FS 2.0 не добавляйте роль службы федерации Active Directory с помощью диспетчера серверов Windows. Вместо этого загрузите и установите пакет служб федерации Active Directory 2,0 RTW at <A href="http://go.microsoft.com/fwlink/p/?linkid=313375">http://go.microsoft.com/fwlink/p/?LinkId=313375</A>.



</div>

<div>


**Настройка AD FS для двухфакторной проверки подлинности**

1.  Войдите в систему на компьютере с AD FS 2.0 с помощью учетной записи администратора домена.

2.  Запустите Windows PowerShell.

3.  Введите в командной строке Windows PowerShell следующую команду:
    
        add-pssnapin Microsoft.Adfs.PowerShell

4.  Установите связь с каждым сервером Lync Server 2013 с накопительными обновлениями для Lync Server 2013: Июль 2013 режиссер, корпоративный пул и сервер Standard Edition, для которых будет включена пассивная проверка подлинности, выполнив указанную ниже команду, заменив имя сервера, относящееся к развертыванию.
    
        Add-ADFSRelyingPartyTrust -Name LyncPool01-PassiveAuth -MetadataURL https://lyncpool01.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  Запустите консоль управления AD FS 2.0 в меню "Средства администрирования".

6.  Разверните элемент \> **доверия проверяющей стороны** **отношений доверия** .

7.  Убедитесь в том, что для Lync Server 2013 установлены новые доверительные отношения с накопительными обновлениями для Lync Server 2013: Июль 2013 корпоративным пулом или Standard Edition Server.

8.  С помощью Windows PowerShell и следующих команд создайте и назначьте для отношения доверия с проверяющей стороны правило утверждения авторизации:
    
       ```
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.microsoft.com/authorization/claims/permit", Value = "true");'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth 
        -IssuanceAuthorizationRules $IssuanceAuthorizationRules
       ```

9.  С помощью Windows PowerShell и следующих команд создайте и назначьте для отношения доверия с проверяющей стороны правило утверждения преобразования:
    
       ```
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.microsoft.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName LyncPool01-PassiveAuth -IssuanceTransformRules $IssuanceTransformRules
       ```

10. В консоли управления AD FS 2.0 щелкните отношение доверия с проверяющей стороной правой кнопкой мыши и выберите команду **редактирования правил утверждений**.

11. Перейдите на вкладку **правил разрешения выпуска** и убедитесь в том, что новое правило разрешения успешно создано.

12. Перейдите на вкладку **правил преобразования выпуска** и убедитесь в том, что новое правило преобразования успешно создано.

</div>

</div>

<span> </span>

</div>

</div>

</div>

