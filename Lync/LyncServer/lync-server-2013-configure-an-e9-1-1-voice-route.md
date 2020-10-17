---
title: 'Lync Server 2013: Настройка маршрута голосовой связи E9 – 1 – 1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d5eb996b149bda87ea799768aea9821ec06f49f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523016"
---
# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a>Настройка маршрута голосовой связи E9 – 1 – 1 в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-17_

Чтобы развернуть E9-1-1, сначала необходимо настроить маршрут голосовой связи для выполнения экстренных вызовов. Более подробную информацию о создании маршрутов голосовой связи можно узнать [в статье Создание маршрута голосовых вызовов в Lync Server 2013](lync-server-2013-create-a-voice-route.md). Можно определить более одного маршрута, если, например, развертывание включает основной магистральный канал SIP и дополнительный магистральный канал SIP.

<div>


> [!NOTE]  
> Чтобы включить информацию о местоположении в приглашение E9-1-1 INVITE, необходимо настроить магистральный канал SIP, который служит для подключения к поставщику службы E9-1-1 для маршрутизации экстренных вызовов через шлюз. Для этого установите для флага EnablePIDFLOSupport в командлете <STRONG>Set-CsTrunkConfiguration</STRONG> значение True. Значение по умолчанию для EnablePIDFLOSupport — False. Например: <CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE><BR>Не требуется включать получение местоположений для резервных шлюзов ТСОП и шлюзов ELIN.



</div>

Для получения подробных сведений о работе с маршрутами голосовой связи обратитесь к документации по командной консоли Lync Server для следующих командлетов:

  - **Set — Кспстнусаже**

  - **Get — Кспстнусаже**

  - **New — Ксвоицерауте**

  - **Get — Ксвоицерауте**

  - **Set — Ксвоицерауте**

  - **Remove — Ксвоицерауте**

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a>Настройка маршрута голосовой связи E9-1-1

1.  Выполните вход в систему компьютера с использованием учетной записи, которая является членом группы RTCUniversalServerAdmins или членом роли администратора CsVoiceAdministrator.

2.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

3.  Выполните следующий командлет, чтобы создать новую запись об использовании ТСОП.
    
    Это должно быть то же самое имя, которое будет использоваться для параметра **ТСОП** в политике определения местоположения. Хотя развертывание будет включать несколько записей об использовании телефона, в следующем примере показано, как добавить «Использование экстренных вызовов» в текущий список доступных использований ТСОП. Подробнее: [Настройка политик голосовой связи и записей использования PSTN для авторизации функций звонков и привилегий в Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  Выполните следующий командлет, чтобы создать новый маршрут голосовой связи с помощью записи об использовании ТСОП, созданной на предыдущем этапе.
    
    Шаблон номера должен соответствовать шаблону номера, который используется в параметре **Строка набора номера для экстренной связи** политики определения местоположения. Знак "+" необходим, так как Lync добавляет "+" в экстренные вызовы. «Co1-pstngateway-1» — это идентификатор службы магистрального канала SIP для поставщика службы E9-1-1 или для идентификатора службы шлюза ELIN. В следующем примере в качестве имени маршрута голосовой связи используется EmergencyRoute.
    
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

