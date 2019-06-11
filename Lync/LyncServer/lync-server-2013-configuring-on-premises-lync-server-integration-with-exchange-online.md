---
title: Настройка локальной интеграции Lync Server с Exchange Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae1ba45ace830f33b239bf2f8ead1a75fcee3417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841207"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a>Настройка локальной интеграции Lync Server 2013 с Exchange Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2018-03-30_

Клиенты, использующие локальные развертывания Lync Server 2013, могут настраивать взаимодействие с приложением Microsoft Outlook Web App в Microsoft Exchange Online в режиме гибридной развертки. Возможности взаимодействия включают единый вход и интеграцию обмена мгновенными сообщениями и сведениями о присутствии в интерфейс Outlook Web App. Чтобы включить эту интеграцию, необходимо настроить граничный сервер в локальной среде развертывания Lync Server, выполнив указанные ниже действия.

  - настройте общее адресное пространство SIP;

  - Настройка поставщика услуг размещения на пограничном сервере

  - Проверка репликации обновленного центрального хранилища в центре администрирования

Если Lync Server 2013 интегрирован с Exchange Online, пользователь, который пытается войти в мгновенном сообщении из OWA, считается удаленным или внешним пользователем. В этом случае пользователю должна быть назначена политика внешней доступа, для которой выбраны указанные ниже параметры.

**Включение связи с удаленными пользователями**

Включите этот параметр, если вы хотите, чтобы пользователи в вашей организации, которые находятся за пределами межсетевого экрана (например, подключены к сети и пользователи, которые находятся в дороге), смогли подключиться к серверу Lync через Интернет.

Дополнительные сведения можно найти [в разделе Управление политикой внешнего доступа в Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).

<div>

## <a name="configure-a-shared-sip-address-space"></a>Настройка общего адресного пространства SIP

Для интеграции локального сервера Lync Server 2013 с Exchange Online необходимо настроить общее адресное пространство SIP. Одно и то же адресное пространство домена SIP поддерживается как в Lync Server, так и в службе Exchange Online.

С помощью командной консоли Lync Server настройте сервер граничного сервера для Федерации, запустив командлет **Set-ксакцесседжеконфигуратион** , используя параметры, показанные в следующем примере.

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers** указывает, разрешено ли внутренним пользователям взаимодействовать с пользователями из федеративных доменов. Это свойство также определяет, могут ли внутренние пользователи общаться с пользователями в общем пространстве адресного пространства SIP с Lync Server и Exchange Online.

Подробнее об использовании командной консоли Lync Server можно узнать в разделе [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Настройка поставщика услуг размещения на пограничном сервере

Для настройки поставщика услуг размещения на пограничном сервере используйте командную консоль Lync Server Management Shell. Для этого выполните командлет **New-кшостингпровидер** с помощью параметров, описанных в приведенном ниже примере.

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> При использовании Office 365 под управлением 21Vianet в Китае замените значение для параметра <STRONG>ProxyFqdn</STRONG> (например, exap.um.outlook.com) на полное доменное имя для службы под управлением 21Vianet: "exap.um.partner.outlook.cn".



</div>

  - Параметр **Identity** определяет строковое значение уникального идентификатора для создаваемого поставщика услуг размещения (например, "Exchange Online"). Значения, содержащие пробелы, должны быть заключены в двойные кавычки.

  - Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения. Должно быть задано **значение true**.

  - Параметр **EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP. Должно быть задано **значение true**.

  - **Хостсоксусерс** указывает, используется ли поставщик услуг размещения для размещения Office Communications Server или Lync Server. Для него должно быть задано **значение false**.

  - Параметр **ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения. Полное доменное имя Exchange Online: exap.um.outlook.com.

  - **** "WebProxy" показывает, является ли прокси-сервер, используемый поставщиком услуг размещения, включен в топологию сервера Lync. Для него должно быть задано **значение false**.

  - **Верификатионлевел** указывает уровень проверки, разрешенный для сообщений, отправляемых и получаемых поставщиком услуг хостинга. Укажите **усесаурцеверификатион**. Этот параметр основывается на уровне проверки, который включен в сообщения, отправляемые поставщиком услуг размещения. Если этот уровень не указан, сообщение будет отвергнуто как Непроверяемое.

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a>Проверка репликации обновленного центрального хранилища управления

Изменения, внесенные с помощью командлетов в предыдущих разделах, автоматически применяются к пограничного сервера, и для их репликации обычно требуется менее одной минуты. Вы можете проверить состояние репликации и применить изменения на пограничном сервере с помощью следующих командлетов.

Чтобы проверить наличие обновлений репликации на внутреннем сервере в развертывании Lync Server, выполните следующий командлет:

    Get-CsManagementStoreReplicationStatus

Чтобы убедиться в том, что изменения применены, выполните на пограничном сервере следующий командлет:

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a>См. также


[Предоставление пользователям Lync Server 2013 голосовой почты в размещенной единой системе обмена сообщениями Exchange](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Интеграция с размещенной единой системой обмена сообщениями Exchange в Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

