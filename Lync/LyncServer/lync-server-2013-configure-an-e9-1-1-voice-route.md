---
title: 'Lync Server 2013: Настройка маршрута голосовой связи E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59f4e2a6707d270f66a66663b19f975ac69961c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a>Настройка маршрута голосовой связи E9-1-1 в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-17_

Чтобы развернуть E9-1-1, сначала необходимо настроить маршрут голосовой связи для выполнения экстренных вызовов. Дополнительные сведения о создании маршрутов голосовой связи можно найти [в разделе Создание голосового маршрута в Lync Server 2013](lync-server-2013-create-a-voice-route.md). Можно определить более одного маршрута, если, например, развертывание включает основной магистральный канал SIP и дополнительный магистральный канал SIP.

<div>


> [!NOTE]  
> Чтобы включить информацию о местоположении в приглашение E9-1-1 INVITE, необходимо настроить магистральный канал SIP, который служит для подключения к поставщику службы E9-1-1 для маршрутизации экстренных вызовов через шлюз. Для этого установите для флага EnablePIDFLOSupport в командлете <STRONG>Set-CsTrunkConfiguration</STRONG> значение True. Значение по умолчанию для EnablePIDFLOSupport — False. Например:<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE><BR>Не требуется включать получение местоположений для резервных шлюзов ТСОП и шлюзов ELIN.



</div>

Дополнительные сведения о работе с голосовыми маршрутами можно найти в документации по оболочке управления Lync Server для следующих командлетов:

  - **Set-CsPstnUsage**

  - **Get-CsPstnUsage**

  - **New-CsVoiceRoute**

  - **Get-CsVoiceRoute**

  - **Set-CsVoiceRoute**

  - **Remove-CsVoiceRoute**

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a>Настройка маршрута голосовой связи E9-1-1

1.  Выполните вход в систему компьютера с использованием учетной записи, которая является членом группы RTCUniversalServerAdmins или членом роли администратора CsVoiceAdministrator.

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Выполните следующий командлет, чтобы создать новую запись об использовании ТСОП.
    
    Это должно быть то же самое имя, которое будет использоваться для параметра **ТСОП** в политике определения местоположения. Хотя развертывание будет включать несколько записей об использовании телефона, в следующем примере показано, как добавить "Использование экстренных вызовов" в текущий список доступных использований ТСОП. Подробности можно найти в разделе [Настройка политик голосовой связи и использование PSTN для авторизации функций и привилегий для звонков в Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  Выполните следующий командлет, чтобы создать новый маршрут голосовой связи с помощью записи об использовании ТСОП, созданной на предыдущем этапе.
    
    Шаблон номера должен соответствовать шаблону номера, который используется в параметре **Строка набора номера для экстренной связи** политики определения местоположения. Знак "+" нужен, так как Lync добавляет "+" для вызова экстренной помощи. "Co1-pstngateway-1" — это идентификатор службы магистрального канала SIP для поставщика службы E9-1-1 или для идентификатора службы шлюза ELIN. В следующем примере в качестве имени маршрута голосовой связи используется EmergencyRoute.
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  Для магистральных соединений SIP мы также рекомендуем (по желанию) выполнить следующий командлет, чтобы создать локальный маршрут для вызовов, которые не обрабатываются магистральным каналом поставщика службы E9-1-1. Этот маршрут будет использоваться, если подключение к поставщику службы E9-1-1 недоступно.
    
    В следующем примере предполагается, что в политику голосовой связи пользователя включено использование "Локально".
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

