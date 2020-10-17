---
title: 'Lync Server 2013: отключение или повторное включение учетной записи пользователя для Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 646f4ae59ce5058af84c0e5ddd3197f7a9f47fe7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528996"
---
# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>Отключение или повторное включение учетной записи пользователя для Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2016-04-04_

Вы можете использовать следующую процедуру, чтобы отключить ранее включенную учетную запись пользователя в Lync Server 2013 без потери параметров Lync Server, настроенных для учетной записи пользователя. Так как параметры учетной записи пользователя Lync Server не теряются, вы можете повторно включить учетную запись пользователя, включенную ранее, без необходимости повторной настройки учетной записи пользователя.

<div>


> [!WARNING]  
> Простое отключение учетной записи пользователя в Active Directory <STRONG>не приведет</STRONG> к прекращению входа пользователя в систему или использования Lync Server. Это связано с тем, что Lync использует проверку подлинности с помощью сертификата, которая упрощает процесс проверки подлинности, и эти сертификаты клиентов действительны в течение 180 дней. Если вы хотите остановить отключение отключенных учетных записей Active Directory, для которых в Lync был разрешен доступ к Lync Server, необходимо использовать командлет <STRONG>Disable – CsUser</STRONG> или использовать <STRONG>Панель управления Lync Server</STRONG> , как описано в этой статье. После отключения пользователя в Lync и репликации центрального хранилища управления в среде пользователи больше не смогут выполнять вход. Кроме того, пользователи, которые вошли в систему, будут отключены.



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>Отключение или повторное включение учетной записи пользователя, включенной ранее для Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Пользователи**.

4.  В поле **Search users** введите отображаемое имя (полностью или первую его часть), имя, фамилию, имя учетной записи SAM (Security Accounts Manager — диспетчер учетных записей безопасности), SIP-адрес или линейный идентификатор URI (Uniform Resource Identifier — универсальный код ресурса) учетной записи пользователя, которую требуется отключить или активировать повторно, а затем щелкните **Найти**.

5.  В таблице щелкните учетную запись пользователя, которую необходимо отключить или активировать повторно.

6.  В меню **Действие** выполните одно из следующих действий:
    
      - Чтобы временно отключить учетную запись пользователя для Lync Server 2013, выберите **временно отключить для Lync Server**.
    
      - Чтобы включить учетную запись пользователя для Lync Server 2013, нажмите кнопку **повторно включить для Lync Server**.

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Использование Windows PowerShell для отключения или повторного включения учетных записей пользователей

Учетные записи пользователей можно временно отключить, а затем снова включить с помощью командлета **Set – CsUser** . Этот командлет можно выполнить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-disable-a-user-account"></a>Отключение учетной записи пользователя

  - Чтобы временно отключить учетную запись пользователя, установите значение свойства "Enabled" равным False ($False). Пример:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>Повторное включение учетной записи пользователя

  - Чтобы повторно включить отключенную учетную запись пользователя, установите значение свойства "Enabled" равным True ($True). Пример:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Set – CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .

</div>

<div>

## <a name="see-also"></a>См. также


[Добавление и включение учетной записи пользователя для Lync Server 2013](lync-server-2013-add-and-enable-user-account-for-lync-server.md)  


[Включение и отключение пользователей для Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

