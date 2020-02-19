---
title: 'Lync Server 2013: Настройка политики мобильности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring mobility policy
ms:assetid: 595536e0-9bb3-49a3-8d13-1a77351ebc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690018(v=OCS.15)
ms:contentKeyID: 48184204
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82ca5fbd079f428edf48ef3f0c28bd3677a5acde
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134755"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-mobility-policy-in-lync-server-2013"></a>Настройка политики мобильности в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-13_

    Some information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 предоставляет политики мобильности, которые определяют, кто может использовать функции мобильности, звонить через Works, Voice over IP (VoIP) или видео, а также требуется ли WiFi для VoIP или видео. Функция "позвонить с рабочего" позволяет пользователям мобильных устройств совершать и принимать звонки на мобильный телефон, используя номер рабочего телефона вместо номера мобильного телефона. Эта функция запрещает вызываемому абоненту Просмотр номера мобильного телефона вызывающего абонента и позволяет пользователю избежать оплаты за исходящие звонки. Настройка VoIP и видео дает пользователям возможность принимать и совершать звонки VoIP и видео. Параметры использования Wi-Fi определите, будет ли устройство пользователя использовать сеть Wi-Fi через сотовую сеть передачи данных.

По умолчанию мобильность, Звонок через Work и функции VoIP и видео включены. Параметры, требующие использования WiFi для VoIp и видео, отключены. Администраторы могут указывать, кому следует предоставить доступ к этим функциям, путем выполнения командлета. Можно отключить эти функции на глобальном уровне, на уровне узла или пользователя.

Использование мобильных функций и функции «Позвонить с рабочего» возможно при условии соблюдения следующих предварительных требований:

  - Пользователи должны быть включены для Lync Server 2013.

  - Для пользователей должна быть включена поддержка корпоративной голосовой связи.

  - Пользователям необходимо назначить политику мобильности с установленным значением True для параметра **EnableMobility**.

Чтобы пользователи могли использовать функцию «Позвонить с рабочего», необходимо соблюдение двух дополнительных предварительных требований:

  - Пользователям должна быть назначена политика голосовой связи с выбранной функцией **Разрешить одновременный звонок на несколько телефонов**.

  - Пользователям необходимо назначить политику мобильности с установленным значением True для параметра **EnableOutsideVoice**.

<div>


> [!NOTE]  
> Пользователи, не поддерживающие корпоративную голосовую связь, могут использовать свои мобильные устройства для совершения звонков Lync по ПРОТОКОЛу VoIP (VoIP) или присоединяться к конференциям с помощью ссылки щелкните, чтобы присоединиться к их мобильным устройствам, если назначить этим пользователям соответствующие параметры политики голосовой связи. Дополнительную информацию можно узнать <A href="lync-server-2013-defining-your-mobility-requirements.md">в статье Определение требований к мобильности для Lync Server 2013</A>.



</div>

Дополнительные сведения о включении пользователей для Lync Server 2013 приведены в статье [Отключение или повторное включение учетной записи пользователя для Lync server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md). Более подробную информацию о включении пользователей для корпоративной голосовой связи можно узнать [в статье Включение поддержки корпоративной голосовой связи в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md). Подробнее о настройке параметров политики голосовой связи можно узнать [в статье изменение политики голосовой связи и настройке записей использования PSTN в Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md).

<div>

## <a name="to-modify-global-mobility-policy"></a>Изменение глобальной мобильной политики

1.  Выполните вход на любой компьютер, на котором установлена командная консоль Lync Server и OCSCore, в качестве участника роли CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Отключите доступ к мобильной функции и функции «Позвонить с рабочего» на глобальном уровне. В командной строке введите:
    
        Set-CsMobilityPolicy -EnableMobility $False -EnableOutsideVoice $False
    
    <div>
    

    > [!NOTE]  
    > Можно отключить функцию «Позвонить с рабочего» без выключения доступа к функции мобильности. Однако вы не можете отключить функцию без выключения функции «Позвонить с рабочего».

    
    </div>

</div>

<div>

## <a name="to-modify-mobility-policy-by-site"></a>Изменение мобильной политики на уровне узла

1.  Выполните вход на любой компьютер, на котором установлена командная консоль Lync Server и OCSCore, в качестве участника роли CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Создайте политику на уровне сайта и отключите VoIP и видео, а затем включите параметр требовать WiFi для протокола IP Audio и для IP-видео по сайту. В командной строке введите следующую команду.
    
        New-CsMobilityPolicy -Identity site:<site identifier> -EnableIPAudioVideo $False -RequireWiFiForIPAudio $True -RequireWiFiForIPVideo $True

</div>

<div>

## <a name="to-modify-mobility-policy-by-user"></a>Изменение мобильной политики на уровне пользователя

1.  Выполните вход на любой компьютер, на котором установлена командная консоль Lync Server и OCSCore, в качестве участника роли CsAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Создайте мобильные политики на уровне пользователя и выключите функцию мобильности и функцию «Позвонить с рабочего» для конкретных пользователей. В командной строке введите:
    
        New-CsMobilityPolicy -Identity <policy name> -EnableMobility $False -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity <user identifier> -PolicyName <policy name>
    
    Можно отключить функцию «Позвонить с рабочего» без выключения доступа к функции мобильности. Однако вы не можете отключить функцию без выключения функции «Позвонить с рабочего».
    
    Пример:
    
        New-CsMobilityPolicy "tag:disableOutsideVoice" -EnableOutsideVoice $False
        Grant-CsMobilityPolicy -Identity -MobileUser1@contoso.com -PolicyName Tag:disableOutsideVoice

</div>

<div>

## <a name="see-also"></a>См. также


[Отключение или повторное включение учетной записи пользователя для Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Разрешить пользователям использовать корпоративную голосовую связь в Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md)  
[Изменение политики голосовой связи и настройка записей использования PSTN в Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  


[Определение требований к мобильности для Lync Server 2013](lync-server-2013-defining-your-mobility-requirements.md)  


[New — CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)  
[Set — CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)  
[Get — CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsMobilityPolicy)  
[Granting — CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsMobilityPolicy)  
[Remove — CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsMobilityPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

