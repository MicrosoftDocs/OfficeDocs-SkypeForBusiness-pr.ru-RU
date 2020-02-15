---
title: Настройка партнерских приложений в Lync Server 2013 и Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring partner applications in Lync Server 2013 and Exchange Server 2013
ms:assetid: 9c3a3054-6201-433f-b128-4c49d3341370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688151(v=OCS.15)
ms:contentKeyID: 49733754
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d6eb00b5efcd811d0fbf1397bce5f8b965c9110
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046352"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-partner-applications-in-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Настройка партнерских приложений в Microsoft Lync Server 2013 и Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-12_

В проверке подлинности "сервер-сервер" обычно участвуют три объекта: два сервера, которые должны обмениваться данными, и сторонний сервер маркеров безопасности. Если двум серверам (например, серверу A и серверу B) необходимо обмениваться данными, оба сервера обычно начинают с обращения к серверу маркеров и получения взаимно доверенного маркера безопасности. Затем сервер A отправляет этот маркер безопасности серверу B (и наоборот) в качестве гарантии своей подлинности и надежности.

Однако это общее правило. Lync Server 2013, Microsoft Exchange Server 2013 и Microsoft SharePoint Server 2013 не требуется использовать сторонний сервер маркеров при взаимодействии друг с другом; Это связано с тем, что эти серверные продукты могут создавать маркеры безопасности, которые могут приниматься друг друга без необходимости использования отдельного сервера маркеров. (Эта возможность доступна только в Lync Server 2013, Exchange 2013 и SharePoint Server 2013. Для настройки проверки подлинности "сервер-сервер" с другими серверами, включая серверные продукты Майкрософт, потребуется использование стороннего сервера маркеров.

Для настройки межсерверной проверки подлинности между Lync Server и Exchange необходимо выполнить два действия: 1) необходимо назначить соответствующие сертификаты каждому серверу; и 2) необходимо настроить для каждого сервера партнерское приложение другого сервера: это означает, что необходимо настроить Lync Server 2013 как партнерское приложение для Exchange 2013, а Exchange 2013 — партнерское приложение для Lync Server 2013.

<div>

## <a name="configuring-lync-server-2013-to-be-a-partner-application-for-exchange-2013"></a>Настройка Lync Server 2013 в качестве партнерского приложения для Exchange 2013

Самый простой способ настроить Lync Server 2013 в качестве партнерского приложения с Exchange 2013 — запустить сценарий сценарий configure-enterprisepartnerapplication. ps1, сценарий Windows PowerShell, поставляемый с Exchange 2013. Для запуска этого сценария необходимо указать URL-адрес документа метаданных проверки подлинности Lync Server; как правило, это полное доменное имя пула Lync Server 2013, за которым следует суффикс/Metadata/JSON/1. Пример:

    https://atl-cs-001.litwareinc.com/metadata/json/1

Чтобы настроить Lync Server в качестве партнерского приложения, откройте командную консоль Exchange и выполните команду, аналогичную следующей, при условии, что Exchange установлен на диске C: и используется путь к папке по умолчанию.

    "C:\Program Files\Microsoft\Exchange Server\V15\Scripts\Configure-EnterprisePartnerApplication.ps1 -AuthMetaDataUrl 'https://atl-cs-001.litwareinc.com/metadata/json/1' -ApplicationType Lync"

После настройки партнерского приложения рекомендуется остановить и перезапустить службы IIS на серверах почтовых ящиков Exchange и клиентского доступа. Для перезапуска служб IIS можно использовать команду, аналогичную указанной, которая выполнит перезапуск службы на компьютере atl-exchange-001:

    iisreset atl-exchange-001

Эту команду можно выполнить в командной консоли Exchange или в любом другом командном окне, которое запускается с правами администратора.

</div>

<div>

## <a name="configuring-exchange-2013-to-be-a-partner-application-for-lync-server-2013"></a>Настройка Exchange 2013 в качестве партнерского приложения для Lync Server 2013

После настройки Lync Server 2013 в качестве партнерского приложения для Exchange 2013 необходимо настроить Exchange в качестве партнерского приложения для Lync Server. Это можно сделать с помощью командной консоли Lync Server и указав документ метаданных проверки подлинности для Exchange. как правило, это универсальный код ресурса (URI) службы автообнаружения Exchange, за которым следует суффикс/Metadata/JSON/1. Пример:

    https://autodiscover.litwareinc.com/autodiscover/metadata/json/1

В Lync Server партнерские приложения настраиваются с помощью командлета [New-CsPartnerApplication](https://technet.microsoft.com/library/JJ204628(v=OCS.15)) . В дополнение к указанию URI метаданных необходимо также установить полное значение уровня доверия для приложения; Это позволит Exchange предоставлять как самого себя, так и любого уполномоченного пользователя в сфере. Пример:

    New-CsPartnerApplication -Identity Exchange -ApplicationTrustLevel Full -MetadataUrl "https://autodiscover.litwareinc.com/autodiscover/metadata/json/1"

Кроме того, вы можете создать партнерское приложение, скопировав и изменив код скрипта, который находится в документации по проверке подлинности "сервер-сервер" в Lync Server 2013. Для получения дополнительных сведений ознакомьтесь со статьей [Управление межсерверной проверкой подлинности (OAuth) и партнерским приложением в Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md) .

Если вы успешно настроили партнерские приложения для Lync Server и Exchange, это означает, что вы успешно настроили межсерверную проверку подлинности между двумя продуктами. Lync Server 2013 включает командлет Windows PowerShell [Test-CsExStorageConnectivity](https://technet.microsoft.com/library/JJ204740(v=OCS.15)), который позволяет убедиться, что проверка подлинности между серверами настроена правильно и служба хранилища Lync Server может подключаться к Exchange 2013. Это выполняется командлетом, подключаясь к почтовому ящику пользователя Exchange 2013, записывая элемент в папку журнала бесед для этого пользователя, а затем (необязательно) удаление этого элемента.

Чтобы протестировать интеграцию Lync Server 2013 и Exchange 2013, выполните следующую команду в командной консоли Lync Server:

    Test-CsExStorageConnectivity -SipUri "sip:kenmyer@litwareinc.com"

В предыдущей команде Сипури представляет SIP адрес пользователя с учетной записью в Exchange 2013; команда не будет работать, так как она не является допустимой учетной записью пользователя.

Если проверка завершилась успешно и соединение было установлено, можно перейти к настройке дополнительных компонентов, таких как интеграция службы архивации и единое хранилище контактов.

</div>

</div>

<span> </span>

</div>

</div>

</div>

