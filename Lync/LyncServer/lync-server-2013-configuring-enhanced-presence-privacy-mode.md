---
title: 'Lync Server 2013: Настройка режима конфиденциальности расширенного присутствия'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring enhanced presence privacy mode
ms:assetid: e7a6b873-486d-4dfb-a967-c48f61f237f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399028(v=OCS.15)
ms:contentKeyID: 48185664
ms.date: 12/09/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c16e33197ed28744df126d672385359f5eb8781b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042991"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enhanced-presence-privacy-mode-in-lync-server-2013"></a>Настройка режима конфиденциальности расширенных сведений о присутствии в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-12-08_

Благодаря расширенному режиму конфиденциальности пользователей пользователи могут ограничить сведения о присутствии, чтобы они отображались только для контактов, перечисленных в списке контактов в Lync 2013. В командлетах **New – CsPrivacyConfiguration** и **Set CsPrivacyConfiguration** этот параметр управляется с помощью параметра енаблепривацимоде. Если для Енаблепривацимоде задано значение true, возможность ограничения сведений о присутствии для контактов становится доступной в параметрах состояния Lync 2013. Когда для EnablePrivacyMode задано значение False, пользователи могут либо разрешить всем остальным просматривать свои сведения, либо принять настройку режима конфиденциальности, выполненную администратором.

<div>


> [!IMPORTANT]  
> Параметры конфиденциальности Lync 2013 и Lync 2010 не принимаются в предыдущих версиях (Microsoft Office Communicator 2007 R2 или Microsoft Office Communicator 2007). Если более ранним версиям Office Communicator разрешено входить в систему, пользователи Lync 2013 могут просмотреть сведения о контакте, контактные данные или фотографию, если кто-то не получил разрешение на просмотр. Кроме того, параметры конфиденциальности пользователя Lync 2013 сбрасываются, если позже он подписывается с помощью предыдущей версии Communicator.<BR>Поэтому перед включением улучшенного режима конфиденциальности для сведений о присутствии во время миграции выполните следующие действия: 
> <UL>
> <LI>
> <P>Убедитесь, что у каждого пользователя установлен Lync 2013.</P>
> <LI>
> <P>Определите правило политики для версий клиента, чтобы предотвратить вход с использованием более ранних версий Communicator.</P></LI></UL>



</div>

<div>

## <a name="to-enable-enhanced-presence-privacy-mode"></a>Включение улучшенного режима конфиденциальности для сведений о присутствии

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Выполните следующую команду:
    
        Get-CsPrivacyConfiguration | Set-CsPrivacyConfiguration -EnablePrivacyMode $True
    
    Эта команда включает режим конфиденциальности для всех параметров конфигурации конфиденциальности, которые в текущий момент используются в организации. Дополнительные сведения о том, как конфигурации политики режима конфиденциальности для расширенного присутствия в Lync Server управляют присутствием контакта для клиента Lync 2013, в статье базы знаний Майкрософт, которая [Включение режима конфиденциальности Lync Server позволяет обновить состояние присутствия некоторых контактов Lync до "недоступно"](http://support.microsoft.com/kb/3020057).

</div>

<div>

## <a name="see-also"></a>См. также


[Get — CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPrivacyConfiguration)  
[New — CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsPrivacyConfiguration)  
[Set — CsPrivacyConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPrivacyConfiguration)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

