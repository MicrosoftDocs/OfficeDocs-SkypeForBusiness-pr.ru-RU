---
title: 'Lync Server 2013: настройка политики мобильных устройств'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7f71252064cef521058aba17a3c220a948e23c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841203"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>Настройка политики мобильных устройств в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 предоставляет политики для мобильных устройств, которые определяют, кто может использовать возможности мобильных устройств, звонки через Works, Voice по протоколу IP (VoIP) или видео, а также требуется ли WiFi для VoIP или видео. Функция "позвонить с помощью рабочих возможностей" позволяет мобильному пользователю совершать и принимать звонки с мобильного телефона с помощью рабочего номера вместо номера мобильного телефона. Эта функция предотвращает просмотр номера мобильного телефона вызывающего абонента и позволяет пользователю избежать оплаты за исходящие звонки. Настройка VoIP и видео дает возможность пользователям принимать и совершать звонки и видео по протоколу VoIP. Параметры использования WiFi определяют, требуется ли устройству пользователя возможность использования сети Wi-Fi для мобильной сети передачи данных.

По умолчанию мобильные устройства, звонки через Work и функции VoIP и видео включены. Параметры, необходимые для использования WiFi для VoIp и видео, отключены. Администраторы могут определить, кто имеет доступ к этим функциям, выполнив командлет. Вы можете отключить параметры глобально, по сайту или по пользователю.

Для использования функций мобильной связи и звонков через Work пользователи должны отвечать следующим требованиям:

  - Пользователи должны быть включены для Lync Server 2013.

  - Пользователи должны быть включены для корпоративной голосовой связи.

  - Пользователям должны быть назначены правила для мобильных устройств, у которых для параметра **енаблемобилити** задано значение true.

Чтобы пользователи могли использовать функцию "звонок с помощью работы", они должны удовлетворять следующим двум дополнительным требованиям:

  - Пользователям должна быть назначена политика голосовой связи, на которой установлен флажок **включить Одновременный звонок для телефонов** .

  - Пользователям должны быть назначены правила для мобильных устройств, у которых для параметра **енаблеаутсидевоице** задано значение true.

<div>


> [!NOTE]  
> Пользователи, не поддерживающие корпоративную голосовую почту, могут использовать свои мобильные устройства, чтобы сделать Lync для голосовой связи Lync по протоколу IP (VoIP), или присоединиться к конференциям с помощью ссылки Click to Join на мобильных устройствах, если вы назначаете этим пользователям соответствующие параметры для политики голосовой связи. Подробности можно найти <A href="lync-server-2013-defining-your-mobility-requirements.md">в разделе Определение требований к мобильным технологиям для Lync Server 2013</A>.



</div>

Дополнительные сведения о включении пользователей для Lync Server 2013 можно найти в разделе [Отключение и повторное включение учетной записи пользователя в Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Дополнительные сведения о включении поддержки пользователей для корпоративной голосовой связи можно найти [в разделе Включение поддержки пользователей для предприятий в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md). Подробнее о настройке параметров политики голосовой связи можно узнать [в статьях изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).

<div>

## <a name="to-modify-global-mobility-policy"></a>Изменение глобальной политики мобильности

1.  Войдите в систему на любом компьютере, на котором установлена оболочка Lync Server Management Shell и Окскоре, как участник роли Ксадминистратор.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Отключите доступ к мобильным технологиям и звоните с помощью глобальной работы. В командной строке выполните следующую команду:
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > Вы можете отключить функцию "звонок через", не отключив доступ к мобильному рабочему каналу. Однако вы не можете отключить функцию мобильной связи, не отключив и не отключая Звонок через работу.

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>Изменение политики мобильной связи по сайту

1.  Войдите в систему на любом компьютере, на котором установлена оболочка Lync Server Management Shell и Окскоре, как участник роли Ксадминистратор.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Создание политики на уровне сайта и отключение VoIP и видео, включение функции "требовать WiFi для IP-звука" и для IP-видео по сайту. В командной строке выполните следующую команду:
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>Изменение политики мобильности с помощью пользователя

1.  Войдите в систему на любом компьютере, на котором установлена оболочка Lync Server Management Shell и Окскоре, как участник роли Ксадминистратор.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Создавайте политики мобильности на уровне пользователей и отключайте мобильность и звоните по рабочему телефону. В командной строке выполните следующую команду:
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    Вы можете отключить функцию "звонок через", не отключив доступ к мобильному рабочему каналу. Однако вы не можете отключить функцию мобильной связи, не отключив и не отключая Звонок через работу.
    
    Например:
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>См. также


[Отключение и повторное включение учетной записи пользователя для Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Включение пользователей корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[Определение требований к мобильной работе для Lync Server 2013](lync-server-2013-defining-your-mobility-requirements.md)  


[New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[Grant-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

