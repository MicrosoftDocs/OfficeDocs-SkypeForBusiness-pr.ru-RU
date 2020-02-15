---
title: 'Lync Server 2013: назначение политики голосовой связи на уровне пользователя'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assign a per-user voice policy
ms:assetid: 9ee47ee7-1030-43b8-a4dc-bf685ea24659
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688155(v=OCS.15)
ms:contentKeyID: 49733758
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 029d9c24a5fb460128c523192c7db682e2122370
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030112"
---
# <a name="assign-a-per-user-voice-policy-in-lync-server-2013"></a>Назначение политики голосовой связи на уровне пользователя в Lync Server 2013

 


Глобальные и на уровне сайта политики голосовой связи автоматически назначаются всем учетным записям пользователей Lync Server 2013, для которых включена поддержка корпоративной голосовой связи. Вы также можете назначать политики голосовой связи определенным пользователям с помощью панели управления Lync Server 2013 или командной консоли Lync Server 2013. Используйте процедуры, описанные в этом разделе, чтобы явным образом назначить политики для пользователей Lync Server.

## <a name="to-assign-a-user-specific-voice-policy-using-the-lync-server-control-panel"></a>Назначение политики голосовой связи для отдельных пользователей с помощью панели управления Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.

4.  В таблице, в которой перечислены результаты поиска, щелкните учетную запись пользователя, нажмите кнопку **Изменить** и нажмите кнопку **Подробнее**.

5.  В окне **Изменение пользователя Lync Server** в разделе **Политика голосовой связи** выберите необходимую политику пользователя.
    

    > [!NOTE]  
    > Параметры <STRONG> &lt;автоматического&gt; </STRONG> применения применяют параметры сервера по умолчанию или глобальные параметры политики.



## <a name="assigning-a-per-user-voice-policy-by-using-windows-powershell-cmdlets"></a>Назначение политики голосовой связи на уровне пользователя с помощью командлетов Windows PowerShell

Политики голосовой связи на уровне пользователей можно назначить с помощью Windows PowerShell и командлета **Grant – CsVoicePolicy** . Этот командлет можно выполнить из командной консоли Lync Server 2013 или из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

## <a name="to-assign-a-per-user-voice-policy-to-a-single-user"></a>Назначение индивидуальной политики голосовой связи одному пользователю

  - Следующая команда назначает политику голосовой связи уровня пользователя с именем RedmondVoicePolicy пользователю Ken Myer.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName "RedmondVoicePolicy"

## <a name="to-assign-a-per-user-voice-policy-to-multiple-users"></a>Назначение индивидуальной политики голосовой связи нескольким пользователям

  - Эта команда назначает политику голосовой связи уровня пользователя с именем FinanceVoicePolicy всем пользователям с учетными записями подразделения Finance в Active Directory. Для получения дополнительных сведений о параметре OU, используемом в этой команде, обратитесь к документации по командлету [Get – CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)) .
    
        Get-CsUser -OU "ou=Finance,ou=North America,dc=litwareinc,dc=com" | Grant-CsVoicePolicy -PolicyName "FinanceVoicePolicy"

## <a name="to-unassign-a-per-user-voice-policy"></a>Отмена назначения политики голосовой связи на уровне пользователя

  - Следующая команда отменяет политику голосовой связи уровня пользователя, назначенную пользователю Ken Myer. После отмены политики уровня пользователя к пользователю Ken Myer будет автоматически применяться глобальная политика или локальная политика сайта (если она существует). Политика сайта имеет приоритет над глобальной политикой.
    
        Grant-CsVoicePolicy -Identity "Ken Myer" -PolicyName $Null

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Grant – CsVoicePolicy](https://technet.microsoft.com/library/gg398828\(v=ocs.15\)) .

## <a name="see-also"></a>См. также


[Отключение пользователя для корпоративной голосовой связи в Lync Server 2013](lync-server-2013-disable-a-user-for-enterprise-voice.md)  


[Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md)

