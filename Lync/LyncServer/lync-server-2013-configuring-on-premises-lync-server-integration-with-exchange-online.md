---
title: Настройка локальной интеграции Lync Server с Exchange Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60cfa8caa0aa2cb7dac704123f2a099bd305aed5
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a>Настройка локальной интеграции Lync Server 2013 с Exchange Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2018-03-30_

Клиенты, использующие локальные развертывания Lync Server 2013, могут настраивать взаимодействие с Microsoft Outlook Web App в Microsoft Exchange Online в режиме гибридного развертывания. Возможности взаимодействия включают единый вход и интеграцию обмена мгновенными сообщениями и сведениями о присутствии в интерфейс Outlook Web App. Чтобы включить эту интеграцию, необходимо настроить пограничный сервер в локальном развертывании Lync Server, выполнив следующие действия:

  - настройте общее адресное пространство SIP;

  - Настройка поставщика услуг хостинга на пограничном сервере

  - Проверка репликации обновленного центрального хранилища управления

Если Lync Server 2013 интегрируется с Exchange Online, пользователь, который пытается войти в систему обмена мгновенными сообщениями из OWA, считается удаленным или внешним пользователем. В этом сценарии пользователю должна быть назначена политика внешнего доступа, в которой выбран следующий параметр:

**Разрешить взаимодействие с удаленными пользователями**

Включите этот параметр, если вы хотите, чтобы пользователи в вашей организации, которые находятся за преправителями, например, пользователи, которые находятся в командировке, могли подключаться к Lync Server через Интернет.

Дополнительные сведения см в разделе [Manage External Access Policy in Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).

<div>

## <a name="configure-a-shared-sip-address-space"></a>Настройка общего адресного пространства SIP

Для интеграции локального сервера Lync Server 2013 с Exchange Online необходимо настроить общее адресное пространство SIP. Одно и то же адресное пространство домена SIP поддерживается как в Lync Server, так и в службе Exchange Online.

С помощью командной консоли Lync Server настройте пограничный сервер для Федерации, выполнив командлет **Set – CSAccessEdgeConfiguration** , используя параметры, показанные в следующем примере:

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers** указывает, разрешено ли внутренним пользователям взаимодействовать с пользователями из федеративных доменов. Это свойство также определяет, могут ли внутренние пользователи связываться с пользователями в общем адресном пространстве SIP с Lync Server и Exchange Online.

Сведения о том, как использовать командную консоль Lync Server, можно найти в статье [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Настройка поставщика услуг размещения на пограничном сервере

Используйте командную консоль Lync Server для настройки поставщика услуг хостинга на пограничном сервере. Для этого выполните командлет **New – CsHostingProvider** , используя параметры, приведенные в следующем примере:

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> Если вы используете Office 365 под управлением 21Vianet в Китае, замените значение параметра <STRONG>ProxyFqdn</STRONG> в этом примере ("exap.UM.Outlook.com") на полное доменное имя службы, обслуживаемой 21vianet: "exap.UM.Partner.Outlook.CN".



</div>

  - Параметр **Identity** определяет строковое значение уникального идентификатора для создаваемого поставщика услуг размещения (например, "Exchange Online"). Значения, содержащие пробелы, должны заключаться в двойные кавычки.

  - Параметр **Enabled** указывает, разрешено ли сетевое подключение между вашим доменом и поставщиком услуг размещения. Должно быть задано **значение true**.

  - **EnabledSharedAddressSpace** определяет, используется ли поставщик услуг размещения в общем адресном пространстве SIP. Должно быть задано **значение true**.

  - **Хостсоксусерс** указывает, используется ли поставщик услуг размещения для размещения Office Communications Server или Lync Server. Должно быть задано значение **false**.

  - Параметр **ProxyFQDN** определяет полное доменное имя прокси-сервера, используемого поставщиком услуг размещения. Для Exchange Online полное доменное имя — exap.um.outlook.com.

  - Параметр "... **" указывает,** входит ли прокси-сервер, используемый поставщиком услуг хостинга, в вашу топологию Lync Server. Должно быть задано значение **false**.

  - **Верификатионлевел** указывает уровень проверки, разрешенный для сообщений, отправляемых и получаемых поставщиком услуг размещения. Укажите **усесаурцеверификатион**. Этот вариант зависит от уровня проверки, включенного в сообщения, отправленные от поставщика услуг хостинга. Если этот уровень не указан, сообщение будет отклонено как Непроверяемое.

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a>Проверка репликации обновленного центрального хранилища управления

Изменения, внесенные с помощью командлетов, описанных в предыдущих разделах, автоматически применяются к пограничному серверу, и для репликации обычно требуется менее одной минуты. Вы можете проверить состояние репликации и применить изменения к пограничному серверу с помощью следующих командлетов.

Чтобы проверить наличие обновлений репликации на внутреннем сервере в развертывании Lync Server, выполните следующий командлет:

    Get-CsManagementStoreReplicationStatus

Чтобы убедиться, что изменения применены, выполните следующий командлет на пограничном сервере:

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a>См. также


[Предоставление пользователям Lync Server 2013 голосовой почты в размещенной единой системе обмена сообщениями Exchange](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Интеграция единой системы обмена сообщениями Exchange в среде Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
