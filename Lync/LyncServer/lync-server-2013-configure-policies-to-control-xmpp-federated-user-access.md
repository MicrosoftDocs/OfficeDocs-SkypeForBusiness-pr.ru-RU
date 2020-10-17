---
title: 'Lync Server 2013: Настройка политик для управления доступом федеративного пользователя XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7cc0eec0dc1371e27834dda69b25a32b9346ab5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535226"
---
# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Настройка политик для управления доступом федеративных пользователей XMPP в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Это Предварительная документация, которая может быть изменена. Пустые разделы включены в качестве заполнителей.

При настройке политик для поддержки федеративных партнеров XMPP (расширяемый протокол обмена сообщениями и контроля присутствия) политики применяют к пользователям федеративных доменов XMPP, а не к пользователям поставщиков (например, Windows Live) услуг обмена мгновенными сообщениями по протоколу SIP (Session Initiation Protocol) или федеративных доменов SIP. **Федеративного партнера XMPP** настраивают для каждого федеративного домена XMPP, в котором пользователям разрешается добавлять контакты и взаимодействовать с ними. Политики федеративных партнеров XMPP доступны только в одной области, хотя политика не определяется как глобальная, она действует как глобальная политика. Чтобы определить для федеративных партнеров XMPP глобальную политику, политику уровня сайта или пользователя, настраивают область действия политики путем создания и настройки политики внешнего доступа для требуемой области действия. Сведения о типах политик, которые можно настроить для внешнего доступа и Федерации, приведены в статье [Управление федерациями и внешним доступом к Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) в документации по операциям.

<div>


> [!NOTE]  
> Все политики <STRONG>федерации и внешнего доступа</STRONG> применяются через предоставление внутренних полос. Политики, которые применяются к пользователям, принадлежат сайту или являются глобальными по области действия, доводятся до клиента во время входа в систему. Политики для управления доступом федеративных партнеров XMPP можно настроить, даже если для вашей организации не включена XMPP-федерация. Однако настраиваемые политики вступают в действие, только когда для организации развернута, включена и настроена федерация партнеров XMPP. Подробные сведения о развертывании и настройке Федерации XMPP Partner приведены в статье <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Настройка Федерации SIP, Федерации XMPP и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013</A> в документации по развертыванию. Кроме того, если вы укажете политику пользователя в политике внешнего доступа для управления федеративными партнерами XMPP, политика применяется только к пользователям, поддерживающим Lync Server 2013 и настроенным на использование политики.



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>Чтобы изменить глобальную политику для федеративных партнеров XMPP

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Внешний доступ пользователей**, затем щелкните **Политика внешнего доступа**.

4.  На странице **Политика внешнего доступа** выполните следующие действия в отношении глобальной политики:

5.  Выберите глобальную политику, щелкните **Изменить**, а затем щелкните "Подробнее".

6.  Предоставьте описание глобальной политики (по желанию).

7.  Выберите настройку **Разрешить связь с федеративными пользователями**.

8.  Выберите пункт **Разрешить связь с федеративными пользователями XMPP**.

9.  Щелкните **Зафиксировать**, чтобы сохранить изменения в глобальной политике.

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>Чтобы создать политику уровня сайта или пользователя для федеративных партнеров XMPP

1.  Щелкните **Создать**, а затем щелкните **Политика уровня сайта** или **Политика уровня пользователя**. В разделе **Выбор сайта** щелкните подходящий сайт в списке и нажмите кнопку **ОК**.

2.  Предоставьте описание политики сайта (по желанию).

3.  В политике уровня сайта или пользователя выберите настройку **Разрешить связь с федеративными пользователями**.

4.  Выберите пункт **Разрешить связь с федеративными пользователями XMPP**.

5.  Щелкните **Зафиксировать**, чтобы сохранить изменения в политике сайта или пользователя.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>Чтобы изменить существующую политику для федеративных партнеров XMPP

1.  Чтобы изменить существующую политику, выберите соответствующую политику в списке, щелкните **Изменить**, а затем щелкните **Подробнее**.

2.  Измените или обновите описание политики (по желанию).

3.  Выберите или отмените выбор настройки **Разрешить связь с федеративными пользователями**.

4.  выберите или отмените выбор настройки **Разрешить связь с федеративными пользователями XMPP**.

5.  Щелкните **Зафиксировать**, чтобы сохранить изменения в политике.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Изменение существующей политики для федеративных партнеров XMPP с помощью Windows PowerShell

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Введите в командной консоли Lync Server следующую команду:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Пример команды, которая задаст глобальную политику для доступа федеративных пользователей в true (Enabled) и доступ домена XMPP к true (включено):
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>Создание политики сайта или пользователя для федеративных партнеров XMPP с помощью Windows PowerShell

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Введите в командной консоли Lync Server следующую команду:
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Пример команды, устанавливающей политику уровня сайта для сайта Редмонда с целью разрешить доступ федеративных пользователей и разрешить доступ в XMPP-домен:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Удаление существующей политики для федеративных партнеров XMPP с помощью Windows PowerShell

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Введите в командной консоли Lync Server следующую команду:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Пример команды, удаляющей политику уровня пользователя:
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Пример команды, сбрасывающей глобальную политику в настройки по умолчанию:
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>См. также


[Назначение политики доступа внешних пользователей пользователю, поддерживающему Lync, в Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Включение или отключение Федерации и общедоступной службы обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Управление федеративными партнерами XMPP в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
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

