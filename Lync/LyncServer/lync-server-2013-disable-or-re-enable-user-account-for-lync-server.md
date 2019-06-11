---
title: 'Lync Server 2013: отключение и повторное включение учетной записи пользователя Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disable or re-enable user account for Lync Server
ms:assetid: 12497d00-f665-4a97-be68-854c5a8be4fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429696(v=OCS.15)
ms:contentKeyID: 48183455
ms.date: 04/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7944af89ffae7545ba3a2593c7617fc944a7916e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834388"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disable-or-re-enable-user-account-for-lync-server-2013"></a>Отключение и повторное включение учетной записи пользователя для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2016-04-04_

Вы можете использовать описанную ниже процедуру, чтобы отключить ранее включенную учетную запись пользователя в Lync Server 2013 без потери параметров сервера Lync Server, настроенных для учетной записи пользователя. Так как вы не потеряли параметры учетной записи пользователя Lync Server, вы можете снова включить ее еще раз, не требуя повторной настройки учетной записи пользователя.

<div>


> [!WARNING]  
> Отключение учетной записи пользователя в службе каталогов Active Directory <STRONG>не</STRONG> означает, что пользователь сможет войти в Lync Server или использовать его. Это связано с тем, что Lync использует проверку подлинности сертификата, которая упрощает процесс проверки подлинности, и эти клиентские сертификаты действительны в течение 180 дней. Если вы хотите отключить отключенные учетные записи Active Directory, для которых в Lync разрешен доступ к серверу Lync Server, необходимо использовать командлет <STRONG>Disable-CsUser</STRONG> или воспользоваться <STRONG>панелью управления Lync Server</STRONG> в соответствии с инструкциями, изложенными в этой статье. После того как пользователь отключен в Lync и хранилище Центрального управления будет реплицировано в среде, пользователи больше не смогут входить. Кроме того, пользователи, которые вошли в систему, будут отключены.



</div>

<div>

## <a name="to-disable-or-re-enable-a-previously-enabled-user-account-for-lync-server"></a>Отключение и повторное включение учетной записи пользователя, включенного в Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Пользователи**.

4.  В поле **Поиск пользователей** введите все или первую часть отображаемого имени, имя, фамилию, диспетчер учетных записей безопасности (SAM), имя учетной записи, адрес SIP или универсальный код ресурса (URI) для учетной записи пользователя, которую вы хотите отключить или включить заново. и нажмите кнопку **найти**.

5.  В таблице выберите учетную запись пользователя, которую вы хотите отключить или включить заново.

6.  В меню **действия** выполните одно из указанных ниже действий.
    
      - Чтобы временно отключить учетную запись пользователя для Lync Server 2013, выберите **временно отключить для Lync Server**.
    
      - Чтобы включить учетную запись пользователя для Lync Server 2013, нажмите кнопку **повторно включить для Lync Server**.

</div>

<div>

## <a name="using-windows-powershell-to-disable-or-re-enable-user-accounts"></a>Использование Windows PowerShell для отключения и повторного включения учетных записей пользователей

Учетные записи пользователей можно временно отключить, а затем снова включить с помощью командлета **Set-CsUser** . Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

<div>

## <a name="to-disable-a-user-account"></a>Отключение учетной записи пользователя

  - Чтобы временно отключить учетную запись пользователя, установите для свойства Enabled значение false ($False). Например:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $False

</div>

<div>

## <a name="to-re-enable-a-user-account"></a>Повторное включение учетной записи пользователя

  - Чтобы повторно включить отключенную учетную запись пользователя, установите для свойства Enabled значение true ($True). Например:
    
        Set-CsUser -Identity "Ken Myer" -Enabled $True

</div>

Дополнительные сведения можно найти в разделе справки по командлету [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/Set-CsUser) .

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

