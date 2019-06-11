---
title: 'Lync Server 2013: настройка политик управления доступом федеративных XMPP-пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ec90a1b079935713ce6f13e7b74763e7004dedf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841343"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Настройка политик управления доступом федеративных XMPP-пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Это предварительная редакция документации и она может меняться. Пустые разделы добавлены в качестве заполнителей.

Если вы настраиваете политики для поддержки федеративных партнеров по протоколу расширенного обмена сообщениями (КСМПП), политики применяются к пользователям КСМПП федеративных доменов, но не к пользователям служб мгновенных сообщений в протоколе запуска сеансов (SIP). (например, Windows Live) или федеративные домены SIP. Вы настраиваете **федеративного партнера КСМПП** для каждого КСМПП федеративного домена, с которым вы хотите разрешить пользователям добавлять контакты и взаимодействовать с ними. Политики федеративного партнера КСМПП доступны только в одной области, хотя она не определена как Глобальная, действует как Глобальная политика. Чтобы определить политику глобального, сайта или пользователя для партнеров Федерации КСМПП, настройте область политики, сначала создав и настроив политику внешнего доступа для нужной области. Подробные сведения о типах политик, которые можно настроить для внешнего доступа и интеграции, приведены в разделе [Управление интеграцией и внешним доступом к Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) в документации по эксплуатации.

<div>


> [!NOTE]  
> Все политики <STRONG>Федерации и внешнего доступа</STRONG> применяются при подготовке по каналу. Политики, которые применяются к пользователю, принадлежат сайту или являются глобальными в области, передаются клиенту во время входа. Вы можете настроить политики для управления доступом КСМПП федеративного партнера, даже если вы не включили КСМПП Федерацию для своей организации. Тем не менее настроенные политики вступают в силу только в том случае, если у вас развернута, включена и настроена федерация КСМППных партнеров для вашей организации. Подробные сведения о развертывании и настройке Федерации КСМПП Partner можно найти <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">в разделе Настройка Федерации SIP, Федерации КСМПП и общедоступной службы обмена мгновенными сообщениями в приложении Lync Server 2013</A> в документации по развертыванию. Кроме того, если вы укажете политику пользователя во внешней политике доступа для управления КСМПП федеративными партнерами, политика применяется только к пользователям, которые включены в Lync Server 2013 и настроены на использование политики.



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>Изменение глобальной политики для федеративных партнеров КСМПП

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите **внешний доступ для пользователей**и нажмите кнопку **Политика внешних доступа**.

4.  На странице " **политика внешней доступа** " выполните указанные ниже действия для глобальной политики.

5.  Выберите глобальную политику, нажмите кнопку **изменить**и выберите пункт Показать подробности.

6.  Введите описание глобальной политики (необязательно).

7.  Выберите **включить связь с федеративными пользователями**.

8.  Выберите **включить связь с федеративными пользователями КСМПП**.

9.  Нажмите **** кнопку Сохранить, чтобы сохранить изменения в глобальной политике.

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>Создание политики сайта или пользователя для федеративных партнеров КСМПП

1.  Нажмите кнопку **создать**, а затем выберите пункт **Политика сайта** или **Политика пользователя**. В разделе **выберите сайт**выберите нужный сайт из списка и нажмите кнопку **ОК**.

2.  Введите описание политики сайта (необязательно).

3.  В разделе Политика сайта или пользователя выберите **включить связь с федеративными пользователями**.

4.  Выберите **включить связь с федеративными пользователями КСМПП**.

5.  Нажмите **** кнопку Сохранить, чтобы сохранить изменения в политике сайта или пользователя.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>Изменение существующей политики для федеративных партнеров КСМПП

1.  Чтобы изменить существующую политику, выберите соответствующую политику в списке, нажмите кнопку **изменить**, а затем выберите пункт **Показать подробности**.

2.  Измените или обновите описание политики (необязательно).

3.  Установите или снимите флажок **включить связь с федеративными пользователями**.

4.  Установите или снимите флажок **включить связь с федеративными пользователями КСМПП**.

5.  Нажмите **** кнопку Сохранить, чтобы сохранить изменения в политике.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Изменение существующей политики для федеративных партнеров КСМПП с помощью Windows PowerShell

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  В командной консоли Lync Server введите следующую команду:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Пример команды, с помощью которой можно настроить глобальную политику для доступа федеративного пользователя к true (Enabled) и доступ домена КСМПП к значению true (включено):
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>Создание политики сайта или пользователя для федеративных партнеров КСМПП с помощью Windows PowerShell

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  В командной консоли Lync Server введите следующую команду:
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Пример команды, которая позволяет настроить политику сайта для сайта Redmond для федеративного доступа пользователей к разрешенным и КСМПП доменам.
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Удаление существующей политики для федеративных партнеров КСМПП с помощью Windows PowerShell

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  В командной консоли Lync Server введите следующую команду:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Пример команды, которая удалит политику пользователя:
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Пример команды, которая будет сбрасывать для глобальной политики значения по умолчанию:
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>См. также


[Назначение политики доступа внешних пользователей пользователю, разрешенному для Lync в Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Включение или отключение федерации и подключение для общедоступного обмена мгновенными сообщениями в Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Управление федеративными XMPP-партнерами в Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
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

