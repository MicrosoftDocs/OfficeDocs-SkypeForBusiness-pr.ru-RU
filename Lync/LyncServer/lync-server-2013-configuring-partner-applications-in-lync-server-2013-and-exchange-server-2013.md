---
title: Настройка партнерских приложений в Lync Server 2013 и Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dad815a67dafea510513e334c910a5dbb8a2e82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Настройка партнерских приложений в Microsoft Lync Server 2013 и Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-12_

Проверка подлинности "сервер-сервер" обычно включает три сущности: два сервера, которые должны взаимодействовать друг с другом, и сторонний сервер маркеров безопасности. Если на двух серверах (например, сервер A и B) требуется связь, то оба эти сервера обычно начинаются с того, чтобы они получали доступ к серверу-маркеру и получили взаимно доверенный маркер безопасности. Сервер а затем представляет маркер безопасности для сервера B (и наоборот), чтобы гарантировать как его подлинность, так и его надежность.

Однако это общее правило. Lync Server 2013, Microsoft Exchange Server 2013 и Microsoft SharePoint Server 2013 не требуется использовать сторонний сервер маркеров при взаимодействии друг с другом. Это может быть вызвано тем, что эти серверные продукты могут создавать маркеры безопасности, которые могут принимать друг друга, без необходимости использования отдельного сервера маркеров. (Эта возможность доступна только в Lync Server 2013, Exchange 2013 и SharePoint Server 2013. Для настройки проверки подлинности "сервер-сервер" с другими серверами, включая серверные продукты Microsoft, потребуется использование стороннего сервера маркеров.)

Для настройки проверки подлинности между сервером Lync Server и Exchange необходимо выполнить два действия: 1) необходимо назначить каждому серверу соответствующие сертификаты. и 2) необходимо настроить каждый сервер как приложение-партнер для другого сервера: это означает, что необходимо настроить Lync Server 2013 таким образом, чтобы он был партнерским приложением для Exchange 2013, и необходимо настроить Exchange 2013 как приложение-партнер для Lync Server 2013.

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>Настройка сервера Lync Server 2013 в качестве партнерской программы для Exchange 2013

Самый простой способ настроить Lync Server 2013 для использования в качестве партнерского приложения с Exchange 2013 — запустить сценарий Конфигуре-ентерприсепартнераппликатион. ps1 — сценарий Windows PowerShell, который поставляется с Exchange 2013. Чтобы выполнить этот сценарий, необходимо указать URL-адрес для документа метаданных проверки подлинности в Lync Server; как правило, это полное доменное имя пула Lync Server 2013, за которым следует суффикс/Metadata/JSON/1. Например:

    https://atl-cs-001.litwareinc.com/metadata/json/1

Чтобы настроить сервер Lync Server как партнерское приложение, откройте командную консоль Exchange и выполните следующую команду (предполагая, что Exchange установлен на диске C: и используется путь к папке по умолчанию):

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

После настройки приложения-партнера рекомендуется остановить и перезапустить службы IIS в почтовом ящике Exchange и на серверах клиентского доступа. Ниже приведен пример команды перезапуска служб IIS, относящийся к компьютеру atl-exchange-001.

    iisreset atl-exchange-001

Эту команду можно выполнить в командной консоли Exchange или в любом другом окне команд, которое запускается с правами администратора.

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>Настройка Exchange 2013 для приложения-партнера для Lync Server 2013

После того как вы настроили Lync Server 2013 в качестве партнера-приложения для Exchange 2013, необходимо настроить Exchange в качестве партнерского приложения для Lync Server. Это можно сделать, используя командную консоль Lync Server Management Shell и указав документ метаданных проверки подлинности для Exchange; как правило, это URI службы автообнаружения Exchange, за которой следует суффикс/Metadata/JSON/1. Например:

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

В Lync Server приложения-партнеры настраиваются с помощью командлета [New-кспартнераппликатион](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15)) . В дополнение к указанию URI метаданных необходимо также установить полный уровень доверия для приложения; Это позволит Exchange самостоятельно представлять себе и всех авторизованных пользователей в сфере. Например:

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

Кроме того, вы можете создать партнерское приложение, скопировав и изменив код сценария, который находится в документации по проверке подлинности серверов в Lync Server 2013. Дополнительные сведения можно найти [в статье Управление проверкой подлинности серверов (OAuth) и партнерских приложений в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .

Если вы успешно настроили партнерские приложения для Lync Server и Exchange, это означает, что вы также успешно настроили проверку подлинности серверов и серверов между двумя продуктами. Lync Server 2013 содержит командлет Windows PowerShell [Test-ксекссторажеконнективити](https://technet.microsoft.com/en-us/library/JJ204740(v=OCS.15)), который позволяет проверить правильность настройки проверки подлинности серверов и сервера в службе хранилища Lync Server, которая может подключиться к Exchange 2013. Командлет делает это, подключаясь к почтовому ящику пользователя Exchange 2013, записывая элемент в папку журнала бесед для этого пользователя и, при необходимости, удаляя его.

Чтобы протестировать интеграцию Lync Server 2013 и Exchange 2013, выполните в командной консоли Lync Server команду, подобную следующей:

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

В предыдущей команде Сипури представляет адрес SIP пользователя с учетной записью в Exchange 2013; не удается выполнить команду, так как она не является действительной учетной записью пользователя.

Если проверка завершилась успешно и соединение было установлено, можно перейти к настройке дополнительных компонентов, таких как интеграция службы архивации и единое хранилище контактов.

</div>

</div>

<span> </span>

</div>

</div>

</div>

